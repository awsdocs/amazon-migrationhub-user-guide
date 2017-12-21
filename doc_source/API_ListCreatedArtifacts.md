# ListCreatedArtifacts<a name="API_ListCreatedArtifacts"></a>

Lists the created artifacts attached to a given migration task in an update stream\. This API has the following traits:

+ Gets the list of the created artifacts while migration is taking place\.

+ Shows the artifacts created by the migration tool that was associated by the `AssociateCreatedArtifact` API\. 

+ Lists created artifacts in a paginated interface\. 

## Request Syntax<a name="API_ListCreatedArtifacts_RequestSyntax"></a>

```
{
   "MaxResults": number,
   "MigrationTaskName": "string",
   "NextToken": "string",
   "ProgressUpdateStream": "string"
}
```

## Request Parameters<a name="API_ListCreatedArtifacts_RequestParameters"></a>

The request accepts the following data in JSON format\.

 ** MaxResults **   
Maximum number of results to be returned per page\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 10\.  
Required: No

 ** MigrationTaskName **   
Unique identifier that references the migration task\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 256\.  
Pattern: `[^:|]+`   
Required: Yes

 ** NextToken **   
If a `NextToken` was returned by a previous call, there are more results available\. To retrieve the next page of results, make the call again using the returned token in `NextToken`\.  
Type: String  
Required: No

 ** ProgressUpdateStream **   
The name of the ProgressUpdateStream\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 50\.  
Pattern: `[^/:|\000-\037]+`   
Required: Yes

## Response Syntax<a name="API_ListCreatedArtifacts_ResponseSyntax"></a>

```
{
   "CreatedArtifactList": [ 
      { 
         "Description": "string",
         "Name": "string"
      }
   ],
   "NextToken": "string"
}
```

## Response Elements<a name="API_ListCreatedArtifacts_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** CreatedArtifactList **   
List of created artifacts up to the maximum number of results specified in the request\.  
Type: Array of [CreatedArtifact](API_CreatedArtifact.md) objects

 ** NextToken **   
If there are more created artifacts than the max result, return the next token to be passed to the next call as a bookmark of where to start from\.  
Type: String

## Errors<a name="API_ListCreatedArtifacts_Errors"></a>

 **AccessDeniedException**   
You do not have sufficient access to perform this action\.  
HTTP Status Code: 400

 **InternalServerError**   
Exception raised when there is an internal, configuration, or dependency error encountered\.  
HTTP Status Code: 500

 **InvalidInputException**   
Exception raised when the provided input violates a policy constraint or is entered in the wrong format or data type\.  
HTTP Status Code: 400

 **ResourceNotFoundException**   
Exception raised when the request references a resource \(ADS configuration, update stream, migration task, etc\.\) that does not exist in ADS \(Application Discovery Service\) or in Migration Hub's repository\.  
HTTP Status Code: 400

 **ServiceUnavailableException**   
Exception raised when there is an internal, configuration, or dependency error encountered\.  
HTTP Status Code: 500

## Example<a name="API_ListCreatedArtifacts_Examples"></a>

### List created artifacts associated with a migration task and update stream<a name="API_ListCreatedArtifacts_Example_1"></a>

The following example lists the created artifact name and its description that is associated with the values passed to the required parameters of `MigrationTaskName` and `ProgressUpdateStream` in the request\.

#### Sample Request<a name="API_ListCreatedArtifacts_Example_1_Request"></a>

```
{
    "ProgressUpdateStream": "SMS", 
    "MigrationTaskName": "sms-12de3cf1a", 
    "MaxResults": 1
}
```

#### Sample Response<a name="API_ListCreatedArtifacts_Example_1_Response"></a>

```
{
    "CreatedArtifactList": [
        {
            "Name": "arn:aws:ec2:us-east-1:488216288981:image/ami-6d0ba87b", 
            "Description": "Using SMS to migrate server to EC2"
        }
    ]
}
```

## See Also<a name="API_ListCreatedArtifacts_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/AWSMigrationHub-2017-05-31/ListCreatedArtifacts) 