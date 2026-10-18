# IAM 

- [ ] Understand what is IAM?
- [ ] Why IAM is essential
- [ ] What are the key parts of IAM?
- [ ] Understanding how to setup an organization


## WHat is IAM?

- Identity and Access Management is the service which
   - Authenticates the person - Who the person/entity is?
   - Authorizes the person - What the person/entity can do?
- IAM consists of processes, policies, and systems that manage the users’ digital identities in a secure, streamlined manner.
- Authentication is the process of signing in to AWS using your identity credentials.


## What is AWS IAM service?

- AWS Identity and Access Management (IAM) is a web service for securely controlling access to AWS resources.
- IAM allows central management of permissions to control user access to AWS resources.
- IAM controls the authentication (sign-in) and authorization (permissions) of users to access resources.
- AWS account root user is the initial sign-in identity with complete access to all AWS services and resources in the account.
- It is recommended to not use the root user for everyday tasks and instead, safeguard the root user credentials and use them only for tasks that require the root user's permissions.
- IAM features include shared access to the AWS account, granular permissions, secure access to AWS resources for applications running on EC2 instances, multi-factor authentication (MFA), identity federation, and identity information for assurance.
- IAM supports the processing, storage, and transmission of credit card data and has been validated as being compliant with Payment Card Industry (PCI) Data Security Standard (DSS).
- IAM is eventually consistent, and the changes may take some time to propagate across IAM, which should be considered when making changes to IAM resources.
- AWS Identity and Access Management (IAM) and AWS Security Token Service (AWS STS) are available features of an AWS account at no additional cost. However, charges apply only when accessing other AWS services using IAM users or AWS STS temporary security credentials


## IAM resources

- *Users*: IAM allows you to create and manage users, which are individual people or applications that need access to AWS resources. Each user can be assigned a set of permissions that determine what actions they can perform on AWS resources.
- *Groups*: Users can be organized into groups to make it easier to manage permissions. You can assign permissions to a group, and all users in that group inherit those permissions
- *Roles*: Roles are a way to grant permissions to AWS services, rather than individual users or groups. You can create roles with specific permissions, and then assign those roles to AWS services or to users or groups that need to assume those roles.
- *Policies*: Policies are the mechanism used to define permissions in IAM. Policies are documents that specify what actions are allowed or denied for a user, group, or role.
- *Access Keys*: IAM allows you to generate access keys for users or applications that need programmatic access to AWS resources. Access keys consist of an access key ID and a secret access key, which are used to sign requests to AWS services 
- *Multi-factor authentication (MFA)*: IAM supports MFA, which is an additional layer of security that requires users to provide a second form of authentication, such as a security token or a text message code, in addition to their password 
- *Integration with AWS services*: IAM integrates with many AWS services, including EC2, S3, and RDS. This allows you to control access to those services using IAM policies.
- *Audit logs*: IAM provides detailed audit logs that allow you to track changes to IAM resources, such as users, groups, roles, and policies.
- *Compliance*: IAM is designed to help you meet various compliance requirements, such as PCI DSS and HIPAA, by providing features such as MFA and fine-grained access control

## What can be done with IAM?

- Users – Create individual users.
- Groups – Manage permissions with groups.
- Permissions – Grant least privilege.
- Auditing – Turn on AWS CloudTrail.
- Password – Configure a strong password policy.
- MFA – Enable MFA for privileged users.
- Roles – Use IAM roles for Amazon EC2 instances.
- Sharing – Use IAM roles to share access.
- Rotate – Rotate security credentials regularly.
- Conditions – Restrict privileged access further with conditions.

## IAM Best practices

- Lock away your AWS Account Root User access keys
- Do not create access keys for the root account
- User Email Address , Password & MFA to login to your root account 
- Do not share credentials of root account with anyone
- Create individual IAM users
- Don't use your AWS account root user credentials to access AWS, and don't give your credentials to anyone else. 
- Instead, create individual users for anyone who needs access to your AWS account. 
- Use groups to assign permissions to IAM users
- Grant least privilege
- When you create IAM policies, follow the standard security advice of granting least privilege, or granting only the permissions required to perform a task. 
- Determine what users (and roles) need to do and then craft policies that allow them to perform only those tasks. 
- To improve the security of your AWS account, you should regularly review and monitor each of your IAM policies. 
- Configure a strong password policy for your users
- Enable MFA
- Use roles for applications that run on Amazon EC2 instances
- Use roles to delegate permissions
- Do not share access keys
- Rotate credentials regularly
- Remove unnecessary credentials
- Use policy conditions for extra security
- Monitor activity in your AWS account 


## How you can access AWS?

- Ways to access AWS 
  - AWS account root user
  - an IAM user
  - assuming an IAM role
  - federated identity 
    - using credentials provided through an identity source, such as your company's single sign-on authentication or Google or Facebook credentials.
    - To sign in as a federated identity, your administrator must set up identity federation using IAM roles.
    - Depending on the type of user you are, you can sign in to the AWS Management Console or the AWS access portal.
-

## ABAC

- Attribute-based access control (ABAC) is a method of controlling access to resources based on attributes associated with the entity requesting access, the resource being accessed, and the environment in which the access request is made.
- In the context of AWS Identity and Access Management (IAM), ABAC is implemented using *IAM policies*, which are a set of rules that determine what actions can be performed on which resources. 
-IAM policies use attributes to evaluate access requests, and determine whether to allow or deny access.
- The attributes used in ABAC can include anything from user identity and group membership to geographic location and device type. They can also include custom attributes that you define yourself. IAM policies can be very specific, allowing you to control access to individual resources or groups of resources, and can be used in combination with other AWS services, such as Amazon S3 and Amazon EC2.
- ABAC in IAM allows you to create policies that are flexible and scalable, and can be tailored to meet the specific needs of your organization. You can use ABAC to manage access to AWS resources based on business requirements, compliance regulations, and other factors.
- One of the benefits of ABAC is that it allows you to define policies based on multiple attributes, giving you more fine-grained control over access to resources. For example, you might create a policy that allows access to a specific S3 bucket only if the user requesting access is located in a specific geographic region and is using a specific device.
- To implement ABAC in IAM, you can create policies that define attributes for users, groups, roles, and resources. These policies can then be used to control access to resources across your organization. You can also use IAM to manage policies for third-party applications that require access to AWS resources.
