# Migrate using Migration Hub migration tools<a name="migrate-wt-migrate"></a>

This section describes how to use the AWS Migration Hub to migrate your on\-premises servers and application resources to AWS and how to track the migration\.

**Topics**
+ [Step 1: Connect migration tools to Migration Hub\.](#migrate-wt-auth-migrate-tools)
+ [Step 2: Migrate using the connected migration tools](#migrate-wt-migrate-using-tools)
+ [Step 3: Group servers as applications](#migrate-wt-group-as-applications)

## Step 1: Connect migration tools to Migration Hub\.<a name="migrate-wt-auth-migrate-tools"></a>

### <a name="migrate-step-1"></a>

Migration happens outside AWS Migration Hub using AWS migration tools or partner migration tools\. To access these tools, in the Migration Hub console navigation pane under **Migrate**, choose **Tools**\.

The table following lists the supported tools\.


| Resource type | Migration tool | 
| --- | --- | 
|  Server  |  **AWS Application Migration Service \(Application Migration Service\)**–AWS Application Migration Service is the primary migration service recommended for lift\-and\-shift migrations to AWS\. For more information about Application Migration Service, see [AWS Application Migration Service](http://aws.amazon.com/application-migration-service/) and [Application Migration Service Documentation](https://docs.aws.amazon.com/mgn/index.html )\.  **AWS Server Migration Service \(AWS SMS\)**–For more information about AWS SMS, see [AWS Server Migration Service](http://aws.amazon.com/server-migration-service/) and [AWS SMS Documentation](https://docs.aws.amazon.com/server-migration-service/index.html)\.  As of March 31, 2022, AWS will discontinue AWS Server Migration Service \(AWS SMS\)\. You must complete your active migration projects that are using AWS SMS by March 31, 2022\. Going forward, we recommend AWS Application Migration Service \(Application Migration Service\) as the primary migration service for lift\-and\-shift migrations\. For more information, see [Using the AWS Migration Hub with Application Migration Service](https://docs.aws.amazon.com/mgn/latest/ug/mgn-mgh.html)\.   | 
| Database |  **AWS Database Migration Service \(AWS DMS\)**–For more information about AWS DMS, see [AWS Database Migration Service](http://aws.amazon.com/dms/) and [AWS DMS Documentation](https://docs.aws.amazon.com/dms/index.html)\.  | 

The preceding tools communicate directly to Migration Hub giving an aggregated view of their migrated progress and status so they can be tracked through Migration Hub\.

The following steps walk you through connecting \(authorizing\) your selected migration tool\.

**To connect \(authorize\) a migration tool**

1. In the Migration Hub console navigation pane under **Migrate**, choose **Tools**\.

1. Decide upon which AWS migration tool or integrated partners' tool to migrate your application\.

1. Choose **Connect** in the box to authorize the migration tool you selected to communicate with Migration Hub\. 

   1. AWS migration tools utilize a one\-click authorization process that automatically adds the required AWS Identity and Access Management \(IAM\) permissions role once you choose **Connect**\.

   1. Integrated partners' tools take you to their website when you choose **Connect** where you will be instructed on how to complete authorization\.

**Note**  
Note that if you are using API's or do not want to authorize through Migration Hub's console, you can learn about manual role creation in [New User IAM Setup](new-customer-setup.md)\.

## Step 2: Migrate using the connected migration tools<a name="migrate-wt-migrate-using-tools"></a>

### <a name="migrate-step-2"></a>

The following steps walk you through the migration of a previously defined application\.

**To migrate an application**

1. In the Migration Hub console navigation pane under **Migrate**, choose **Tools**\.

1. If you connected \(authorized\) an AWS migration tool, choose the console link\. If you connected \(authorized\) an integrated partner's tool, choose the website link\.

1. When you have been linked to either the tool's console or website, follow the migration instructions for your selected migration tool as migration happens outside of Migration Hub\.

1. After your application's migration has started, return to the Migration Hub console\.

## Step 3: Group servers as applications<a name="migrate-wt-group-as-applications"></a>

The following steps walk you through the process of grouping servers as applications when directly migrating with a migration tool without performing discovery first\. \(You already did this, if you first performed discovery as described in [Discovering on\-premises resources using AWS discovery tools](gs-new-user-discovery.md) before migrating\.\)

After the migration tool has started, you'll see the servers listed in Migration Hub from the migration updates sent from the migration tool\. You can select the servers and group them as applications\. Keep in mind that the server information communicated to Migration Hub from the migration tool is not as detailed as what is collected from a discovery tool\.

The following steps show you how to select the server or servers you want to group for your application, how to create your application and name it, and how to add identifying tags\.

**To group servers into a new or existing application**

1. In the Migration Hub console navigation pane, under **Discover**, choose **Servers**\.

1. In the severs list, select each of the servers that you want to group into a new or existing application\.

   1. You can also search and filter on any of the criteria specified in the headers of the server list\. Click inside the search bar and choose an item from the dropdown, then choose an operator from the next dropdown, and then type in your criteria\.

   1. Optionally, for each selected server, you can add a descriptive tag by choosing **Add tag**\. A dialog box appears where you can type a value for **Key**, and optionally, a value for **Value**\.

1. Create your application, or add to an existing one, by choosing **Group as application**\.

1. In the **Group as application** dialog box, select either **Group as a new application** or **Add to an existing application**\.

   1. If you chose **Group as a new application**, type a name for **Application name**\. Optionally, you can type a description for **Application description**\.

   1. If you chose **Add to an existing application**, select the radio button next to the application name in the list box\.

1. Choose **Save**\. A green confirmation message appears at the top of the screen\.

**Next steps**

After you complete the migration steps, proceed to
+ [Track the status of your migrations in Migration Hub](migrate-wt-track.md)