To fix this issue and ensure your S3 Buckets have 'Block public access' enabled, follow these steps from the official AWS documentation:

1. Sign in to the AWS Management Console and open the [Amazon S3 console](https://console.aws.amazon.com/s3/).
2. In the **Buckets** list, choose the name of the bucket you want to update.
3. Choose the **Permissions** tab, and then choose **Block public access (bucket settings)**.
4. To turn on Block Public Access settings, choose **Edit**.
5. Select the checkboxes next to the settings you want to enable (e.g., 'Block all public access' or any combination of the individual settings).
6. Choose **Save changes**. You'll be prompted to confirm the changes by typing 'confirm' and then clicking **Confirm**.

Make sure to review your bucket policies and access control lists (ACLs) to ensure you are not unintentionally allowing public access. You can also refer to the official *[Using Amazon S3 Block Public Access](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html)* documentation for additional information on managing public access to your S3 buckets.
