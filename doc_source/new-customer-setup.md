# New user IAM setup<a name="new-customer-setup"></a>

This section provides an overview of the AWS managed policies that can be used with AWS Migration Hub and instructions on how to use them\.

## Managed policies and roles<a name="required-managed-policies"></a>

The following are the AWS managed policies that can be used with Migration Hub:
+ **AWSMigrationHubFullAccess** – Grants access to the Migration Hub console and API/CLI for non\-administrative IAM users\.
+ **AWSMigrationHubDiscoveryServiceFullAccess** – Used by the **migrationhub\-discovery** role, the policy grants permission to allow the Migration Hub service to call Application Discovery Service\. You only need to use the `migrationhub-discovery` role if you use the AWS Command Line Interface \(AWS CLI\) or the AWS Migration Hub API without ever using the Migration Hub console\. For more information about AWSMigrationHubDiscoveryServiceFullAccess, see [AWSMigrationHubDiscoveryServiceFullAccess](https://docs.aws.amazon.com/application-discovery/latest/userguide/security-iam-awsmanpol.html#security-iam-awsmanpol-AWSApplicationDiscoveryServiceFullAccess) in the *Application Discovery Service User Guide*\. 
+ **AWSMigrationHubDMSAccess** – Used by the **migrationhub\-dms** role, the policy grants permission for Migration Hub to receive notifications from the AWS Database Migration Service migration tool\.

If you want to grant Migration Hub rights to non\-admin IAM users, see [Migration Hub Service API and Console Managed Access](#api-console-access-managed)\.

If you want to authorize \(that is, connect\) AWS migration tools, see [AWS Database Migration Service \(AWS DMS\)](#dms-managed)\.

### Migration Hub Service API and Console Managed Access<a name="api-console-access-managed"></a>

An administrator can create users and grant them permission to access the Migration Hub console using managed policies\.

**To grant permissions to an IAM user to access the Migration Hub console**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. Create an IAM user\. For information about creating an IAM user, see [Create an IAM user](setting-up.md#setting-up-iam)\.

1. After the user is created, choose the Permissions tab and then choose **Add Permissions**\. 

1. Choose **Attach existing policies directly**\. 

1. Select **AWSMigrationHubFullAccess** from the list of policies\. You can use the search box to find the policy or to filter the list\.

1. Choose **Next: Review**\.

1. Choose **Add permission**\.

### migrationhub\-discovery role<a name="adscaller-role-managed"></a>

Migration Hub requires access to the Application Discovery Service on your behalf\. 

If you use the AWS Migration Hub console, permissions to access Application Discovery Service are granted by the `AWSServiceRoleForMigrationHub` service linked role\. For more information, see [Using Roles to Connect Migration Hub to Application Discovery Service](using-service-linked-roles-discovery-service-role.md)\.

However, if you never use the Migration Hub console but you want to use the AWS Command Line Interface \(AWS CLI\) or the AWS Migration Hub API, you need to manually add the `migrationhub-discovery` role—which contains [AWSMigrationHubDiscoveryServiceFullAccess](https://docs.aws.amazon.com/application-discovery/latest/userguide/security-iam-awsmanpol.html#security-iam-awsmanpol-AWSApplicationDiscoveryServiceFullAccess)—to your AWS account\.

**To create the `migrationhub-discovery` role**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, under **Access management**, choose **Roles**\.

1. Choose **Create role**\.

1. Choose **AWS service**\.

1. Under **Use case for other AWS services **, choose **Migration Hub** from the dropdown, and then select **Migration Hub**\.

1. Choose **Next**\.

1. To attach the managed policy, select **AWSApplicationDiscoveryServiceFullAccess** from the list of policies on the **Add permissions** page\. You can use the search box to find the policy or to filter the list\.

1. Choose **Next**\.

1. You must enter **migrationhub\-discovery** for the **Role name**\. 

1. Choose **Create role**\.

Optionally, you can modify the role after you create it\.

**To modify the trust policy used by the `migrationhub-discovery` role**

1. In the navigation pane, under **Access management**, choose **Roles**\.

1. Choose the **migrationhub\-discovery** name from the list of roles\. You can use the search box to find the role or to filter the list\.

1. Choose the **Trust relationships** tab and then choose **Edit trust policy**\.

1. You can modify the trust policy under **Trusted entities**\. 

   For example, you can add an optional `Condition` *block* as show in the following example policy\. You can use it to limit the scope of the policy\. You can delete the block from the policy if you don't need it\.

   If you use the `Condition` block, you must add the ID of your AWS account and the AWS Region code for the Region where the resource resides to the policy, which are shown in *red*\. For example, `123456789012` is an example of an account ID and `us-east-2` is an example of a Region\.

   ```
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Effect": "Allow",
               "Principal": {
                   "Service": "migrationhub.amazonaws.com"
               },
               "Action": "sts:AssumeRole",
               "Condition": {
                   "StringEquals": {
                       "aws:SourceAccount": "account-id"
                   },
                   "StringLike": {
                       "aws:SourceArn": "arn:aws:mgh:region:account-id:*"
                   }
               }
           }
       ]
   }
   ```

1. Choose **Update Policy**\.

### Migration tools managed policies<a name="migration-tools-managed"></a>

This section describes AWS managed policies that are used with migration tools\.

#### AWS Database Migration Service \(AWS DMS\)<a name="dms-managed"></a>

The **AWSMigrationHubDMSAccess** AWS managed policy grants permissions to allow Migration Hub to receive notifications from the AWS DMS migration tool\.

The following procedure describes how to create the `migrationhub-dms` role that uses the **AWSMigrationHubDMSAccess** policy\.

**To create the `migrationhub-dms` role**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, under **Access management**, choose **Roles**\.

1. Choose **Create role**\.

1. Choose **AWS service**\.

1. Under **Use case for other AWS services **, choose **Migration Hub** from the dropdown, and then select **Migration Hub**\.

1. Choose **Next**\.

1. To attach the managed policy, select **AWSMigrationHubDMSAccess** from the list of policies on the **Add permissions** page\. You can use the search box to find the policy or to filter the list\.

1. Choose **Next**\.

1. You must enter **migrationhub\-dms** for the **Role name**\. 

1. Choose **Create role**\.