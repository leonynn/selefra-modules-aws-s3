To remediate this issue, update the permissions policy of the S3 bucket.

**To configure an S3 bucket to deny nonsecure transport**

1. Open the Amazon S3 console at [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/).
2. Navigate to the noncompliant bucket, then choose the bucket name.
3. Choose **Permissions**, and then choose **Bucket Policy**.
4. Add a similar policy statement to that in the policy below. Replace `awsexamplebucket` with the name of the bucket you are modifying.

```json
{
    "Id": "ExamplePolicy",
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowSSLRequestsOnly",
            "Action": "s3:*",
            "Effect": "Deny",
            "Resource": [
                "arn:aws:s3:::awsexamplebucket",
                "arn:aws:s3:::awsexamplebucket/*"
            ],
            "Condition": {
                "Bool": {
                    "aws:SecureTransport": "false"
                }
            },
          "Principal": "*"
        }
    ]
}
```

5. Choose **Save**.

For more information, See the knowledge center article [What S3 bucket policy should I use to comply with the AWS Config rule s3-bucket-ssl-requests-only?](http://aws.amazon.com/premiumsupport/knowledge-center/s3-bucket-policy-for-config-rule/).
