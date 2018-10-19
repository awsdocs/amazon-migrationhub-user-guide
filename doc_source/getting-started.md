# Getting Started with AWS Migration Hub<a name="getting-started"></a>

In this section, you can find information about how to get started with AWS Migration Hub\. Included are steps to introduce you to the initial console screens that Migration Hub presents to a new user\.

**Topics**
+ [Assumptions](#gs-assumptions)
+ [Accessing AWS Migration Hub](#access-via-console-and-api)
+ [Two Ways to Get Started](#gs-the-two-ways)
+ [Perform Discovery and Then Migrate](gs-new-user-discovery.md)
+ [Migrate Without Performing Discovery](gs-new-user-migration.md)

**Note**  
If you are a developer or are interested in sending migration status from either a migration tool, script, or custom code, see [AWS Migration Hub API](api-reference.md)\.

## Assumptions<a name="gs-assumptions"></a>

For these exercises, the following is assumed:
+ You have signed up for AWS\. For more information, see [Setting Up](setting-up.md)
+ Migration Hub monitors the status of your migrations in all AWS regions, provided your migration tools are available in that region\.
+ The migration tools that integrate with Migration Hub send migration status to Migration Hub in us\-west\-2 where the status is aggregated and visible in a single location\.
+ The migration tools do not send status unless you have authorized \(that is, connected\) them\.
+ For a list of AWS regions where you can use Migration Hub, see the [Amazon Web Services General Reference](https://docs.aws.amazon.com/general/latest/gr/rande.html#migrationhub_region)\.

## Accessing AWS Migration Hub<a name="access-via-console-and-api"></a>

You can use AWS Migration Hub to track the status of application migrations\. The Getting Started section and various other sections of this guide use the AWS Migration Hub console to illustrate migration functionality\. You can find AWS Migration Hub at [AWS Migration Hub](http://console.aws.amazon.com/migrationhub/home)\.

Additionally, you can use the AWS Migration Hub API to track the status of your migrations from other tools or to send custom migration status to the AWS Migration Hub\. For more information about the API, see [AWS Migration Hub API](api-reference.md)\. 

You can also use the AWS SDKs to develop applications that interact with Migration Hub\. The AWS SDKs for Java, \.NET, and PHP wrap the underlying Migration Hub API to simplify your programming tasks\. For information about downloading the SDK libraries, see [Sample Code Libraries](http://aws.amazon.com/code)\.

## Two Ways to Get Started<a name="gs-the-two-ways"></a>

If you want to discover detailed information about your servers using AWS discovery tools before migrating, see [Perform Discovery and Then Migrate](gs-new-user-discovery.md) to guide you through the discovery process\.

If you want to start migrating immediately without using AWS discovery tools, see [Migrate Without Performing Discovery](gs-new-user-migration.md) to guide you through starting to migrate and tracking the status in Migration Hub\. You can also perform discovery at a later time if you want to gather server details\.

If this is the first time you are using Migration Hub or you have not sent any data to Migration Hub yet, you will see the new user screen where you will be given the option to choose one of the two migration workflows\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/DashNewUser.png)

To begin your migration, choose either **Get started with discovery** or **Get started migrating** and then proceed to the respective workflow listed in the topics below\.

**Topics**
+ Option 1: [Perform Discovery and Then Migrate](gs-new-user-discovery.md)
+ Option 2: [Migrate Without Performing Discovery](gs-new-user-migration.md)