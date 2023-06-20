**From Console**

1. Login to AWS Management Console and open the Amazon S3 console using [https://console.aws.amazon.com/s3](https://console.aws.amazon.com/s3)
2. Select click on a bucket.
3. Click on `Permissions` and find `Access control list (ACL)`.
4. Click the `Edit` button, uncheck the `List` object option box of `Everyone (public access)`, and save.
5. Repeat for all the buckets in your AWS account that contain sensitive data.

**From Command Line**

1. Export the bucket acl policy to a json file.

```bash
aws s3api get-bucket-acl --bucket <bucket_name> --output json > acl.json
```

2. Modify the acl.json file and remove the following from the acl.json file.

```json
{
  "Grantee": {
    "Type": "Group",
    "URI": "http://acs.amazonaws.com/groups/global/AllUsers"
  },
  "Permission": "WRITE_ACP"
}
```

   or

```json
{
  "Grantee": {
    "Type": "Group",
    "URI": "http://acs.amazonaws.com/groups/global/AllUsers"
  },
  "Permission": "FULL_CONTROL"
}
```

3. Apply this modified acl policy back to the S3 bucket.

```bash
aws s3api put-bucket-acl --bucket <bucket_name> --access-control-policy file://acl.json
```

4. Repeat for all the buckets in your AWS account that contain sensitive data.
