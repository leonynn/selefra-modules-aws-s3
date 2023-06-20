To fix the non-compliance issue, create an S3 recovery point for the affected S3 buckets at least once a month, following the guidelines provided in the official AWS documentation. Here's a step-by-step recommendation on how to enable cross-region replication, which creates a copy of every new S3 object in a destination bucket:

1. Sign in to the [Amazon S3 console](https://console.aws.amazon.com/s3/).
2. Select the *source* bucket for which you want to create recovery points.
3. Choose the **Management** tab and then click on **Add replication rule**.
4. Specify the *destination* bucket where the objects will be replicated.
5. Set up the proper IAM roles for replication, following the instructions provided in the dialog.
6. (Optional) Customize the rule by choosing a specific object prefix or specifying object tagging requirements for determining which objects should be replicated.
7. Click on **Save** to confirm the changes.

Please refer to the [official documentation on Cross-Region Replication](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html) for more detailed instructions.

If your goal is to create versioning-enabled backup points at regular intervals, consider using AWS Backup service, which supports Amazon S3. Follow these steps:

1. Navigate to the [AWS Backup console](https://console.aws.amazon.com/backup/).
2. Click **Create backup plan** and either create a new plan or use an existing template.
3. Configure the backup plan's schedule, retention settings, and other options as needed.
4. Add Amazon S3 as a resource type and assign tags or use resource assignments to select the appropriate S3 buckets for the backup.
5. Click **Create plan** to save the configuration and start creating backups according to the plan's rules.

For more detailed instructions, refer to the [official documentation on creating an AWS Backup plan](https://docs.aws.amazon.com/aws-backup/latest/devguide/creating-a-backup-plan.html).
