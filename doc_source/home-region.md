# Migration Hub home Region<a name="home-region"></a>

The data stored in the AWS Migration Hub \(Migration Hub\) home Region provides a single repository of discovery and migration planning information for your entire migration portfolio\. The data stored in the home Region from the discovery and migration tools is used to track the progress of your migrations regardless of the migrating application’s target Region\. 

You can view discovered data and track the progress of your migrations in the Migration Hub console in your home Region\. The console gives you detailed visibility into discovered data and migration status, regardless of whether you are moving applications into one AWS Region or many\. 

From the console in your Migration Hub home Region, you can track your migration into any AWS Region, giving you a single view of migrations into multiple AWS Regions\.

For example, let's say you choose to set US West \(Oregon\) Region as your Migration Hub home Region\. You perform discovery of your data centers\. Then you analyze and identify your applications\. You then use AWS Application Migration Service \(Application Migration Service\) to migrate into the US West \(Oregon\) Region and the Europe \(Frankfurt\) Region\. You track your Application Migration Service migrations at the application level in the Migration Hub console\.

Throughout all of the migration steps in the example, your migration team uses Migration Hub in only one AWS Region – the home Region you chose, which is the US West \(Oregon\) Region\.

**Note**  
After your home Region is set, it can only be changed by contacting [AWS Support](http://aws.amazon.com/contact-us)\. For more information, see [Changing your Migration Hub home RegionChanging your home Region](#change-home-region)\.

You must choose a home Region before you can perform any write action from the console, AWS SDKs, or AWS CLI\. The following topics describe how to choose and change the home Region for your AWS account\.

**Topics**
+ [Choose a Migration Hub home Region](#select-home-region)
+ [Changing your Migration Hub home Region](#change-home-region)
+ [Discovery requires the home Region](#home-region-with-discovery)
+ [Migration progress is stored in the home Region](#migration-reporting)
+ [Working with the Migration Hub home Region APIs](#using-migration-hub-apis)

## Choose a Migration Hub home Region<a name="select-home-region"></a>

When you first use the AWS Migration Hub console, choose a Migration Hub home Region\. If you don't choose a home Region, you’ll be prompted to choose one before you can perform any write action from the console, AWS SDKs, or AWS CLI\. 

The Region that you choose to set as the home Region must be one of the AWS Regions supported by AWS Migration Hub\. For a list of the supported Regions, see [AWS Migration Hub Service endpoints](https://docs.aws.amazon.com/general/latest/gr/migrationhubn.html#migrationhub-region#migrationhub-region) in the *AWS General Reference*\. 

You can choose the home Region from the Migration Hub console or by using the Home Region API\. For information about using the API, see [Working with the Migration Hub home Region APIs](#using-migration-hub-apis)\. The following procedure describes how to choose the home region by using the console\. 

**To choose your home Region using the console**

1. Using your AWS account, sign in to the AWS Management Console and open the Migration Hub console at [https://console\.aws\.amazon\.com/migrationhub/](https://console.aws.amazon.com/migrationhub/)\.

1. In the lower\-section of the Migration Hub console navigation pane, choose **Settings**\.

1. Under **Migration Home Region**, select your home Region\.

1. Optionally, you can enable the console to automatically switch to your home Region the next time you sign in to the AWS Management Console\.

1. Choose **Confirm Home Region** to set the home Region\.

After you set your home Region, you can view it on the **Settings** page\.

After your home Region is set, it can only be changed by contacting [AWS Support](http://aws.amazon.com/contact-us)\. For more information, see [Changing your Migration Hub home RegionChanging your home Region](#change-home-region)\.

## Changing your Migration Hub home Region<a name="change-home-region"></a>

After it is set, the Migration Hub home Region can only be changed by contacting [AWS Support](http://aws.amazon.com/contact-us)\. 

Your home Region can only be changed to another AWS Region that is supported by AWS Migration Hub\. For a list of the supported Regions, see [AWS Migration Hub Service endpoints](https://docs.aws.amazon.com/general/latest/gr/migrationhubn.html) in the *AWS General Reference*\.

If you change the Migration Hub home Region, you'll need to recollect the data in the new home Region\. Data collected in the old home Region doesn't migrate to the new home Region\. 

## Discovery requires the home Region<a name="home-region-with-discovery"></a>

To start discovery and planning, you can deploy data collectors, such as AWS Application Discovery Agent \(Discovery Agent\) or Application Discovery Service Agentless Collector \(Agentless Collector\), into your data centers\. These tools send data to the AWS Migration Hub service in your home Region, and the information is displayed in your home Region in the console\.

Before you install your data collectors, you must choose an AWS Migration Hub home Region as described in [Choose a Migration Hub home Region](#select-home-region)\. Before collecting data, you must register your collectors in your home Region\. If you're using the AWS CLI, you must set up your AWS CLI to use the home Region as the default Region\.  

Discovery Agent discovers data for many types of hardware, hypervisors, and operating systems including Linux and Windows\. An agent must be installed on each host that is targeted for migration\. For specific information about the data fields that are returned by Discovery Agent, see [Data collected by Discovery Agent](https://docs.aws.amazon.com/application-discovery/latest/userguide/agent-data-collected.html) in the *Application Discovery Service User Guide*\.

Agentless Collector discovers data for VMware vCenter hosts and systems, using VMware metadata\. For specific information about the data fields that are returned by Agentless Collector, see [Data collected by Agentless Collector](https://docs.aws.amazon.com/application-discovery/latest/userguide/agentless-collector-data-collected.html) in the *Application Discovery Service User Guide*\.

Alternatively, you can use Migration Hub import to import details of your on\-premises environment directly into Migration Hub without using Agentless Collector or Discovery Agent\. For more information, see [Migration Hub import](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-import.html)\.

## Migration progress is stored in the home Region<a name="migration-reporting"></a>

When you’re ready to migrate, use the migration tools that best fit your needs\. Options include AWS Application Migration Service \(Application Migration Service\), AWS Database Migration Service \(AWS DMS\), or one of many third\-party tools\.

Migrate your servers and applications into any AWS Region, and the migration progress reported by each tool is stored in your home Region\. Stored data provides a single discovery and migration planning repository for your entire portfolio, and a single view of your migrations in multiple AWS Regions\.

Authorize your migration tools, such as Application Migration Service, to read discovery data from and send migration status to Migration Hub in your home Region\. The migration tools read application groupings and send basic identifying information for each resource\. For example, the hostname, IP address, MAC address, and VMware or hypervisor identifiers are sent, along with the resource’s migration status, from the migration’s destination Region to the Migration Hub home Region\.

## Working with the Migration Hub home Region APIs<a name="using-migration-hub-apis"></a>

You can call the AWS Migration Hub, AWS Application Discovery Service, and AWS Migration Hub home Region APIs from within your home Region *only*\. API calls for write actions \(create, notify, associate, disassociate, import, or put\) originating from outside your home Region are rejected, except for the ability to register your agents and collectors\. API calls for read actions \(list, describe, stop, and delete\) are permitted outside of your home Region\.

**Note**  
 You can register agents and collectors outside your home Region\. However, the `StartDataCollection` API call in AWS Application Discovery Service prevents you from enabling data collection from outside the home Region\.

The [AWS Migration Hub Home Region APIs](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/Welcome.html) are available specifically for working with your Migration Hub home Region\. The following is a general description of each API:
+ [CreateHomeRegionControl](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/API_CreateHomeRegionControl.html) – This API sets up the home Region\. It applies to the calling account only\.
+ [GetHomeRegion](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/API_GetHomeRegion.html) – Returns the calling account’s home Region, if configured\. This API is used by other AWS services to determine the regional endpoint for calling AWS Application Discovery Service and Migration Hub\.

  You must call `GetHomeRegion` at least once before you call any other Application Discovery Service and Migration Hub APIs, to obtain the account's Migration Hub home Region\.
+ [DescribeHomeRegionControls](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/API_DescribeHomeRegionControls.html) – This API permits filtering on the `ControlId`, `HomeRegion`, and `RegionControlScope` fields\.

For more information, see the [AWS Migration Hub Home Region API reference](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/Welcome.html)\.