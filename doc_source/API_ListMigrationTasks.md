# ListMigrationTasks<a name="API_ListMigrationTasks"></a>

Lists all, or filtered by resource name, migration tasks associated with the user account making this call\. This API has the following traits:

+ Can show a summary list of the most recent migration tasks\.

+ Can show a summary list of migration tasks associated with a given discovered resource\.

+ Lists migration tasks in a paginated interface\.

## Request Syntax<a name="API_ListMigrationTasks_RequestSyntax"></a>

```
{
   "MaxResults": number,
   "NextToken": "string",
   "ResourceName": "string"
}
```

## Request Parameters<a name="API_ListMigrationTasks_RequestParameters"></a>

The request accepts the following data in JSON format\.

 ** MaxResults **   
Value to specify how many results are returned per page\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 100\.  
Required: No

 ** NextToken **   
If a `NextToken` was returned by a previous call, there are more results available\. To retrieve the next page of results, make the call again using the returned token in `NextToken`\.  
Type: String  
Required: No

 ** ResourceName **   
Filter migration tasks by discovered resource name\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 1600\.  
Required: No

## Response Syntax<a name="API_ListMigrationTasks_ResponseSyntax"></a>

```
{
   "MigrationTaskSummaryList": [ 
      { 
         "MigrationTaskName": "string",
         "ProgressPercent": number,
         "ProgressUpdateStream": "string",
         "Status": "string",
         "StatusDetail": "string",
         "UpdateDateTime": number
      }
   ],
   "NextToken": "string"
}
```

## Response Elements<a name="API_ListMigrationTasks_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** MigrationTaskSummaryList **   
Lists the migration task's summary which includes: `MigrationTaskName`, `ProgressPercent`, `ProgressUpdateStream`, `Status`, and the `UpdateDateTime` for each task\.  
Type: Array of [MigrationTaskSummary](API_MigrationTaskSummary.md) objects

 ** NextToken **   
If there are more migration tasks than the max result, return the next token to be passed to the next call as a bookmark of where to start from\.  
Type: String

## Errors<a name="API_ListMigrationTasks_Errors"></a>

 **AccessDeniedException**   
You do not have sufficient access to perform this action\.  
HTTP Status Code: 400

 **InternalServerError**   
Exception raised when there is an internal, configuration, or dependency error encountered\.  
HTTP Status Code: 500

 **InvalidInputException**   
Exception raised when the provided input violates a policy constraint or is entered in the wrong format or data type\.  
HTTP Status Code: 400

 **PolicyErrorException**   
Exception raised when there are problems accessing ADS \(Application Discovery Service\); most likely due to a misconfigured policy or the `migrationhub-discovery` role is missing or not configured correctly\.  
HTTP Status Code: 400

 **ResourceNotFoundException**   
Exception raised when the request references a resource \(ADS configuration, update stream, migration task, etc\.\) that does not exist in ADS \(Application Discovery Service\) or in Migration Hub's repository\.  
HTTP Status Code: 400

 **ServiceUnavailableException**   
Exception raised when there is an internal, configuration, or dependency error encountered\.  
HTTP Status Code: 500

## Example<a name="API_ListMigrationTasks_Examples"></a>

### List a summary of all the migration tasks<a name="API_ListMigrationTasks_Example_1"></a>

The following example lists a summary of the migration tasks associated with the values passed to the optional parameters of `ResourceName` and `MaxResults`\.

#### Sample Request<a name="API_ListMigrationTasks_Example_1_Request"></a>

```
{
   "MaxResults": 1,
   "ResourceName": "d-server-0025db43a885966c8"
}
```

#### Sample Response<a name="API_ListMigrationTasks_Example_1_Response"></a>

```
{
    "MigrationTaskSummaryList": [
        {
            "Status": "COMPLETED", 
            "ProgressUpdateStream": "SMS", 
            "StatusDetail": "Replication finished", 
            "UpdateDateTime": 1487858882.0, 
            "MigrationTaskName": "sms-12de3cf1a"
        }
    ]
}
```

## See Also<a name="API_ListMigrationTasks_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/AWSMigrationHub-2017-05-31/ListMigrationTasks) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/AWSMigrationHub-2017-05-31/ListMigrationTasks) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/AWSMigrationHub-2017-05-31/ListMigrationTasks) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/AWSMigrationHub-2017-05-31/ListMigrationTasks) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/AWSMigrationHub-2017-05-31/ListMigrationTasks) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/AWSMigrationHub-2017-05-31/ListMigrationTasks) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/AWSMigrationHub-2017-05-31/ListMigrationTasks) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/AWSMigrationHub-2017-05-31/ListMigrationTasks) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/AWSMigrationHub-2017-05-31/ListMigrationTasks) 