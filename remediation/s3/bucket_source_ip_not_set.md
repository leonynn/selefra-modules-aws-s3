**From Console**

1. Login to AWS Management Console and open the Amazon S3 console using [https://console.aws.amazon.com/s3](https://console.aws.amazon.com/s3)
2. Select click on a bucket.
3. Click on `Permissions`.
4. Click `Bucket Policy`.
5. Add this to the existing policy filling in the required information.

```json
{
  "Sid": "<optional>",
  "Action": "s3:*",
  "Effect": "Allow",
  "Principal": "*",
  "Resource": "arn:aws:s3:::<bucket_name>/*",
  "Condition": {
    "IpAddress": {
      "aws:SourceIp": "<ip_address>"
    }
  }
}
```

6. Save
7. Repeat for all the buckets in your AWS account that contain sensitive data.

**From Console (using AWS Policy Generator)**

using AWS Policy Generator:

1. Repeat steps 1-4 above.
2. Click on Policy Generator at the bottom of the Bucket Policy Editor.
3. Select Policy Type S3 Bucket Policy.
4. Add Statements.

```text
Effect = Deny
Principal = *
AWS Service = Amazon S3
Actions = s3:*
Amazon Resource Name = arn:aws:s3:::<bucket_name>/*
```

5. Add Conditions.

```text
Condition = IpAddress
Key = aws:SourceIp
Value = <ip_address>
```

6. Generate Policy.
7. Copy the text and add it to the Bucket Policy.

**From Command Line**

1. Export the bucket policy to a json file.

```bash
aws s3api get-bucket-policy --bucket <bucket_name> --query Policy --output text > policy.json
```

2. Modify the policy.json file by adding in this statement:

```json
{
  "Sid": "<optional>",
  "Action": "s3:*",
  "Effect": "Allow",
  "Principal": "*",
  "Resource": "arn:aws:s3:::<bucket_name>/*",
  "Condition": {
    "IpAddress": {
      "aws:SourceIp": "<ip_address>"
    }
  }
}
```

3. Apply this modified policy back to the S3 bucket:

```bash
aws s3api put-bucket-policy --bucket <bucket_name> --policy file://policy.json
```
