# Getting started with AWS CLI 

## Day 19 Checklist

- [ ] Get to know AWS CLI
- [ ] Install AWS CLI tool
- [ ] Create a new IAM user to work with AWS CLI
- [ ] Configure AWS CLI
- [ ] Using AWS CLI with S3 Buckets


## AWS CLI

- AWS CLI, or the Amazon Web Services Command Line Interface, is a command-line tool for interacting with AWS services. 
- It provides a way to automate AWS services and simplify the management of your AWS resources. 
- The AWS Command Line Interface (AWS CLI) is an open source tool that enables you to interact with AWS services using commands in your command-line shell. 
- With minimal configuration, the AWS CLI enables you to start running commands that implement functionality equivalent to that provided by the browser-based AWS Management Console from the command prompt in your terminal program:

- Linux shells – Use common shell programs such as bash, zsh, and tcsh to run commands in Linux or macOS.
- Windows command line – On Windows, run commands at the Windows command prompt or in PowerShell.
- Remotely – Run commands on Amazon Elastic Compute Cloud (Amazon EC2) instances through a remote terminal program such as PuTTY or SSH, or with AWS Systems Manager.
- The AWS CLI allows you to manage resources from your terminal or command prompt without the need for a graphical user interface.
- The AWS CLI can be used to manage a wide range of AWS services, including Amazon S3, EC2, Lambda, CloudFormation, and more. In this tutorial, we will focus on the use of AWS CLI with S3 buckets.


## Install AWS CLI

If you haven't already, you will need to install the AWS CLI on your local machine. You can do this by following the instructions in the AWS CLI documentation. Once installed, you can run the aws command in your terminal to verify that it is installed correctly.

Some important links

- [AWS CLI homepage](https://aws.amazon.com/cli/)
- [Installing AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

### Linux

To Install for linux:

```bash
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

### Windows

Download and run the AWS CLI MSI installer for Windows (64-bit): [AWS CLI for windows](https://awscli.amazonaws.com/AWSCLIV2.msi)

```powershell
C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi

C:\> aws --version
aws-cli/2.10.0 Python/3.11.2 Windows/10 exe/AMD64 prompt/off
```

### Mac

```bash

curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
$ sudo installer -pkg AWSCLIV2.pkg -target /

```

## Configure AWS CLI

After installing the AWS CLI, you will need to configure it with your AWS access keys. You can do this by running the aws configure command in your terminal. You will be prompted to enter your AWS access key ID, secret access key, default region, and default output format.

```bash
$ aws configure
AWS Access Key ID [None]: your_access_key_id
AWS Secret Access Key [None]: your_secret_access_key
Default region name [None]: us-west-2
Default output format [None]: json
```

## S3 and S3API

- The AWS CLI provides two distinct commands for interacting with Amazon S3: `s3` and `s3api`. - While both commands are used to interact with Amazon S3, they have some differences in functionality and usage.

Here are some of the key differences between s3 and s3api:
| S3                                                                                                                             | S3API                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Interacts with Amazon S3 using a high-level API                                                                                | Interacts with Amazon S3 using a low-level API                                                                                                                                                                                  |
| Supports file and folder-level operations                                                                                      | Supports individual operation-level requests                                                                                                                                                                                    |
| Provides high-level commands such as cp, sync, ls, mv, rm, mb, rb, website, and presign                                   | Provides low-level commands for each Amazon S3 API call                                                                                                                                                                         |
| Uses S3-specific parameters for commands                                                                                       | Uses AWS CLI parameters, and HTTP status codes returned from Amazon S3 for any error codes                                                                                                                                       |
| Automatically performs multipart uploads and parallel transfers for large files                                               | Requires manual specification of each multipart upload request, and does not automatically perform parallel transfers for large files                                                                                           |
| Supports simple management of Amazon S3 objects, Amazon S3 buckets, and AWS Identity and Access Management (IAM) policies | Supports complex management of Amazon S3 objects, Amazon S3 buckets, and AWS Identity and Access Management (IAM) policies.                                                                                                   |
| Provides Amazon S3-specific features such as encryption, transfer acceleration, versioning, lifecycle policies, and access logging | Provides the ability to make individual Amazon S3 API calls, with support for authentication, and provides control over Amazon S3-specific features such as encryption, transfer acceleration, versioning, lifecycle policies, and access logging. |
| Provides support for AWS CloudFormation                                                                                         | Does not provide support for AWS CloudFormation                                                                                                                                                                                 |

## S3 Command reference

- List S3 Buckets - `aws s3 ls`
- Create a bucket - `aws s3 mb s3://my-new-s3-bucket`
- Upload file to S3 bucket - `aws s3 cp my_file.txt s3://my-s3-bucket-1/`
- Download a file - `aws s3 cp s3://my-s3-bucket-1/ . --recursive`
- Delete a file - `aws s3 rm s3://my-s3-bucket-1/my_file.txt`
- Sync a folder - `aws s3 sync /path/to/local/directory s3://mybucket/directory`
- Use s3api - `aws s3api list-buckets`
