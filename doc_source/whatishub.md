# What Is AWS Migration Hub?<a name="whatishub"></a>

AWS Migration Hub \(Migration Hub\) provides a single place to discover your existing servers, plan migrations, and track the status of each application migration\. The Migration Hub provides visibility into your application portfolio and streamlines planning and tracking\. You can visualize the connections and the status of the servers and databases that make up each of the applications you are migrating, regardless of which migration tool you are using\.

Migration Hub gives you the choice to start migrating right away and group servers while migration is underway, or to first discover servers and then group them into applications\. Either way, you can migrate each server in an application and track progress from each tool in the AWS Migration Hub\.

Migration Hub supports migration status updates from the following tools:
+ **AWS Application Migration Service \(Application Migration Service\)**–AWS Application Migration Service is the primary migration service recommended for lift\-and\-shift migrations to AWS\. For more information about Application Migration Service, see [AWS Application Migration Service](http://aws.amazon.com/application-migration-service/) and [Application Migration Service Documentation](https://docs.aws.amazon.com/mgn/index.html )\. 
+ **AWS Database Migration Service \(AWS DMS\)**–For more information about AWS DMS, see [AWS Database Migration Service](http://aws.amazon.com/dms/) and [AWS DMS Documentation](https://docs.aws.amazon.com/dms/index.html)\.

To access these tools, open the AWS Migration Hub console at [https://console\.aws\.amazon\.com/migrationhub/](https://console.aws.amazon.com/migrationhub/), and in the navigation pane under **Migrate**, choose **Tools**\. \(You must first have an AWS account and credentials to access the Migration Hub console\. For information about signing up for AWS, see [Setting up](setting-up.md)\.\)

## Are you a first\-time user of AWS Migration Hub?<a name="welcome-first-time-user"></a>

On your first use of the AWS Migration Hub console, you’re prompted to select a Migration Hub home region where your migration tracking data will be stored\. You can choose a home region on the **Settings** page of the console\. After you select a home region, you are redirected automatically to the console in that AWS Region\. You must make a selection before you can perform any write action from the console, SDK, or CLI interfaces\.

 If you are a first\-time user of AWS Migration Hub, we recommend that you read the following sections in order:
+  [Getting started](getting-started.md) 
+  [The AWS Migration Hub home Region](home-region.md) 

To learn about sending status to or querying status from AWS Migration Hub using the AWS SDK or AWS CLI, see the following API references:
+  [AWS Migration Hub API](api-reference.md) 
+  [AWS Migration Hub Home Region API](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/Welcome.html) 

**Note**  
Only your migration tracking data is stored in your home region\. You can migrate into any AWS Region that is supported by the migration tool that you use\.