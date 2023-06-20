**From Console**

1. Login to AWS Management Console and open the Amazon S3 console using [https://console.aws.amazon.com/s3](https://console.aws.amazon.com/s3).
2. Select click on a bucket.
3. Click on `Properties` and find the `Bucket Versioning` funtion.
4. Click the `Edit` button, check the `Enable` box, and then click `Save changes`.
5. Repeat for other buckets that need to be modified.

**From Command Line**

1. Use the command line to turn on bucket versioning for the Bucket to be modified.

```bash
aws s3api put-bucket-versioning --bucket <bucket_name> --versioning-configuration Status=Enabled
```

2. Repeat for other buckets that need to be modified.

References: [https://docs.aws.amazon.com/AmazonS3/latest/userguide/manage-versioning-examples.html](https://docs.aws.amazon.com/AmazonS3/latest/userguide/manage-versioning-examples.html)
