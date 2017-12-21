# PutResourceAttributes<a name="API_PutResourceAttributes"></a>

Provides identifying details of the resource being migrated so that it can be associated in the Application Discovery Service \(ADS\)'s repository\. This association occurs asynchronously after `PutResourceAttributes` returns\.

**Important**  
Keep in mind that subsequent calls to PutResourceAttributes will override previously stored attributes\. For example, if it is first called with a MAC address, but later, it is desired to *add* an IP address, it will then be required to call it with *both* the IP and MAC addresses to prevent overiding the MAC address\.

**Note**  
Because this is an asynchronous call, it will always return 200, whether an association occurs or not\. To confirm if an association was found based on the provided details, call `ListAssociatedResource`\.

## Request Syntax<a name="API_PutResourceAttributes_RequestSyntax"></a>

```
{
   "DryRun": boolean,
   "MigrationTaskName": "string",
   "ProgressUpdateStream": "string",
   "ResourceAttributeList": [ 
      { 
         "Type": "string",
         "Value": "string"
      }
   ]
}
```

## Request Parameters<a name="API_PutResourceAttributes_RequestParameters"></a>

The request accepts the following data in JSON format\.

 ** DryRun **   
Optional boolean flag to indicate whether any effect should take place\. Used to test if the caller has permission to make the call\.  
Type: Boolean  
Required: No

 ** MigrationTaskName **   
Unique identifier that references the migration task\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 256\.  
Pattern: `[^:|]+`   
Required: Yes

 ** ProgressUpdateStream **   
The name of the ProgressUpdateStream\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 50\.  
Pattern: `[^/:|\000-\037]+`   
Required: Yes

 ** ResourceAttributeList **   
Information about the resource that is being migrated\. This data will be used to map the task to a resource in the Application Discovery Service \(ADS\)'s repository\.  
Type: Array of [ResourceAttribute](API_ResourceAttribute.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 100 items\.  
Required: Yes

## Response Elements<a name="API_PutResourceAttributes_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response with an empty HTTP body\.

## Errors<a name="API_PutResourceAttributes_Errors"></a>

 **AccessDeniedException**   
You do not have sufficient access to perform this action\.  
HTTP Status Code: 400

 **DryRunOperation**   
Exception raised to indicate a successfully authorized action when the `DryRun` flag is set to "true"\.  
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

 **UnauthorizedOperation**   
Exception raised to indicate a request was not authorized when the `DryRun` flag is set to "true"\.  
HTTP Status Code: 400

## Example<a name="API_PutResourceAttributes_Examples"></a>

### Put migration resource attributes to associate with resource in repository<a name="API_PutResourceAttributes_Example_1"></a>

The following example sends identifying details of the resource being migrated so that it can be associated with a resource in the Application Discovery Service's repository using the values passed to the required parameters `MigrationTaskName` and `ProgressUpdateStream` to tag the correct target and its migration tool\. The `ResourceAttributeList` parameter is also required to define the resource type and its identifying value\.

The resource `Type` is restricted to one of the following values: `IPV4_ADDRESS | IPV6_ADDRESS | MAC_ADDRESS | FQDN | VM_MANAGER_ID | VM_MANAGED_OBJECT_REFERENCE | BIOS_ID | MOTHERBOARD_SERIAL_NUMBER | LABEL`, and the identifying `Value` can be a string up to 256 characters\.

#### Sample Request<a name="API_PutResourceAttributes_Example_1_Request"></a>

```
{
   "MigrationTaskName": "sms-12de3cf1a",
   "ProgressUpdateStream": "SMS",
   "ResourceAttributeList": [ 
      { 
         "Type": "MAC_ADDRESS",
         "Value": "06:D0:05:72:FF:A9"
      }
   ]
}
```

## See Also<a name="API_PutResourceAttributes_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/AWSMigrationHub-2017-05-31/PutResourceAttributes) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/AWSMigrationHub-2017-05-31/PutResourceAttributes) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/AWSMigrationHub-2017-05-31/PutResourceAttributes) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/AWSMigrationHub-2017-05-31/PutResourceAttributes) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/AWSMigrationHub-2017-05-31/PutResourceAttributes) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/AWSMigrationHub-2017-05-31/PutResourceAttributes) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/AWSMigrationHub-2017-05-31/PutResourceAttributes) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/AWSMigrationHub-2017-05-31/PutResourceAttributes) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/AWSMigrationHub-2017-05-31/PutResourceAttributes) 