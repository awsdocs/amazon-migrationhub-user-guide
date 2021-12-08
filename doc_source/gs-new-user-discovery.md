# Get started with discovery<a name="gs-new-user-discovery"></a>

You can get data about your servers and applications into the AWS Migration Hub console for migration tracking in three ways; Migration Hub import, the AWS Agentless Discovery Connector, and the AWS Application Discovery Agent\.
+ **Migration Hub import** – With Migration Hub import, you can import information about your on\-premises servers and applications into Migration Hub, including server specifications and utilization data\. You can also use this data to track the status of application migrations\. For more information, see [Migration Hub import](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-import.html) in the *Application Discovery Service User Guide*\.
+ **AWS Agentless Discovery Connector** – The Discovery Connector is a VMware appliance that can collect information about VMware virtual machines \(VMs\)\. You install the Discovery Connector as a VM in your VMware vCenter Server environment using an Open Virtualization Archive \(OVA\) file\. Using the Discovery Connector minimizes the time required for initial on\-premises infrastructure assessment\. For more information, see [AWS Agentless Discovery Connector](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-connector.html) in the *Application Discovery Service User Guide*\.
+ **AWS Application Discovery Agent** – The Discovery Agent is AWS software that you install on your on\-premises servers and VMs to capture system configuration, system performance, running processes, and details of the network connections between systems\. Agents support most Linux and Windows operating systems, and you can deploy them on physical on\-premises servers, Amazon EC2 instances, and virtual machines\. For more information, see [AWS Application Discovery Agent](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-agent.html) in the *Application Discovery Service User Guide*\.

Discovering your servers first is an optional starting point for migrations by gathering detailed server information and then grouping the discovered servers into applications to be migrated and tracked\.

Use this section to guide you through the console pages that Migration Hub presents to the first\-time user to view, compare, and download AWS discovery tools\. To help you decide whether to choose a Discovery Connector or a Discovery Agent, see [Compare Connectors and Agents](https://docs.aws.amazon.com/application-discovery/latest/userguide/what-is-appdiscovery.html#compare-tools) in the *Application Discovery Service User Guide*\.

**To perform discovery and then migrate**

1. Choose **Get started with discovery** on the AWS Migration Hub page as described in [Two ways to get started](getting-started.md#gs-the-two-ways)\.

1. In the **Get started with discovery** dialog box, choose **Use discovery tools**\. 

   \(Optionally, you can choose **Import**\. For information about importing data, see [Migration Hub import](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-import.html) in the *Application Discovery Service User Guide*\.\)  
![\[The Get started with discovery dialog box.\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/mhub-get-started-discovery.png)

1. On the **Discovery Tools** page, you can download AWS discovery tools or import data\.   
![\[The Discovery Tools page.\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/mhub-discovery-tools.png)

1. To proceed with next steps, see [Phase 1: Discover](discovery-wt-discover.md) of the [Option 1: Perform discovery and then migrate](discovery-walkthroughs.md) walkthrough\.