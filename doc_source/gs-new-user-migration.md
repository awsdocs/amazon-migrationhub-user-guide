# Migrate to AWS using Migration Hub migration tools and tracking<a name="gs-new-user-migration"></a>

You can start migrating with or without first using the Migration Hub discovery tools\. Directly migrating servers is efficient because your servers are migrating while you simultaneously group them into applications\.

Remember that if you haven't selected a Migration Hub home Region, the first time you view the console, you'll be required to select one\.

It is important to understand that connecting a migration tool to Migration Hub is how you authorize that tool to communicate migration status to Migration Hub in your home Region\. Without this authorization, Migration Hub will not track your migration\. 

As you perform the migration, the servers you are migrating appear in the **Servers** page\. On this page you can logically define and group all the servers that comprise the applications you are migrating\. You can also group more servers into either an existing or a new application at a later time\. To get to the **Servers** page, in the Migration Hub console navigation pane, under **Discover**, choose **Servers**\.

The following topics guide you through the migration process\.

**Topics**
+ [Migrate using Migration Hub migration tools](migrate-wt-migrate.md)
+ [Track the status of your migrations in Migration Hub](migrate-wt-track.md)