# Getting started with AWS Migration Hub<a name="getting-started"></a>

In this section, you can find information about how to get started with AWS Migration Hub\. Included are steps to introduce you to the initial console pages that Migration Hub presents to a new user\.

Before you begin, be sure to set your home Region, either from the console or by using commands in the CLI\. 

The first time you view the Migration Hub console, you'll be prompted to choose a home Region\. You can choose and view your current home Region on the Migration Hub **Settings** page\. To navigate to the **Settings** page, choose **Settings** in the navigation pane\. After the home Region is set, it can only be changed by contacting [AWS Support](http://aws.amazon.com/contact-us)\. For information, see [Migration Hub home Region](home-region.md)\.

**Note**  
If you are a developer or are interested in sending migration status from a migration tool, script, or custom code, see [AWS Migration Hub API](api-reference.md) and [AWS Migration Hub Home Region API Reference](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/Welcome.html)\.  
All Migration Hub and AWS Application Discovery Service API commands must be called from within the home Region only, and they require you to call `GetHomeRegion` at least once before you call any other API, to obtain the account's Migration Hub home Region\. Calls originating from outside your home Region are rejected\.

**Topics**
+ [Assumptions](#gs-assumptions)
+ [Access to AWS Migration Hub](#access-via-console-and-api)
+ [Discovering on\-premises resources using AWS discovery tools](gs-new-user-discovery.md)
+ [Migrate to AWS using Migration Hub migration tools and tracking](gs-new-user-migration.md)
+ [Strategy Recommendations](gs-strategy-reccommendations.md)
+ [Refactor Spaces](gs-refactor-spaces.md)
+ [Migration Hub Orchestrator](gs-orchestrator.md)

## Assumptions<a name="gs-assumptions"></a>

For the Migration Hub walkthroughs, we make the following assumptions:
+ You have signed up for AWS\. For more information, see [Setting up](setting-up.md)\.
+ You have selected your Migration Hub home Region\.

Here's what to expect:
+ Migration Hub monitors the status of your migrations in all AWS Regions, provided that your migration tools are available in each Region\. 
+ The migration status of every AWS Region undergoing migration is shown in your home Region console\.
+ The migration tools that integrate with Migration Hub store all data about your migration status in Migration Hub\. The data is stored in your selected home Region\.
+ The migration tools do not send a status unless you have authorized their connection\.
+ For a list of AWS Regions where you can use Migration Hub, see the [Amazon Web Services General Reference](https://docs.aws.amazon.com/general/latest/gr/rande.html#migrationhub_region)\.
+ For more information about working with your home Region, see the section about [Migration Hub home Region](home-region.md)\.

## Access to AWS Migration Hub<a name="access-via-console-and-api"></a>

AWS Migration Hub tracks the status of application migrations on the AWS Migration Hub console in your home Region\. The Getting Started section and other sections of this guide use the console to illustrate migration functionality\. Open the AWS Migration Hub console at [https://console\.aws\.amazon\.com/migrationhub/](https://console.aws.amazon.com/migrationhub/)\.

Additionally, you can use the AWS Migration Hub API to track the status of your migrations from other tools, or to send custom migration status to AWS Migration Hub\. For more information about the Migration Hub API, see [AWS Migration Hub API](api-reference.md)\. You'll also need to call the `GetHomeRegion` API from the Migration Hub [home region API](https://docs.aws.amazon.com/migrationhub-home-region/latest/APIReference/Welcome.html) when working with Migration Hub programmatically\. 

The AWS SDKs assist you to develop applications that interact with Migration Hub\. The AWS SDKs for Java, \.NET, and PHP wrap the underlying Migration Hub API to simplify your programming tasks\. For information about downloading the SDK libraries, see [Sample Code Libraries](http://aws.amazon.com/code)\.

