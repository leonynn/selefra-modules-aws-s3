**From Console**

1. Login to AWS Management Console and open the Amazon S3 console using [https://console.aws.amazon.com/s3](https://console.aws.amazon.com/s3).
2. Select click on a bucket.
3. Click on `Properties` and find the `Server access logging` funtion.
4. Set the `Target bucket` to another bucket to avoid the log being recorded in an infinite loop, then click `Save changes`.
5. Repeat for other buckets that need to be modified.

**From Command Line**

1. Create and edit the logging.json file and set the TargetBucket to another bucket to avoid the log being logged in an infinite loop.

```json
{
    "LoggingEnabled": {
        "TargetBucket": "<bucket_name>",
        "TargetPrefix": "<bucket_prefix>"
    }
}
```

2. Apply this file to the S3 bucket.

```bash
aws s3api put-bucket-logging --bucket <bucket_name> --bucket-logging-status file://logging.json
```

3. Repeat for other buckets that need to be modified.

References: [https://docs.aws.amazon.com/AmazonS3/latest/userguide/enable-server-access-logging.html](https://docs.aws.amazon.com/AmazonS3/latest/userguide/enable-server-access-logging.html)
