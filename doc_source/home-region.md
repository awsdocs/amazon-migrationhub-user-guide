# The AWS Migration Hub home Region<a name="home-region"></a>

Your AWS Migration Hub data is stored in your home Region for purposes of discovery, planning, and migration tracking\. The status of migrations for your entire portfolio appears in your selected home Region\.

You can specify a home Region from the Migration Hub **Settings** page or by using the Home Region API\. To navigate to the **Settings** page, choose **Settings** from the Migration Hub console navigation pane\. For information about the Home Region API, see the [Migration Hub Home Region API Reference](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/Welcome.html)\.

 For information about changing the Migration Hub home Region after it is set, see [Changing your Migration Hub home Region](#change-home-region)\.

**Topics**
+ [Choose a Migration Hub home Region](#select-home-region)
+ [Changing your Migration Hub home Region](#change-home-region)
+ [Set a home Region for discovery](#home-region-with-discovery)
+ [Set a home Region for migration reporting](#migration-reporting)
+ [Working with the Migration Hub home Region APIs](#using-migration-hub-apis)

## Choose a Migration Hub home Region<a name="select-home-region"></a>

On your first use of the AWS Migration Hub console, select a Migration Hub home Region\. If you haven’t selected a home Region, you’ll be prompted to make a selection before you can perform any write action from the console, AWS SDKs, or AWS CLI\. After you select a home Region, you are redirected automatically to the console in that AWS Region\.

You can choose and view your current home Region on the Migration Hub **Settings** page\. To navigate to the **Settings** page, choose **Settings** from the navigation pane\.

For a list of the available AWS Migration Hub home Regions, see [AWS Migration Hub endpoints](https://docs.aws.amazon.com/general/latest/gr/migrationhubn.html) in the *AWS General Reference*\.

The Migration Hub console in your home Region gives you detailed visibility into discovery and migration, regardless of whether you are moving applications into one AWS Region or ten\. From your Migration Hub home Region, you can track your migration into any AWS Region\.

All of the discovery and migration tracking data sent from AWS tools or partner migration tools is stored and processed in your home Region, regardless of the migrating application’s target Region\.

For example, you can select US West \(Oregon\) as your Migration Hub home Region, then perform discovery of your datacenters, and analyze and identify your applications\. Then if you use AWS Application Migration Service \(Application Migration Service\) to migrate into the Oregon and Frankfurt AWS Regions, you can track your Application Migration Service migrations at the application level in Migration Hub\. Throughout each step in this example, your migration team uses Migration Hub in one AWS Region only – the home Region you selected, which is the US West \(Oregon\) Region\.

## Changing your Migration Hub home Region<a name="change-home-region"></a>

After it is set, the Migration Hub home Region can only be changed by contacting [AWS Support](http://aws.amazon.com/contact-us)\. If you change the Migration Hub home Region, data collected in the old home Region doesn't migrate to the new home Region\. You'll need to recollect the data in the new home Region\.

## Set a home Region for discovery<a name="home-region-with-discovery"></a>

To start discovery and planning, you can deploy data collectors, such as AWS Application Discovery Agent \(Discovery Agent\) or Application Discovery Service Agentless Collector \(Agentless Collector\), into your data centers\. These tools send data to the AWS Migration Hub service in your home Region, and the information is displayed on your home Region console\.

Before you install your data collectors, your home Region must be set\. Before collecting data, you must register your collectors in your home Region\. If you're using the AWS CLI, you must set up your AWS CLI to use the home Region as the default Region\. Instructions for how to set your home Region in the AWS CLI are provided in the AWS CLI sections of this guide\.

Discovery Agent discovers data for many types of hardware, hypervisors, and operating systems including Linux and Windows\. An agent must be installed on each host that is targeted for migration\. For specific information about the data fields that are returned by Discovery Agent, see [Data collected by Discovery Agent](https://docs.aws.amazon.com/application-discovery/latest/userguide/agent-data-collected.html) in the *Application Discovery Service User Guide*\.

Agentless Collector discovers data for VMWare vCenter hosts and systems, using VMWare metadata\. For specific information about the data fields that are returned by Agentless Collector, see [Data collected by Agentless Collector](https://docs.aws.amazon.com/application-discovery/latest/userguide/agentless-collector-data-collected.html) in the *Application Discovery Service User Guide*\.

Alternatively, you can use Migration Hub import to import details of your on\-premises environment directly into Migration Hub without using Agentless Collector or Discovery Agent\. For more information, see [Migration Hub import](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-import.html)\.

## Set a home Region for migration reporting<a name="migration-reporting"></a>

When you’re ready to migrate, use the migration tools that best fit your needs\. Options include AWS Application Migration Service \(Application Migration Service\), AWS Database Migration Service \(AWS DMS\), or one of many third\-party tools\. Migrate your servers and applications into any AWS Region, and the migration progress reported by each tool is stored in your home Region\. Stored data provides a single discovery and migration planning repository for your entire portfolio, and a single view of your migrations in multiple AWS Regions\.

Authorize your migration tools, such as Application Migration Service, to read discovery data from and send migration status to Migration Hub in your home Region\. The migration tools read application groupings and send basic identifying information for each resource\. For example, the hostname, IP address, MAC address, and VMware or hypervisor identifiers are sent, along with the resource’s migration status, from the migration’s destination Region to the Migration Hub home Region\.

## Working with the Migration Hub home Region APIs<a name="using-migration-hub-apis"></a>

You can call the AWS Migration Hub, AWS Application Discovery Service, and AWS Migration Hub home Region APIs from within your home Region *only*\. API calls for write actions \(create, notify, associate, disassociate, import, or put\) originating from outside your home Region are rejected, except for the ability to register your agents and collectors\. API calls for read actions \(list, describe, stop, and delete\) are permitted outside of your home Region\.

**Note**  
 You can register agents and collectors outside your home Region\. However, the `StartDataCollection` API call in AWS Application Discovery Service prevents you from enabling data collection from outside the home Region\.

The AWS Migration Hub home Region APIs are available specifically for working with your Migration Hub home Region\. A general description of each API is provided next\. For specific API usage, see the [AWS Migration Hub Home Region API reference](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/Welcome.html)\.

[CreateHomeRegionControl](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/API_CreateHomeRegionControl.html)

This API sets up the home Region\. It applies to the calling account only\.

[GetHomeRegion](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/API_GetHomeRegion.html)

Returns the calling account’s home Region, if configured\. This API is used by other AWS services to determine the regional endpoint for calling AWS Application Discovery Service and Migration Hub\.

You must call `GetHomeRegion` at least once before you call any other Application Discovery Service and Migration Hub APIs, to obtain the account's Migration Hub home Region\.

[DescribeHomeRegionControls](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/API_DescribeHomeRegionControls.html)

This API permits filtering on the `ControlId`, `HomeRegion`, and `RegionControlScope` fields\.