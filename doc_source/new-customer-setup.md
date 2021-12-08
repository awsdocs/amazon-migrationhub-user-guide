# New User IAM Setup<a name="new-customer-setup"></a>

This section provides an overview of the four managed policies that can be used with AWS Migration Hub as well as instructions on how to setup access to either the Migration Hub console or its APIs for users or migration tools\.

## Required Managed Policies<a name="required-managed-policies"></a>

The following AWS managed policies, which you can attach to users in your account, are specific to Migration Hub and are grouped by use case scenario:
+ **AWSMigrationHubDiscoveryAccess** – \(Included in the **migrationhub\-discovery** role\) – Grants permission to allow the Migration Hub service to call Application Discovery Service\.
+ **AWSMigrationHubFullAccess** – Grants access to the Migration Hub console and API/CLI for a user who's not an administrator\.
+ **AWSMigrationHubSMSAccess** – Grants permission for Migration Hub to receive notifications from the AWS Server Migration Service migration tool\.
+ **AWSMigrationHubDMSAccess** – Grants permission for Migration Hub to receive notifications from the AWS Database Migration Service migration tool\.

If you want to grant Migration Hub rights to non\-admin IAM users, then see [Migration Hub Service API and Console Managed Access](#api-console-access-managed)\.

If you want to authorize \(that is, connect\) AWS migration tools, see [AWS Server Migration Service \(AWS SMS\)](#sms-managed) or [AWS Database Migration Service \(AWS DMS\)](#dms-managed)\.

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

### migrationhub\-discovery Role<a name="adscaller-role-managed"></a>

To use Migration Hub, the `migrationhub-discovery` role \(which contains the `AWSMigrationHubDiscoveryAccess` policy\) must be added to your AWS account\. It allows Migration Hub to access the Application Discovery Service on your behalf\.

The AWS Migration Hub console creates the `migrationhub-discovery` role that is automatically attached to your AWS account when you use the Migration Hub console as an administrator\. If you use the AWS Command Line Interface \(AWS CLI\) or the AWS Migration Hub API without also using the console, you need to manually add this role to your account\.

**To create the `migrationhub-discovery` role**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, under **Access management**, choose **Roles**\.

1. Choose **Create role**\.

1. Choose **AWS service** and then under **Or select a service to view its use cases**, choose **Migration Hub**\.

1. Choose **Next: Permissions**\.

1. To attach the managed policy, select **AWSApplicationDiscoveryServiceFullAccess** from the list of policies\. You can use the search box find the policy or to filter the list\.

1. Choose **Next: Tags**\.

1. Choose **Next: Review**\.

1. You must enter **migrationhub\-discovery** for the **Role name**\. 

1. Choose **Create role**\.

1. Choose **Roles** in the navigation pane, and then choose the **migrationhub\-discovery** name from the list of roles\. You can use the search box to find the role or to filter the list\.

1. Choose the **Trust relationships** tab, and then choose **Edit trust relationship**\.

1. Under **Policy Document**, paste the following trust policy\. 

   The `Condition` *block* is optional\. You can use it to limit the scope of the policy\. Delete it from the policy if you don't need it\.

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
                       "aws: SourceAccount": "account-id"
                   },
                   "StringLike": {
                       "aws: SourceArn": "arn:aws:mgh:region:account-id:*"
                   }
               }
           }
       ]
   }
   ```

1. Choose **Update Trust Policy**\.

### Migration Tools \(Managed Policies\)<a name="migration-tools-managed"></a>

Roles and policies are needed for each migration tool in order for the Migration Hub to receive notifications from migration tools\. These permissions allow AWS services like AWS Server Migration Service and AWS Database Migration Service to send updates to Migration Hub\. The following procedures described how to create managed policies to use with AWS SMS and AWS DMS\.

#### AWS Server Migration Service \(AWS SMS\)<a name="sms-managed"></a>

**To create the `migrationhub-sms` role**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, under **Access management**, choose **Roles**\.

1. Choose **Create role**\.

1. Choose **AWS service** and then under **Or select a service to view its use cases**, choose **Migration Hub**\.

1. Choose **Next: Permissions**\.

1. To attach the managed policy, select **AWSMigrationHubSMSAccess** from the list of policies\. You can use the search box find the policy or to filter the list\.

1. Choose **Next: Tags**\.

1. Choose **Next: Review**\.

1. You must enter **migrationhub\-sms** for the **Role name**\. 

1. Choose **Create role**\.

1. Choose **Roles** in the navigation pane, and then choose the **migrationhub\-sms** name from the list of roles\. You can use the search box find the role or to filter the list\. 

1. Choose the **Trust relationships** tab, and then choose **Edit trust relationship**\.

1. Under **Policy Document**, paste the following trust policy\. 

   ```
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Effect": "Allow",
               "Principal": {
                   "Service": [
                       "sms.amazonaws.com"
                   ]
               },
               "Action": "sts:AssumeRole"
           }
       ]
   }
   ```

1. Choose **Update Trust Policy**\.

#### AWS Database Migration Service \(AWS DMS\)<a name="dms-managed"></a>

**To create the `migrationhub-dms` role**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, under **Access management**, choose **Roles**\.

1. Choose **Create role**\.

1. Choose **AWS service** and then under **Or select a service to view its use cases**, choose **Migration Hub**\.

1. Choose **Next: Permissions**\.

1. To attach the managed policy, select **AWSMigrationHubDMSAccess** from the list of policies\. You can use the search box find the policy or to filter the list\.

1. Choose **Next: Tags**\.

1. Choose **Next: Review**\.

1. You must enter **migrationhub\-dms** for the **Role name**\. 

1. Choose **Create role**\.

1. Choose **Roles** in the navigation pane, and then choose the **migrationhub\-sms** name from the list of roles\. You can use the search box find the role or to filter the list\. 

1. Choose the **Trust relationships** tab, and then choose **Edit trust relationship**\.

1. Under **Policy Document**, paste the following trust policy\. 

   ```
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Effect": "Allow",
               "Principal": {
                   "Service": [
                       "dms.amazonaws.com"
                   ]
               },
               "Action": "sts:AssumeRole"
           }
       ]
   }
   ```

1. Choose **Update Trust Policy**\.