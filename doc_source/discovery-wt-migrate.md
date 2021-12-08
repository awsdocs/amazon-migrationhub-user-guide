# Phase 2: Migrate<a name="discovery-wt-migrate"></a>

The migrate phase has the following steps:
+ Connect migration tools to Migration Hub\.
+ Migrate using the connected migration tools\.

**Topics**
+ [Migrate Step 1: Connect migration tools to Migration Hub](#discovery-wt-auth-migrate-tools)
+ [Migrate Step 2: Migrate using the connected migration tools](#discovery-wt-migrate-using-tools)

## Migrate Step 1: Connect migration tools to Migration Hub<a name="discovery-wt-auth-migrate-tools"></a>

### <a name="migrate-step-1"></a>

Migration happens outside AWS Migration Hub using AWS migration tools or partner migration tools\. To access these tools, in the Migration Hub console navigation pane under **Migrate**, choose **Tools**\.

The table following lists the supported tools\.


| Resource type | Migration tool | 
| --- | --- | 
|  Server  |  **AWS Application Migration Service \(AWS MGN\)**–AWS Application Migration Service is the primary migration service recommended for lift\-and\-shift migrations to AWS\. For more information about AWS MGN, see [AWS Application Migration Service](http://aws.amazon.com/application-migration-service/) and [Using the AWS Migration Hub with MGN](https://docs.aws.amazon.com/mgn/latest/ug/mgn-mgh.html)\.  **AWS Server Migration Service \(AWS SMS\)**–For more information about AWS SMS, see [AWS Server Migration Service](http://aws.amazon.com/server-migration-service/) and [AWS SMS Documentation](https://docs.aws.amazon.com/server-migration-service/index.html)\. The **ATADATA ATAmotion partner tool**–For more information about ATAmotion, see [AWS Migration Hub Partners](http://aws.amazon.com/migration-hub/partners/)\.  | 
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

## Migrate Step 2: Migrate using the connected migration tools<a name="discovery-wt-migrate-using-tools"></a>

### <a name="migrate-step-2"></a>

The following steps walk you through the migration of a previously defined application\.

**To migrate an application**

1. In the Migration Hub console navigation pane under **Migrate**, choose **Tools**\.

1. If you connected \(authorized\) an AWS migration tool, choose the console link\. If you connected \(authorized\) an integrated partner's tool, choose the website link\.

1. When you have been linked to either the tool's console or website, follow the migration instructions for your selected migration tool as migration happens outside of Migration Hub\.

1. After your application's migration has started, return to Migration Hub\.

### <a name="w103aac12c15c25c11b5"></a>

**Next steps**

Once you have completed the two steps of the Migrate phase, proceed to
+ [Phase 3: Track](discovery-wt-track.md)