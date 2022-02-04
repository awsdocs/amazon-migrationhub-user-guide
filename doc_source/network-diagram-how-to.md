# How to use the network diagram in Migration Hub<a name="network-diagram-how-to"></a>

This section describes how to use the network diagram in Migration Hub\.

**To use the network diagram**

1. In the navigation pane, under **Discover**, choose **Servers**\. 

1. To view details about the server, choose the hostname of the server from the **Server info** column\. The server's detail page displays information about the server, such as hostname, IP address, performance metrics, and so on\.

1. Choose **Network**\. The icon for the server you choose is centered in the network diagram\. Connections fan out from the center server to servers that are directly connected to the server you choose\.

The network diagram console is divided into three panes: toolbar, diagram, and the server detail/selected server list pane\.

The following topics describe the network diagram console panes\.

**Topics**
+ [Toolbar](#network-diagram-toolbar)
+ [Diagram](#network-diagram-pane)
+ [Server details and selected server list](#network-diagram-server-details)

## Toolbar<a name="network-diagram-toolbar"></a>

Choosing an icon on the toolbar performs an action or opens a pane with more choices\. Only one of these panes can be open at any one time\. 

The toolbar icons are described in the following table\.


| Icon | Name | Description | 
| --- | --- | --- | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/settings.png)  |  Settings  |  To change your settings, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/settings.png)\.  | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/filter.png)  |  Filters  |  To filter server connections, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/filter.png) and then clear the check box next to each port number that you do not want to display connections for\.  | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/zoom_in.png)  |  Zoom in  |  To zoom in on the diagram, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/zoom_in.png)\.  | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/zoom_out.png)  |  Zoom out  |  To zoom out, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/zoom_out.png)\.  | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/zoom-to-fit-icon.png)  |  Zoom to fit  |  To zoom to fit the entire diagram in the current view, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/zoom-to-fit-icon.png)\.  | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/full-view-icon.png)  |  View full screen  |  To view the diagram full screen, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/full-view-icon.png)\.   | 

## Diagram<a name="network-diagram-pane"></a>

This section describes the icons used in the diagram to show network server nodes and how to interact with the diagram\.
+ [Diagram Icons](#network-diagram-icons)
+ [Adding a server to a diagram](#network-diagram-add-server)
+ [Interacting with the diagram](#network-diagram-controls)

### Diagram Icons<a name="network-diagram-icons"></a>

The icons used in the diagram are shown in the following table\.


| Icon | Name | Description | 
| --- | --- | --- | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-icon.png)  |  Server  |  Represents a server that is running a discovery agent that is part of your network\. To view details about a server, right\-click ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-icon.png) and then choose **View server details**\. To select a server for a group application, right\-click ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-icon.png) and then choose **Select Server**\.  | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-selected-icon.png)  |  Selected Server  |  Represents a server that you selected for group application\.  To deselect a server, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-selected-icon.png) and then choose **Unselect server** in the server details pane\. To select a server for a group application, right\-click ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-selected-icon.png) and then choose **Select Server**\.  | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-app-label-icon.png)  |  Server with application label  |  Represents a server that belongs to a group application\. The name of the application is displayed under the server icon\. The names of all the applications the server belongs to are displayed\.    | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-no-agent-icon.png)  |  Server without agent  |  Represents a server in your network that doesn't have Discovery Agent installed\. To view details about the server, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/server-no-agent-icon.png)\.  | 
|  ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/node-expand-icon.png) ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/node-contract-icon.png)  |  Plus sign on upper right corner of server icon Minus sign on upper right corner of server icon  |  Represents that the server has servers connected to it that aren't shown in the diagram\. To expand the network from the server node, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/node-expand-icon.png) on the server icon\. To collapse the network back to the server node, choose ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/migrationhub/latest/ug/images/node-contract-icon.png) on the server icon\.  | 

### Adding a server to a diagram<a name="network-diagram-add-server"></a>

You can search for servers to add to the diagram by searching by hostname or by IP address\. You'll get results after adding your search criteria and pressing **Enter**\. 

**To search for servers to add to the network diagram**

1. Choose the search icon on the toolbar, and then choose **Hostname** or **IP address**\.

1. Type the criteria for your search in the search box\. 

   For example, to search for servers that contain **IAM** in their hostname, enter **IAM**\. Or, enter **0\.0\.0\.** to search for servers that contain **0\.0\.0\. ** in their IP address\.

1. From the result, select the servers to add to the diagram, and then choose **\+** to add them to the diagram\. 

### Interacting with the diagram<a name="network-diagram-controls"></a>

You can interact with the diagram in the following ways:
+ To pan around, choose and drag on empty areas in the diagram\.
+ To zoom in and out, scroll up and down, respectively\.
+ To highlight all the connections to and from a server on the diagram, hover over a server icon\.
+ To see a server's details in the server detail pane, choose a server icon\.
  + Inbound ports only shows ports that are being opened on the server\.
  + Outbound ports aren't displayed\.
  + Hovering over a port highlights all the connections that open that port on the diagram\.
+ Hold shift and choose servers to select them for grouping applications or other actions\.

## Server details and selected server list<a name="network-diagram-server-details"></a>

Server details and the list of selected servers share the pane right of the diagram\. You can toggle back and forth between the server details view and the selected server list view by choosing the server icon\.

To see details about a server on the diagram, choose the server icon\. Details about the server display in the pane to the right of the diagram\.

You can use the following options to select servers from the network diagram:
+ On the network diagram, choose a server node icon\. Details about the server show in the server details pane, where you choose **Select server**\.
+ On the network diagram, open the context \(right\-click\) menu on the server node icon, and then choose **Select server** from the dropdown list\.
+ Choose **Select all** to select all the servers for grouping that are in your diagram\. Only the servers with the Discovery Agent running on them are selected\.
+ Hold **shift** to select multiple servers at the same time\.

Selected servers are shown in a list in the same pane as the server details\. You can toggle back and forth between the server details view and the selected server list view by choosing the server icon\. 

After you select one or more servers, you can create an application, or add to an existing one, by choosing **Group as application**\. You can add a descriptive tag to the selected servers by choosing **Add tag** from the **Actions ** menu\. Doing so shows a dialog box where you can type a value for **Key**, and optionally a value for **Value**\. For more information, see [Step 3: Group servers as applicationsStep 3: Group servers](gs-new-user-discovery.md#gs-discovery-group-as-applications)\.