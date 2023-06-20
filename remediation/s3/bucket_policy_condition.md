**From Console**

1. Login to AWS Management Console and open the Amazon S3 console using [https://console.aws.amazon.com/s3](https://console.aws.amazon.com/s3)
2. Select click on a bucket.
3. Click on `Permissions`.
4. Click `Bucket Policy`.
5. Manually check whether the Condition configuration content in the policy has security risks, such as whether there are similar policies below, if so, it is recommended to change to a more secure method such as a whitelist.

```json
"Condition": {
  "StringLike": {
    "aws:UserAgent": "<string>"
  }
}
```

6. Save
7. Repeat for all the buckets in your AWS account that contain sensitive data.

**From Command Line**

1. Export the bucket policy to a json file.

```bash
aws s3api get-bucket-policy --bucket <bucket_name> --query Policy --output text > policy.json
```

2. Manually check whether the Condition configuration content in policy.json has security risks, such as whether there are similar policies below, if so, it is recommended to change to a more secure method such as a whitelist.

```json
"Condition": {
  "StringLike": {
    "aws:UserAgent": "<string>"
  }
}
```

3. Apply this modified policy back to the S3 bucket:

```bash
aws s3api put-bucket-policy --bucket <bucket_name> --policy file://policy.json
```
