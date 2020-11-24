# Viewing Network Connections in Migration Hub<a name="network-diagram"></a>

Viewing network connections in AWS Migration Hub allows you to visualize a server's dependencies\. The visualization of these dependencies helps you verify all of the resources required to successfully migrate each of your applications to Amazon Web Services\.

You view network connections by using the network diagram\. When using the network diagram, you can visually review large amounts of data to understand what server dependencies exist\. Understanding these server dependencies helps you plan how to group together the needed resources to support an application for migration to AWS\.

The following topics provide information about using the network diagram\.

**Topics**
+ [Use the Network Diagram to View Connections](#network-diagram-what-is)
+ [Prerequisites for Using the Network Diagram in Migration Hub](network-diagram-prerequisites.md)
+ [How to Use the Network Diagram in Migration Hub](network-diagram-how-to.md)
+ [Troubleshooting the Network Diagram](network-diagram-troubleshooting.md)

## Use the Network Diagram to View Connections<a name="network-diagram-what-is"></a>

Using network connectivity data from Application Discovery Service, the network diagram in Migration Hub reduces the time it takes to plan your migration by helping you quickly determine which of your servers are included in an application\. 

Server connections are visually mapped for you in the network diagram, which you can modify to organize your server inventory into groups for application migration\.

The network diagram provides the following capabilities:
+ Viewing detailed server information discovered by Application Discovery Service\. 
+ Viewing server dependency information\. 
+ Viewing detailed network connection information between servers\. 
+ Applying filters to narrow the search for specific servers\.
+ Validating existing application groups\.
+ Exporting application information for use in migration planning\.