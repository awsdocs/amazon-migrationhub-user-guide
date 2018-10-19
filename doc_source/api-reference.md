# AWS Migration Hub API<a name="api-reference"></a>

The AWS Migration Hub API methods help to obtain server and application migration status and integrate your resource\-specific migration tool by providing a programmatic interface to Migration Hub\. 

## Reporting Migration Status Updates<a name="api-reference-workflow"></a>

### Creating a `ProgressUpdateStream` for your Migration Tool<a name="api-reference-create-pus-for-tool"></a>

In order to send status to Migration Hub, you must first create a `ProgressUpdateStream` corresponding to your migration tool using `CreateProgressUpdateStream` and `ProgressUpdateStreamName` is the namespace for your migration tool\. `ProgressUpdateStreamName` is scoped to the current AWS account, so it can be the same across all accounts\. `ProgressUpdateStreamName` will be displayed as\-is throughout the Migration Hub console as the name representing your migration tool\. For example, Server Migration Service uses `ProgressUpdateStreamName` “SMS” and it is displayed as the “Migration Tool” on the application’s page under the Migrate section\.

### Importing a Migration Task<a name="api-reference-import-migration-task"></a>

Once you’ve created a `ProgressUpdateStream`, you can start importing migration tasks from your migration tool by calling `ImportMigrationTask`\. It is recommended to call `ImportMigrationTask` as early as possible to inform the Migration Hub user about the existence of the task, even if the task has yet to be started\.

### Associating a Migration Task with a Previously Discovered Server<a name="api-reference-associate_task"></a>

In order to add migration task detail to the console, the task must be associated with a resource\. The resource represents the existing or source server for the migration\.   There are two ways that this association can be made:
+ **Auto\-mapping \(recommended\)**: A migration tool can associate \(Put\) sufficient identifiable information \(e\.g\., IP address, MAC address, and/or fully qualified domain name, and in a VMware environment, vCenter ID, MoRef ID, VM name, and/or VM folder path\) by calling `PutResourceAttributes` with a migration task so that AWS Migration Hub can correctly map the server being migrated to a server in AWS Application Discovery Service \(ADS\)'s servers repository\. If Migration Hub does not find a matching server in ADS’ server repository, then it automatically adds the server to the ADS repository\.
+ **Manual\-mapping**: Alternatively, a migration tool can allow the user to make this association manually by providing them with a mapping experience within the migration tool’s workflow that displays a list of existing AWS Application Discovery Service \(ADS\) servers\.
**Note**  
This approach is not recommended and rarely necessary since auto\-mapping \(above\) will automatically add and map the server from your tool to the Application Discovery Service repository when calling `PutResourceAttributes`\.

### Auto\-Map Explained<a name="api-reference-automatch"></a>
+ A migration tool uses the `PutResourceAttributes` API to provide information about the resource being migrated\. This is done by an asynchronous association made with the resource after the `PutResourceAttributes` call is returned\. If no matching server was found, then `PutResourceAttributes` automatically adds a server to the ADS repository and maps the migration task to the new server\.  This association can then be verified by calling `ListDiscoveredResource.` 
+ It is called with `MigrationTaskName` and `ResourceAttributes`\. The `MigrationTaskName` is an identifier provided by the migration tool\. This name uniquely identifies a migration task within your `ProgressUpdateStream`\.
+ The `ResourceAttributes` is descriptive information about the resource being migrated, such as a MAC address, IP address, fully qualified domain name, etc\. for servers, or in a VMware environment, VM name, vCenter Id or MoRef ID\. It can be used to associate the migration task with a server in the Application Discovery Service \(ADS\)\.

### Sending Migration Status Updates<a name="api-reference-send-updates"></a>

Now that a migration task exists, you can send migration status updates for display on the Migration Hub\. Call AWS Migration Hub's `NotifyMigrationTaskState` API to share the latest task status\.  The information returned from this call contains the migration task’s progress and status\. This is the information that customers see displayed in Migration Hub\.

The `MigrationTaskName` input parameter includes arguments used for addressing updates to the correct target task, and the `ProgressUpdateStream` parameter is used for access control and to provide a unique namespace scoped to the AWS account\. API parameters are described in detail later in this section\.

### Migration Tool Expected Behavior<a name="api-reference-expected-behaviour"></a>

The following points are important information regarding the interaction between the migration tool you use and AWS Migration Hub\.
+ The migration tool is expected to retry on Migration Hub API failures\.
+ The migration tool is expected to publish updates as often as possible\.  A migration tool must specify its own update expectations with every call to  `NotifyMigrationTaskState` API\. It is recommended to send updates as soon as they are available\.
+ The migration tool should call `PutResourceAttributes`\. If during the course of migration, the migration tool detects any change to the resource, or finds additional information, it can resend `PutResourceAttributes` data and Migration Hub will use the new values, overwriting old ones, and attempt to re\-map to a resource in the Application Discovery Service\.

## API Endpoint<a name="api-reference-endpoint"></a>

The API endpoint is the DNS name used as a host in the HTTP URI for the API calls\. These API endpoints are region\-specific and take the following form:

https://mgh\.us\-west\-2\.amazonaws\.com/

## API Version<a name="api-reference-version"></a>

The version of the API being used for a call is identified by the first path segment of the request URI, and its form is a ISO 8601 date\. 

The documentation describes API version 2017\-05\-31\.

## AWS CloudTrail<a name="api-cloudtrail-logging"></a>

Migration Hub is integrated with CloudTrail, a service that captures API calls from the Migration Hub console or from your code to the Migration Hub API operations\. Using the information collected by CloudTrail, you can determine the request that was made to Migration Hub, the source IP address from which the request was made, who made the request, when it was made, and so on\. See [Logging Migration Hub API Calls with AWS CloudTrail](logging-using-cloudtrail.md)\.

## Related Topics<a name="api-reference-related-topics"></a>

The following sections provide descriptions of the API operations, how to create a signature for request authentication, and how to grant permissions for these API operations using the IAM policies\.
+  [Authentication and Access Control for AWS Migration Hub](auth-and-access-control.md) 
+  [Actions](API_Operations.md) 
+  [Data Types](API_Types.md) 
+  [](logging-using-cloudtrail.md) 