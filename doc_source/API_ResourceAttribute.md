# ResourceAttribute<a name="API_ResourceAttribute"></a>

Attribute associated with a resource\.

Note the corresponding format required per type listed below:

IPV4  
 `x.x.x.x`   
 *where x is an integer in the range \[0,255\]* 

IPV6  
 `y : y : y : y : y : y : y : y`   
 *where y is a hexadecimal between 0 and FFFF\. \[0, FFFF\]* 

MAC\_ADDRESS  
 `^([0-9A-Fa-f]{2}[:-]){5}([0-9A-Fa-f]{2})$` 

FQDN  
 `^[^<>{}\\\\/?,=\\p{Cntrl}]{1,256}$` 

## Contents<a name="API_ResourceAttribute_Contents"></a>

 **Type**   
Type of resource\.  
Type: String  
Valid Values:` IPV4_ADDRESS | IPV6_ADDRESS | MAC_ADDRESS | FQDN | VM_MANAGER_ID | VM_MANAGED_OBJECT_REFERENCE | VM_NAME | VM_PATH | BIOS_ID | MOTHERBOARD_SERIAL_NUMBER | LABEL`   
Required: Yes

 **Value**   
Value of the resource type\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 256\.  
Required: Yes

## See Also<a name="API_ResourceAttribute_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/AWSMigrationHub-2017-05-31/ResourceAttribute) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/AWSMigrationHub-2017-05-31/ResourceAttribute) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/AWSMigrationHub-2017-05-31/ResourceAttribute) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/AWSMigrationHub-2017-05-31/ResourceAttribute) 