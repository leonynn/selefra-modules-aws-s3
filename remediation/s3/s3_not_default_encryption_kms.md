To enable default encryption with KMS keys for S3 buckets, follow these steps:

1. Navigate to the Amazon S3 console in the AWS Management Console.
2. Select the S3 bucket that you want to enable default encryption for.
3. In the Bucket settings list, click on "Properties."
4. Locate the "Default encryption" card and click "Edit."
5. Select the "AWS-KMS" option and choose the desired KMS key from the "KMS master key" drop-down list. You can use your account's default key or specify a custom KMS key.
6. Click "Save changes" to enable default encryption with the selected KMS key for the S3 bucket.

Please refer to the official AWS documentation for more details: [Setting bucket-level encryption](https://docs.aws.amazon.com/AmazonS3/latest/userguide/set-bucket-policy.html#bucket-encryption)
