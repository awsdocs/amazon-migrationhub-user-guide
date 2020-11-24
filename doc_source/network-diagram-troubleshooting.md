# Troubleshooting the Network Diagram<a name="network-diagram-troubleshooting"></a>

Use the information here to help you troubleshoot and fix issues that you might encounter when working with the network diagram in AWS Migration Hub\.

**Topics**
+ [Message that You Need to Install Discovery Agent](#troubleshooting-problem-need-agent)
+ [Problems When Adding Servers or Expanding Diagram](#troubleshooting-problem-expand-diagram)

## Message that You Need to Install Discovery Agent<a name="troubleshooting-problem-need-agent"></a>

The following topics describe scenarios when you get a message that you need to install Discovery Agent\.

### After choosing one or more servers on the server list page, and then choosing **Visualize network**, you get a message that you need to install a discovery agent on the server\.<a name="troubleshooting-problem-need-agent-1"></a>

Add AWS Application Discovery Service Discovery Agent to the servers that you that want mapped in the network diagram\. For more information, see [Setting up Agent Based Discovery](https://docs.aws.amazon.com/application-discovery/latest/userguide/setting-up-agents.html) the *Application Discovery Service User Guide*\. 

### When trying add a server that doesn't have discovery agent installed to a group, you get a message that you need to install discovery agent on the server\.<a name="troubleshooting-problem-need-agent-2"></a>

Add the Discovery Agent to the servers that you that want to be able to add to a group\.

## Problems When Adding Servers or Expanding Diagram<a name="troubleshooting-problem-expand-diagram"></a>

The following topics describe scenarios when you get a message when adding new servers or expanding existing servers\.

### When adding new servers or expanding existing servers on the network diagram, you get a message that your choices will cause the diagram to exceed its visual limit of 1,500 server nodes\.<a name="troubleshooting-problem-expand-diagram-1"></a>

Retry adding fewer servers\.

### When adding new servers or expanding existing servers on the network diagram, you experience high latency that leads to a time out\.<a name="troubleshooting-problem-expand-diagram-2"></a>

Retry adding fewer servers\.