To remediate this issue, update your S3 bucket to enable default encryption.

**To enable default encryption on an S3 bucket**

1. Open the Amazon S3 console at [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/).
2. In the left navigation pane, choose **Buckets**.
3. Choose the S3 bucket from the list.
4. Choose **Properties**.
5. Choose **Default encryption**.
6. For the encryption, choose either **AES-256** or **AWS-KMS**.

   - Choose **AES-256** to use keys that are managed by Amazon S3 for default encryption. For more information about using Amazon S3 server-side encryption to encrypt your data, See the [*Amazon Simple Storage Service User Guide*](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingServerSideEncryption.html).

   - Choose **AWS-KMS** to use keys that are managed by AWS KMS for default encryption. Then choose a root key from the list of the AWS KMS root keys that you have created.

     Type the Amazon Resource Name (ARN) of the AWS KMS key to use. You can find the ARN for your AWS KMS key in the IAM console, under **Encryption keys**. Or, you can choose a key name from the drop-down list.

     **Important**

     If you use the AWS KMS option for your default encryption configuration, you are subject to the RPS (requests per second) quotas of AWS KMS. For more information about AWS KMS quotas and how to request a quota increase, See the [*AWS Key Management Service Developer Guide*](https://docs.aws.amazon.com/kms/latest/developerguide/limits.html).

     For more information about creating an AWS KMS key, See the [*AWS Key Management Service Developer Guide*](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html).

     For more information about using AWS KMS with Amazon S3, See the [*Amazon Simple Storage Service User Guide*](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingKMSEncryption.html).

   When enabling default encryption, you might need to update your bucket policy. For more information about moving from bucket policies to default encryption, See the [*Amazon Simple Storage Service User Guide*](https://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html#bucket-encryption-update-bucket-policy).

7. Choose **Save**.

For more information about default S3 bucket encryption, See the [*Amazon Simple Storage Service User Guide*](https://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html).
