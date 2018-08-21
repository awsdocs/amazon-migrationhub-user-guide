# Logging AWS Migration Hub API Calls with AWS CloudTrail<a name="logging-using-cloudtrail"></a>

Migration Hub is integrated with CloudTrail, a service that captures all of the Migration Hub API calls and delivers the log files to an Amazon S3 bucket that you specify\. CloudTrail captures API calls from the Migration Hub console or from your code to the Migration Hub API operations\. Using the information collected by CloudTrail, you can determine the request that was made to Migration Hub, the source IP address from which the request was made, who made the request, when it was made, and so on\. 

To learn more about CloudTrail, including how to configure and enable it, see the [AWS CloudTrail User Guide](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/)\.

## Migration Hub Information in CloudTrail<a name="migrationhub-info-in-cloudtrail"></a>

When CloudTrail logging is enabled in your AWS account, API calls made to Migration Hub actions are tracked in CloudTrail log files, where they are written with other AWS service records\. CloudTrail determines when to create and write to a new file based on a time period and file size\.

All Migration Hub actions are logged by CloudTrail and are documented in the [AWS Migration Hub API Reference](http://docs.aws.amazon.com//migrationhub/latest/ug/api-reference.html)\. For example, calls to the  `DescribeApplicationState`, `ImportMigrationTask`, `NotifyApplicationState`, and all of the rest of the Migration Hub actions generate entries in the CloudTrail log files\. 

Every log entry contains information about who generated the request\. The user identity information in the log entry helps you determine the following: 
+ Whether the request was made with root or IAM user credentials
+ Whether the request was made with temporary security credentials for a role or federated user
+ Whether the request was made by another AWS service

For more information, see the [CloudTrail userIdentity Element](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-user-identity.html)\.

You can store your log files in your Amazon S3 bucket for as long as you want, but you can also define Amazon S3 lifecycle rules to archive or delete log files automatically\. By default, your log files are encrypted with Amazon S3 server\-side encryption \(SSE\)\.

If you want to be notified upon log file delivery, you can configure CloudTrail to publish Amazon SNS notifications when new log files are delivered\. For more information, see [Configuring Amazon SNS Notifications for CloudTrail](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/getting_notifications_top_level.html)\.

You can also aggregate Migration Hub log files from multiple AWS regions and multiple AWS accounts into a single Amazon S3 bucket\. 

For more information, see [Receiving CloudTrail Log Files from Multiple Regions](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html) and [Receiving CloudTrail Log Files from Multiple Accounts](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html)\.

## Understanding Migration Hub Log File Entries<a name="understanding-migrationhub-entries"></a>

CloudTrail log files can contain one or more log entries\. Each entry lists multiple JSON\-formatted events\. A log entry represents a single request from any source and includes information about the requested action, the date and time of the action, request parameters, and so on\. Log entries are not an ordered stack trace of the public API calls, so they do not appear in any specific order\. 

The following example shows a CloudTrail log entry that demonstrates the  `DescribeApplicationState` action\.

```
{
    "eventVersion": "1.05",
    "userIdentity": {
        "type": "AssumedRole",
        "principalId": "AROAIGZQV3RRQMO4RQZCI:sally-90b99f9f-2ffd-4187-9ef1-26b9f22d6419",
        "arn": "arn:aws:sts::123456789012:assumed-role/Sally/sally-90b99f9f-2ffd-4187-9ef1-26b9f22d6419",
        "accountId": "123456789012",
        "accessKeyId": "AKIAIOSFODNN7EXAMPLE",
        "sessionContext": {
            "attributes": {
                "mfaAuthenticated": "false",
                "creationDate": "2017-05-23T23:54:04Z"
            },
            "sessionIssuer": {
                "type": "Role",
                "principalId": "AROAIGZQV3RRQMO4RQZCI",
                "arn": "arn:aws:iam::123456789012:role/Sally",
                "accountId": "123456789012",
                "userName": "Sally"
            }
        }
    },
    "eventTime": "2017-05-24T00:03:06Z",
    "eventSource": "migrationhub.amazonaws.com",
    "eventName": "DescribeApplicationState",
    "awsRegion": "us-west-2",
    "sourceIPAddress": "34.223.252.133",
    "userAgent": "aws-internal/3, sally-generated exec-env/AWS_Lambda_java8",
    "requestParameters": {"applicationId": "d-application-05d4e9901fa320fa0"},
    "responseElements": null,
    "requestID": "5d4eacdc-4014-11e7-925d-65290d4fc127",
    "eventID": "b12097ee-d121-43f4-a3f8-ca4aa57e6c94",
    "eventType": "AwsApiCall",
    "recipientAccountId": "123456789012"
}
```