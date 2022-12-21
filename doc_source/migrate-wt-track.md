# Track the status of your migrations in Migration Hub<a name="migrate-wt-track"></a>

With a migration underway, you can track its progress status as well as details for each server grouped to the application\. This status is communicated to Migration Hub from the migration tool at key points during the migration\.

**To track an application's migration status**

1. After your application's migration has started, return to Migration Hub console and then choose **Dashboard** in the navigation pane\.

1. Under **Most recently updated applications**, choose the name of your migrating application\. Doing this displays the application's detail screen\.

   1. If you do not see all of your application's servers listed in the application's details page, it could be because you have not grouped those servers into this application yet\.  See [Updates About My Migrations Don't Appear Inside an Application](troubleshooting.md#migs-do-not-appear-in-app)\.

1. The first time a migration task is started for a server associated with the application, applications with this server will change to the **In progress** status, automatically\. After verifying the in\-progress migration status from the application's detail screen, if the status is still **Not started**, you can manually change it to **In progress**\. To change the status, choose **In progress** from the **Update status** menu\.

1. Choose **Confirm**\. A green confirmation message appears at the top of the screen, and the status label changes to **In progress**\.

1. When the data in the application's detail screen indicates migration has completed, and you've performed testing and verification, change the status from **In progress** to **Completed** from the **Update status** menu\.

1. Choose **Confirm**\. A green confirmation message appears at the top of the screen, and the status label changes to **Completed**\.

For more information about tracking, see [Migration Hub tracking, tagging, and console navigation tips](doing-more.md)\.