# S3 Permissions

## Day 25 Checklist

- [ ] Sharing access to you data?
- [ ] Common use cases of data sharing in AWS
- [ ] Understanding ACLs and Bucket ownership
- [ ] How to use ACLs



## What are ACLs?

Access Control Lists (ACLs) in Amazon S3 are used to manage access to your S3 buckets and objects at a more granular level. ACLs allow you to define permissions for different AWS accounts and users, enabling you to control who can perform specific actions on your S3 resources.

- An ACL is a JSON-based resource policy that specifies the permissions for individual AWS accounts or predefined groups.
- ACLs can be applied at the bucket level or the object level within a bucket.
- Each ACL consists of a set of grants, where each grant represents a permission (e.g., read, write, delete) given to a specific AWS account or predefined group.
- By default, newly created S3 buckets have a private ACL, meaning only the bucket owner has access to the bucket and its objects.

### Grant types

S3 supports various grant types in ACLs, including the following:

- Bucket owner: The owner of Bucket
- Canonical User: Refers to an AWS account identified by its AWS access key ID and AWS secret access key.
- Amazon S3 Group: Represents predefined groups (e.g., "AllUsers" for public access, "AuthenticatedUsers" for all AWS accounts).


Each grant type can have different permissions assigned to it, such as read, write, read ACL, write ACL, etc.

## Understanding Bucket ownership

### Bucket owner enforced (default)

- ACLs are disabled, and the bucket owner automatically owns and has full control over every object in the bucket.The bucket uses policies exclusively to define access control.
- By default, ACLs are disabled.
- A majority of modern use cases in Amazon S3 no longer require the use of ACLs
- It is recommended that you keep ACLs disabled, except in unusual circumstances where you must control access for each object individually

### ACLs enabled

- Bucket owner preferred – The bucket owner owns and has full control over new objects that other accounts write to the bucket with the bucket-owner-full-control canned ACL.
- To require all Amazon S3 uploads to include the bucket-owner-full-control canned ACL, you can add a bucket policy that allows only object uploads that use this ACL.
- Object writer – The AWS account that uploads an object owns the object, has full control over it, and can grant other users access to it through ACLs.
- The default setting is Bucket owner enforced. To apply the default setting and keep ACLs disabled, only the s3:CreateBucket permission is needed. To enable ACLs, you must have the s3:PutBucketOwnershipControls permission.
- Under Block Public Access settings for this bucket, choose the Block Public Access settings that you want to apply to the bucket.
- By default, all four Block Public Access settings are enabled. We recommend that you keep all settings enabled, unless you know that you need to turn off one or more of them for your specific use case. For more information about blocking public access, see Blocking public access to your Amazon S3 storage.

| Setting | Applies to | Effect on object ownership | Effect on ACLs | Uploads accepted |
|---|---|---|---|---|
|Bucket owner enforced (default)|All new and existing objects|Bucket owner owns every object| ACLs are disabled and no longer affect access permissions to your bucket.Bucket owner has full ownership and control.|Uploads with bucket owner full control ACLs or uploads that don't specify an ACL |
| Bucket owner preferred | New objects | If an object upload includes the `bucket-owner-full-control` canned ACL, the bucket owner owns the object.  Objects uploaded with other ACLs are owned by the writing account. | ACLs can be updated and can grant permissions.If an object upload includes the `bucket-owner-full-control` canned ACL, the bucket owner has full control access, and the object writer no longer has full control access. | All uploads |
| Object writer | New objects | Object writer owns the object. |ACLs can be updated and can grant permissions.Object writer has full control access. | 	All uploads |


## Use cases

- Granting Access to Other AWS Accounts: You can use ACLs to share your S3 resources with other AWS accounts by specifying the account ID or email address in the grant.
- Public Read or Write Access: ACLs can be configured to allow public read or write access to objects, making them accessible to anyone without authentication.
- Fine-Grained Access Control: ACLs enable you to grant specific permissions to different entities, allowing for fine-grained access control.


## Using CLI

- Check the policy

`aws s3api get-bucket-acl --bucket your-bucket-name`

- Create a policy

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Only allow writes to my bucket with bucket owner full control",
            "Effect": "Allow",
            "Principal": {
                "AWS": [
                    "arn:aws:iam::652897695890:user/awscliuser"
                ]
            },
            "Action": [
                "s3:PutObject"
            ],
            "Resource": "arn:aws:s3:::100daysofaws/*",
            "Condition": {
                "StringEquals": {
                    "s3:x-amz-acl": "bucket-owner-full-control"
                }
            }
        }
    ]
}

```

- Apply a policy

`aws s3api put-bucket-policy --bucket 100daysofaws --policy file://acl.json`