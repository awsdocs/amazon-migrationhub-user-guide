# Troubleshooting AWS Migration Hub<a name="troubleshooting"></a>

Following, you can find information on how to troubleshoot issues for AWS Migration Hub\.


+ [My Migrations Do Not Appear in Migration Hub](#migs-do-not-appear-in-hub)
+ [Updates About My Migrations Don't Appear Inside an Application](#migs-do-not-appear-in-app)

## My Migrations Do Not Appear in Migration Hub<a name="migs-do-not-appear-in-hub"></a>

If you are not seeing your applications' migration status updates on the **Updates** page in Migration Hub, it is usually due to one of the following:

+ Migration tools not being authorized to commmunicate with Migration Hub\.

+ You do not have the neccesary polices and roles set up in IAM\.

+ Migration status mapping is incorrect needs to be done manually\.

### Authentication<a name="authenitcation-ts"></a>

To make sure authentication is occurring correctly:

+ Check if the migration tools you are using have been authorized to communicate with Migration Hub\. For more information, see [steps to authorize a migration tool](migrate-wt-migrate.md#migrate-wt-migrate-using-tools)\.

+ Check the [Tools page](http://console.aws.amazon.com/migrationhub/migrate/tools) to see the status of connected tools\. Learn more about setting up necessary polices and roles in [Required Managed Policies](new-customer-setup.md#required-managed-policies)\.

### Migration Status Matching When Using AWS Discovery Tools<a name="matching"></a>

+ Check if a migration update must be manually mapped or was incorrectly mapped to a discovered server, see [Tracking Migration Updates](doing-more.md#updates-tracking-wt)\.

## Updates About My Migrations Don't Appear Inside an Application<a name="migs-do-not-appear-in-app"></a>

If you are not seeing your migration updates associated with an application, it is usually due to one of the following:

+ Servers not being grouped as an application\.

+ Migration update status not being refreshed\.

+ Migration updates are not mapped or are incorrectly mapped to a server\.

### Servers' Application Grouping<a name="group-as-apps"></a>

+ Check if all your severs have been grouped into an application, see [steps to groups servers into applications](migrate-wt-migrate.md#migrate-wt-group-as-applications)\.

### Update Status<a name="update-status"></a>

+ The application details page requires you to refresh the page in order to see the latest status\. See [steps to track status of migrations](migrate-wt-track.md#migrate-wt-track-app-status)\.

### Update and Server Mapping<a name="update-mapping"></a>

+ Check if the update is present on **Updates** page\.

+ If not on the **Updates** page, then check if the migration tool was authorized by looking on the **Migration Tools** page \- in the navigation pane, under **Migrate**, choose **Tools**\.

+ On the **Updates** page, verify the update is mapped to the correct server \(will show "Edit" in "Mapped servers" column\)\.

+ If mapped to a server on the **Updates** page, then verify if the server is grouped into application on the **Servers** page with an application name present in the "Applications" column\.