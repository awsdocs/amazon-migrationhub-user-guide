# Prerequisites for using the network diagram in Migration Hub<a name="network-diagram-prerequisites"></a>

The following are the prerequisites for using the network diagram in AWS Migration Hub:
+  AWS Application Discovery Service Discovery Agent must be running on all of the on\-premises servers that you want mapped in the diagram\. For more information, see [Setting up Agent Based Discovery](https://docs.aws.amazon.com/application-discovery/latest/userguide/setting-up-agents.html) in the *Application Discovery Service User Guide*\.
+ AWS recommends that server and network connection data be collected for two to six weeks to capture important connection patterns, such as month\-end or year\-end business cycles\.
+ To grant access to the network diagram when creating an identity\-based policy that allows or denies access to AWS Application Discovery Service or Migration Hub, you might need to add the `discovery:GetNetworkConnectionGraph` action to the policy\. For more information, see [Granting permissions to use the network diagram](https://docs.aws.amazon.com/application-discovery/latest/userguide/security_iam_id-based-policy-examples.html#security_iam_id-based-policy-examples-network-connection-graph) in the *Application Discovery Service User Guide*\.

The network diagram has the following limits:
+ Currently, data ingestion stops after 180 days\.
+ The network diagram can visualize up to 1,500 server nodes\.