# AWS Migration Hub User Guide

-----
*****Copyright &copy; 2018 Amazon Web Services, Inc. and/or its affiliates. All rights reserved.*****

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
+ [Setting Up](setting-up.md)
+ [Getting Started with AWS Migration Hub](getting-started.md)
   + [Perform Discovery and Then Migrate](gs-new-user-discovery.md)
   + [Migrate Without Performing Discovery](gs-new-user-migration.md)
+ [AWS Migration Hub Walkthroughs](walkthroughs.md)
   + [Option 1: Perform Discovery and Then Migrate](discovery-walkthroughs.md)
      + [Phase 1: Discover](discovery-wt-discover.md)
      + [Phase 2: Migrate](discovery-wt-migrate.md)
      + [Phase 3: Track](discovery-wt-track.md)
   + [Option 2: Migrate Without Performing Discovery](migrate-walkthroughs.md)
      + [Phase 1: Migrate](migrate-wt-migrate.md)
      + [Phase 2: Track](migrate-wt-track.md)
+ [Doing More in Migration Hub](doing-more.md)
+ [Authentication and Access Control for AWS Migration Hub](auth-and-access-control.md)
   + [AWS Migration Hub Roles and Policies](policy-templates.md)
      + [New User IAM Setup](new-customer-setup.md)
      + [Custom Policies for Migration Tools](customer-managed-vendor.md)
   + [AWS Migration Hub API Permissions: Actions and Resources Reference](migrationhub-api-permissions-ref.md)
   + [AWS Migration Hub Authentication and Access Control Explained](auth-and-access-explained.md)
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
      + [ListCreatedArtifacts](API_ListCreatedArtifacts.md)
      + [ListDiscoveredResources](API_ListDiscoveredResources.md)
      + [ListMigrationTasks](API_ListMigrationTasks.md)
      + [ListProgressUpdateStreams](API_ListProgressUpdateStreams.md)
      + [NotifyApplicationState](API_NotifyApplicationState.md)
      + [NotifyMigrationTaskState](API_NotifyMigrationTaskState.md)
      + [PutResourceAttributes](API_PutResourceAttributes.md)
   + [Data Types](API_Types.md)
      + [CreatedArtifact](API_CreatedArtifact.md)
      + [DiscoveredResource](API_DiscoveredResource.md)
      + [MigrationTask](API_MigrationTask.md)
      + [MigrationTaskSummary](API_MigrationTaskSummary.md)
      + [ProgressUpdateStreamSummary](API_ProgressUpdateStreamSummary.md)
      + [ResourceAttribute](API_ResourceAttribute.md)
      + [Task](API_Task.md)
+ [Logging Migration Hub API Calls with AWS CloudTrail](logging-using-cloudtrail.md)
+ [Document History](document-history.md)