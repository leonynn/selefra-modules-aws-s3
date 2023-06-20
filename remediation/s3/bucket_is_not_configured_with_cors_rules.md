**From Console**

1. Login to AWS Management Console and open the Amazon S3 console using [https://console.aws.amazon.com/s3](https://console.aws.amazon.com/s3).
2. Select click on a bucket.
3. Click on `Permissions` and find the `Cross-origin resource sharing (CORS)` funtion.
4. Click 'Edit' and enter CORS configuration information, then click 'Save changes'.
5. Repeat for other buckets that need to be modified.

**From Command Line**

1. Create and edit the cors.json file, for example:

```json
{
  "CORSRules": [
    {
      "AllowedOrigins": ["http://www.example.com"],
      "AllowedHeaders": ["*"],
      "AllowedMethods": ["PUT", "POST", "DELETE"],
      "MaxAgeSeconds": 3000,
      "ExposeHeaders": ["x-amz-server-side-encryption"]
    },
    {
      "AllowedOrigins": ["*"],
      "AllowedHeaders": ["Authorization"],
      "AllowedMethods": ["GET"],
      "MaxAgeSeconds": 3000
    }
  ]
}
```

2. Apply this file to the S3 bucket.

```bash
aws s3api put-bucket-cors --bucket <bucket_name> --cors-configuration file://cors.json
```

3. Repeat for other buckets that need to be modified.

References: [https://docs.aws.amazon.com/AmazonS3/latest/userguide/enabling-cors-examples.html](https://docs.aws.amazon.com/AmazonS3/latest/userguide/enabling-cors-examples.html)
