# AWS Migration Hub User Guide

-----
*****Copyright &copy; Amazon Web Services, Inc. and/or its affiliates. All rights reserved.*****

-----
Amazon's trademarks and trade dress may not be used in
connection with any product or service that is not Amazon's,
in any manner that is likely to cause confusion among customers,
or in any manner that disparages or discredits Amazon. All other
trademarks not owned by Amazon are the property of their respective
owners, who may or may not be affiliated with, connected to, or
sponsored by Amazon.

-----
## Contents
+ [What Is AWS Migration Hub?](whatishub.md)
+ [Setting up](setting-up.md)
+ [Getting started with AWS Migration Hub](getting-started.md)
   + [Discovering on-premises resources using AWS discovery tools](gs-new-user-discovery.md)
   + [Migrate to AWS using Migration Hub migration tools and tracking](gs-new-user-migration.md)
      + [Migrate using Migration Hub migration tools](migrate-wt-migrate.md)
      + [Track the status of your migrations in Migration Hub](migrate-wt-track.md)
   + [Strategy Recommendations](gs-strategy-reccommendations.md)
   + [Refactor Spaces](gs-refactor-spaces.md)
   + [Migration Hub Orchestrator](gs-orchestrator.md)
+ [Migration Hub tracking, tagging, and console navigation tips](doing-more.md)
+ [Migration Hub home Region](home-region.md)
+ [Amazon EC2 instance recommendations](ec2-recommendations.md)
+ [Viewing network connections in Migration Hub](network-diagram.md)
   + [Prerequisites for using the network diagram in Migration Hub](network-diagram-prerequisites.md)
   + [How to use the network diagram in Migration Hub](network-diagram-how-to.md)
   + [Troubleshooting the network diagram](network-diagram-troubleshooting.md)
+ [Security in AWS Migration Hub](security.md)
   + [Identity and access management in Migration Hub](auth-and-access-control.md)
      + [AWS Migration Hub roles and policies](policy-templates.md)
         + [New user IAM setup](new-customer-setup.md)
         + [Custom Policies for Migration Tools](customer-managed-vendor.md)
      + [AWS Migration Hub API Permissions: Actions and Resources Reference](migrationhub-api-permissions-ref.md)
      + [AWS Migration Hub Authentication and Access Control Explained](auth-and-access-explained.md)
      + [Using Service-Linked Roles for Migration Hub](using-service-linked-roles.md)
         + [Using Roles to Connect Migration Hub to Application Discovery Service](using-service-linked-roles-discovery-service-role.md)
         + [Using Roles to Connect Migration Hub to AWS DMS](using-service-linked-roles-dms-service-role.md)
   + [Logging and monitoring in AWS Migration Hub](logging-monitoring.md)
+ [AWS Migration Hub quotas](limits.md)
+ [Troubleshooting AWS Migration Hub](troubleshooting.md)
+ [AWS Migration Hub API](api-reference.md)
   + [Actions](API_Operations.md)
      + [AssociateCreatedArtifact](API_AssociateCreatedArtifact.md)
      + [AssociateDiscoveredResource](API_AssociateDiscoveredResource.md)
      + [CreateProgressUpdateStream](API_CreateProgressUpdateStream.md)
      + [DeleteProgressUpdateStream](API_DeleteProgressUpdateStream.md)
      + [DescribeApplicationState](API_DescribeApplicationState.md)
      + [DescribeMigrationTask](API_DescribeMigrationTask.md)
      + [DisassociateCreatedArtifact](API_DisassociateCreatedArtifact.md)
      + [DisassociateDiscoveredResource](API_DisassociateDiscoveredResource.md)
      + [ImportMigrationTask](API_ImportMigrationTask.md)
      + [ListApplicationStates](API_ListApplicationStates.md)
      + [ListCreatedArtifacts](API_ListCreatedArtifacts.md)
      + [ListDiscoveredResources](API_ListDiscoveredResources.md)
      + [ListMigrationTasks](API_ListMigrationTasks.md)
      + [ListProgressUpdateStreams](API_ListProgressUpdateStreams.md)
      + [NotifyApplicationState](API_NotifyApplicationState.md)
      + [NotifyMigrationTaskState](API_NotifyMigrationTaskState.md)
      + [PutResourceAttributes](API_PutResourceAttributes.md)
   + [Data Types](API_Types.md)
      + [ApplicationState](API_ApplicationState.md)
      + [CreatedArtifact](API_CreatedArtifact.md)
      + [DiscoveredResource](API_DiscoveredResource.md)
      + [MigrationTask](API_MigrationTask.md)
      + [MigrationTaskSummary](API_MigrationTaskSummary.md)
      + [ProgressUpdateStreamSummary](API_ProgressUpdateStreamSummary.md)
      + [ResourceAttribute](API_ResourceAttribute.md)
      + [Task](API_Task.md)
+ [Logging Migration Hub API calls with AWS CloudTrail](logging-using-cloudtrail.md)
+ [Document history](document-history.md)