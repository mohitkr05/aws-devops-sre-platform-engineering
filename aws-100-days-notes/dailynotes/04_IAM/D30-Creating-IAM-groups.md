# Creating IAM Groups and adding users

- [ ] Create IAM groups using console
- [ ] Adding users to the groups
- [ ] Adding IAM groups using CLI 


## Amazon Resource Name

In AWS, an ARN (Amazon Resource Name)[^1] is a unique identifier for a resource, which is used to identify and access AWS resources across different AWS services and accounts. ARNs are similar to URNs (Uniform Resource Names) and URIs (Uniform Resource Identifiers) in other contexts.

An ARN is a string of characters that identifies a specific AWS resource, and follows a specific format:

`arn:partition:service:region:account-id:resource-id`
`arn:partition:service:region:account-id:resource-type/resource-id`


- partition – The partition that the resource is in (e.g. "aws" or "aws-cn" for China).
- service – The AWS service that the resource belongs to (e.g. "s3" or "ec2").
- region – The AWS region where the resource is located (e.g. "us-west-2" or "cn-north-1").
- account-id – The AWS account ID that owns the resource.
- resource-type - The resource type. For example, vpc for a virtual private cloud (VPC). 
- resource-id – The ID of the resource (e.g. an EC2 instance ID or an S3 bucket name).

Example ARN:

`arn:aws:s3:us-west-2:123456789012:my-bucket`

## Use Cases

ARNs are useful in many ways in AWS, including:

- IAM policies: ARNs can be used to specify the resource to which a policy applies. For example, you can use an ARN to specify an S3 bucket in an IAM policy.
- Resource-level permissions: ARNs can be used to specify the specific resource on which a user or role has permissions. For example, you can use an ARN to grant read access to a specific S3 bucket.
- Cross-account access: ARNs can be used to grant permissions to AWS resources across accounts. For example, you can use an ARN to grant access to an S3 bucket in one account from an EC2 instance in another account.
- Tagging: ARNs can be used to tag AWS resources for easier management and organization. For example, you can use an ARN to tag all resources belonging to a particular department or project.

## IAM ARNs

An IAM user in the account:

`arn:aws:iam::123456789012:user/JohnDoe`

Another user with a path reflecting an organization chart:

`arn:aws:iam::123456789012:user/division_abc/subdivision_xyz/JaneDoe`

An IAM user group:

`arn:aws:iam::123456789012:group/Developers`

An IAM user group with a path:

`arn:aws:iam::123456789012:group/division_abc/subdivision_xyz/product_A/Developers`

An IAM role:

`arn:aws:iam::123456789012:role/S3Access`

A service-linked role:

`arn:aws:iam::123456789012:role/aws-service-role/access-analyzer.amazonaws.com/AWSServiceRoleForAccessAnalyzer`


## References

[^1]: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference-arns.html
