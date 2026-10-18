# S3 Access logs

## Day 23 Checklist

- [ ] Understand S3 access logs
- [ ] Use cases of S3 access logs
- [ ] How to enable S3 access logs
- [ ] S3 access logs explained

## What is S3 Access logs?

- S3 access logs is a feature that enable the capturing and recording of detailed information about requests made to your S3 bucket. 
- When enabled, S3 access logs generate log files that contain valuable data about who accessed your bucket, when the access occurred, and from where the requests originated.


## What type of information is captured?

The access logs provide a wealth of information, including the following key details:

- Request Information
  - details about the requests made to your bucket
  - request type (e.g., GET, PUT, DELETE)
  - the requested object
  - HTTP status code of the response
  
- Requester Identity
  - which can be an AWS account
  - an IAM user
  - or an anonymous user.

- Source IP Address
  - S3 access logs record the source IP address of the requester
  - allowing you to identify the geographical location or network from which the requests originated. 
  - This information is valuable for security monitoring and identifying potential threats or unauthorized access attempts.

- Timestamps
  - Each log entry includes a timestamp that indicates when the request was made. 
  - This allows you to track the timing of requests and detect any unusual patterns or spikes in activity.

## Enabling S3 access logs provides several benefits

- Security Monitoring: By analyzing the access logs, you can identify and investigate any suspicious or unauthorized activities in your S3 bucket. Unusual access patterns, unexpected IP addresses, or excessive request frequencies can be indications of security breaches or unauthorized access attempts.
- Compliance and Audit Trails: S3 access logs serve as an audit trail for compliance purposes and security audits. They provide a detailed record of all bucket activity, helping you meet regulatory requirements and demonstrate adherence to security best practices.
- Troubleshooting and Debugging: Access logs are useful for troubleshooting and diagnosing issues related to access permissions, connectivity, or application errors. You can review the logs to identify the source of errors or investigate access-related problems.
- Usage Analysis: The access logs provide insights into the usage patterns of your S3 bucket. By analyzing the logs, you can track the number of requests, data transfer sizes, and popular objects. This information helps optimize storage costs, identify trends, and make informed decisions about data management.

## Enable bucket logging

`aws s3api put-bucket-logging --bucket <bucket-name> --logging-configuration '{"LoggingEnabled":{"TargetBucket":"<target-bucket>","LogFilePrefix":"logs/"}}'`

`aws s3api put-bucket-logging --bucket <bucket-name> --logging-configuration '{"LoggingEnabled":{"TargetBucket":"<target-bucket>","LogFilePrefix":"logs/","ServerSideEncryption":"AES256"}}'`


## Sample log


```csv
41eb12da481d20bbdaf7970a20e1c478afb9f4a80c5e0a54199c31e7dc66300f,bucketname,[17/May/2023:06:56:38 +0000],2.2.2.2,arn:aws:iam::1111111:user/testusers, RF118FR0TSH39F6D, REST.GET.TAGGING,  - "GET /bucketname?tagging= HTTP/1.1",  404, NoSuchTagSet, 292 - 26 - "-" "S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.241-160.348.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.362-b10 java/1.8.0_362 vendor/Oracle_Corporation cfg/retry-mode/standard" - V0uTx9v0KT6VH3NWtzUFs6fHRQNqpRuqypPq2nQjM0TikWE4QHKD+YVGfeBx4Zk06V+I99/2IIg= SigV4 ECDHE-RSA-AES128-GCM-SHA256 AuthHeader s3.ap-south-1.amazonaws.com TLSv1.2 - -
```