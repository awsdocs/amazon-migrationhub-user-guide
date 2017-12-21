# MigrationTask<a name="API_MigrationTask"></a>

Represents a migration task in a migration tool\.

## Contents<a name="API_MigrationTask_Contents"></a>

 **MigrationTaskName**   
Unique identifier that references the migration task\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 256\.  
Pattern: `[^:|]+`   
Required: No

 **ProgressUpdateStream**   
A name that identifies the vendor of the migration tool being used\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 50\.  
Pattern: `[^/:|\000-\037]+`   
Required: No

 **ResourceAttributeList**   
  
Type: Array of [ResourceAttribute](API_ResourceAttribute.md) objects  
Array Members: Minimum number of 0 items\. Maximum number of 100 items\.  
Required: No

 **Task**   
Task object encapsulating task information\.  
Type: [Task](API_Task.md) object  
Required: No

 **UpdateDateTime**   
The timestamp when the task was gathered\.  
Type: Timestamp  
Required: No

## See Also<a name="API_MigrationTask_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/AWSMigrationHub-2017-05-31/MigrationTask) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/AWSMigrationHub-2017-05-31/MigrationTask) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/AWSMigrationHub-2017-05-31/MigrationTask) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/AWSMigrationHub-2017-05-31/MigrationTask) 