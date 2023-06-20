Perform the steps below to enable MFA delete on an S3 bucket.

**Note:**

- You cannot enable MFA Delete using the AWS Management Console. You must use the AWS CLI or API.
- You must use your 'root' account to enable MFA Delete on S3 buckets.

**From Command Line**

1. Run the s3api put-bucket-versioning command.

```bash
aws s3api put-bucket-versioning --profile my-root-profile --bucket Bucket_Name --versioning-configuration Status=Enabled,MFADelete=Enabled --mfa "arn:aws:iam::aws_account_id:mfa/root-account-mfa-device passcode"
```
