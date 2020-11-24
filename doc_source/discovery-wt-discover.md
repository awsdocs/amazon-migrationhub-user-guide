# Phase 1: Discover<a name="discovery-wt-discover"></a>

This section describes the discovery phase in the following topics\. 

**Topics**
+ [Discover Step 1: Choose and Deploy AWS Discovery Tools](#discovery-wt-aws-disco-tools)
+ [Discover Step 2: View Server Details and Dependencies](#discovery-wt-view-disco-servers)
+ [Discover Step 3: Group Servers as Applications](#discovery-wt-group-as-applications)

## Discover Step 1: Choose and Deploy AWS Discovery Tools<a name="discovery-wt-aws-disco-tools"></a>

If you landed here from Step 3 of [Perform Discovery and Then Migrate](gs-new-user-discovery.md), or if you already have AWS discovery tools implemented and would like to deploy more, the following steps show you how to deploy either an [AWS Agentless Discovery Connector](#discovery-agent-less-wt) or an [AWS Application Discovery Agent](#discovery-agent-wt)\. If you have already performed discovery using an AWS Migration Partner discovery tool or have existing data from data sources such as a Configuration Management Database \(CMDB\) or IT Asset Management System \(ITAM\), you can use Migration Hub import to upload them\. For more information, see [Migration Hub Import](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-import.html) in the *Application Discovery Service User Guide*\.

To help you decide whether to choose a Discovery Connector or a Discovery Agent, the following comparison chart is provided\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/AgentConnectorCompTbl.png)

### Discovery Using the AWS Agentless Discovery Connector<a name="discovery-agent-less-wt"></a>

These steps walk you through the discovery process using an AWS Agentless Discovery Connector for collecting data about your on\-premises resources\.

The Discovery Connector is a VMWare appliance \(OVA\) and can only collect information about VMWare VMs\.

You use a Discovery Connector because it lets you quickly assess your infrastructure using a tool that isn’t specific to any operating system, without having to install anything on the servers themselves\.

**To discover resources using an agentless connector**

1. If you are proceeding from Step 3 of [Perform Discovery and Then Migrate](gs-new-user-discovery.md), choose **Download connector**; else, in the navigation pane, under **Discover**, choose **Tools**, and then choose **Download connector**\.

1. Deploy and configure the agentless connector by following the instructions specified in [Setting up Agentless Discovery](http://docs.aws.amazon.com/application-discovery/latest/userguide/setting-up-agentless.html) from the AWS Application Discovery Service User Guide\.

1. After you have successfully installed the agentless connector, return to the **Data Collectors** page on the Migration Hub console and choose the refresh icon\.

1. Select the check box of the connector\(s\) you want to start\.

1. Choose **Start data collection**\.

   1. To install additional connectors, repeat the above procedure\.

### Discovery Using the AWS Application Discovery Agent<a name="discovery-agent-wt"></a>

These steps walk you through the discovery process using an AWS Application Discovery Agent for collecting data about your on\-premises resources\.

You can install Discovery Agents on both your VMs and physical servers to not only discover your on\-premises servers, but also to capture technical specifications, system performance, network dependencies, and process information\. Network dependency and process information is available, but only for export\. Use the Application Discovery Service CLI to export the data and analyze it outside of the Migration Hub\. For more information, see [describe\-export\-tasks](http://docs.aws.amazon.com/cli/latest/reference/discovery/describe-export-tasks.html)\.

The beneﬁt of using a Discovery Agent is that it provides more detailed information than using the agentless Discovery Connector\. This information includes system performance and resource utilization\. In contrast, the beneﬁt of using a discovery connector is that it provides a more efficient and faster on\-premises infrastructure assessment\.

**To discover resources using an agent**

1. If you are proceeding from Step 3 of [Perform Discovery and Then Migrate](gs-new-user-discovery.md), choose **Download agent**, then in the dropdown, select either **Windows** or **Linux**; else, the **Download agent** button can be accessed by choosing **Tools** under **Discover** in the navigation pane\.

1. Deploy and configure the agent by following the instructions specified in [Setting up Agent Based Discovery](http://docs.aws.amazon.com/application-discovery/latest/userguide/setting-up-agents.html) from the AWS Application Discovery Service User Guide\.

1. After you have successfully installed the agent, return to the **Data Collectors** page on the Migration Hub console and choose the refresh icon\.

1. Select the check box of the agent\(s\) you want to start\.

1. Choose **Start data collection**\.

   1. To install additional agents, repeat the above procedure\.

## Discover Step 2: View Server Details and Dependencies<a name="discovery-wt-view-disco-servers"></a>

The following procedures describe how to view detailed information about servers discovered with AWS discovery tools\. 

### Viewing Server Details<a name="discovery-wt-view-disco-servers-details"></a>

The following procedure describes how to view information about the servers discovered by using any of the AWS discovery tools described in [Discover Step 1: Choose and Deploy AWS Discovery Tools](#discovery-wt-aws-disco-tools)\.

**To view details about a discovered server**

1. In the navigation pane, under **Discover**, choose **Servers**\. 

1. To view details about the server, choose the hostname of the server from the **Server info** column\. The server's detail page displays information about the server, such as hostname, IP address, performance metrics, and so on\.

### Exploring Server Network Connections<a name="discovery-wt-view-disco-servers-network"></a>

If you use AWS Application Discovery Agent for discovery, you can explore server network connections by using the network diagram in AWS Migration Hub\. 

Start exploring by choosing a single server or by choosing multiple servers at the same time\. Use the network diagram to explore your discovered servers and their connections to help you decide on how to group them together to assist in your migration planning\.

**To explore network connections starting with a single server**

1. In the navigation pane, under **Discover**, choose **Servers**\. 

1. To view details about the server, choose the hostname of the server from the **Server info** column\. The server's detail page displays information about the server, such as hostname, IP address, performance metrics, and so on\.

1. Choose **Network**\. The icon for the server you choose is centered in the network diagram\. Connections fan out from the center server to servers that are directly connected to the server you choose\.

1. Choose a server icon to see details about the server\. For information about how to work with the network diagram, see [Viewing Network Connections in Migration Hub](network-diagram.md)\. 

**To explore network connections starting with multiple servers**

1. In the navigation pane, under **Discover**, choose **Servers**\. 

1. To see the network connections for multiple servers, select the check box for each of the servers you want in the network diagram, and then choose **Visualize network**\.

1. You can modify the network diagram for the servers you chose\. For information on how to work with the network diagram, see [Viewing Network Connections in Migration Hub](network-diagram.md)\. 

## Discover Step 3: Group Servers as Applications<a name="discovery-wt-group-as-applications"></a>

The following procedures describe how to group servers as applications\. Because applications can have multiple servers, it can help simplify migration tracking to group them into logical units\.

### Grouping Servers as Applications from the Servers List<a name="discovery-wt-group-as-applications-server-list"></a>

The following procedure shows you how to select the servers you want to group for your application, how to create your application and name it, and how to add identifying tags\.

**Tip**  
You can import application groups in bulk using the AWS CLI for Application Discovery Service and calling the `CreateApplication` API\. For more information, see [CreateApplication](http://docs.aws.amazon.com/application-discovery/latest/APIReference/API_CreateApplication.html) in the *Application Discovery Service API Reference*\.

**To group servers into a new or existing application from the servers list**

1. In the navigation pane, choose **Servers**\.

1. In the servers list, select the check box for each of the servers you want to group into a new or existing application\.

   1. You can also search and filter on any of the criteria specified in the headers of the server list\. In the search box choose an item from the dropdown, then choose an operator from the next dropdown, and then type in your criteria\.

   1. Optionally, for each selected server, you can add a descriptive tag by choosing **Add tag** from the **Actions ** menu\. Doing so shows a dialog box where you can type a value for **Key**, and optionally a value for **Value**\.

1. Create your application, or add to an existing one, by choosing **Group as application**\.

1. In the **Group as application** dialog box, choose either **Group as a new application** or **Add to an existing application**\.

   1. If you chose **Group as a new application**, type a name in the **Application name** field\. Optionally, you can type a description for **Application description**\.

   1. If you chose **Add to an existing application**, choose the option next to the application name in the list box\.

1. Choose **Save**\. A green confirmation message is displayed at the top of the screen\.

### Grouping Servers as Applications from the Network Diagram<a name="discovery-wt-group-as-applications-net-diagram"></a>

You must select the servers in the network diagram that you want to group into a new or existing application\. 

The following procedure shows you how to select the servers you want to group for your application from the network diagram, how to create your application and name it, and how to add identifying tags\. 

**To group servers into a new or existing application from the network diagram**

1. Set up a network diagram following one of the procedures in the [Exploring Server Network Connections](#discovery-wt-view-disco-servers-network) section\. 

1. You can use the following options to select servers from the network diagram:
   + Choose a server node icon\. Details about the server show in the server details pane, where you choose **Select server**\.
   + Open the context \(right\-click\) menu on the server node icon, and then choose **Select server**\.
   + Choose **Select all** to select all the servers for grouping that are in your diagram\. Only the servers with the Discovery Agent running on them can be selected\.
   + Hold **shift** to select/unselect multiple servers at the same time\.

   Selected servers are shown in a list in the same pane as the server details\. You can toggle back and forth between the server details view and the selected server list view by choosing the server icon\. 

1. After you select one or more servers, create your application, or add to an existing one, by choosing **Group as application**\.

1. In the **Group as application** dialog box, choose either **Group as a new application** or **Add to an existing application**\.

   1. If you chose **Group as a new application**, type a name in the **Application name** field\. The servers that are members of the group are labeled on the diagram with the application name\. 

      Optionally, you can type a description for **Application description**\.

   1. If you chose **Add to an existing application**, choose the option next to the application name in the list box\.

1. Choose **Save**\. A green confirmation message is displayed at the top of the screen\.

1. Optionally, you can add a descriptive tag to the selected servers by choosing **Add tag** from the **Actions ** menu\. Doing so shows a dialog box where you can type a value for **Key**, and optionally a value for **Value**\.

**Next steps**

Once you have completed the three steps of the Discover phase, proceed to
+ [Phase 2: Migrate](discovery-wt-migrate.md)