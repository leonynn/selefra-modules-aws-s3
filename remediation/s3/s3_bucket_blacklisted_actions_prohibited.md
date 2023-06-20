To remediate this issue, edit the S3 bucket policy to remove the permissions.

**To edit an S3 bucket policy**

1. Open the Amazon S3 console at [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/).
2. In the `Bucket name` list, choose the name of the S3 bucket for which you want to edit the policy.
3. Choose `Permissions`, and then choose `Bucket Policy`.
4. In the `Bucket policy editor` text box, do one of the following:
   - Remove the statements that grant access to denied actions to other AWS accounts
   - Remove the permitted denied actions from the statements
5. Choose `Save`.

Reference document: [https://docs.aws.amazon.com/securityhub/latest/userguide/s3-controls.html#s3-6](https://docs.aws.amazon.com/securityhub/latest/userguide/s3-controls.html#s3-6)
