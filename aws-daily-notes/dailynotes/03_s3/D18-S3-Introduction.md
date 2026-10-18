# Introduction to S3

## Day 18 Checklist

- [ ] Overview of S3 and its features
- [ ] Creating an S3 bucket using the AWS Management Console
- [ ] Uploading files to the bucket  
- [ ] Accessing files in the bucket via URL
- [ ] Emptying a Bucket
- [ ] Deleting a Bucket


## Overview of S3 and its features

Amazon Simple Storage Service (S3) is a scalable and secure cloud storage service provided by Amazon Web Services (AWS). It allows users to store and retrieve large amounts of data from anywhere on the web. S3 is designed to offer 99.999999999% durability, and 99.99% availability of data over a given year. This article provides an overview of S3 and its features.

## What is Amazon S3?

Amazon S3 is a simple object storage service that enables users to store and retrieve data from anywhere on the web. S3 provides a web services interface that can be used to store and retrieve any amount of data, at any time, from anywhere on the web. This means that users can access S3 from anywhere with an internet connection.

- You can use Amazon S3 to store and retrieve any amount of data at any time, from anywhere on the web. 
- Amazon S3 stores data as **objects** within **buckets**. 
- *An object is a file and any optional metadata that describes the file*
- To store a file in Amazon S3, you upload it to a bucket. 
- When you upload a file as an object, you can set permissions on the object and any metadata. 


## Features of Amazon S3

- Scalability: S3 is designed to be highly scalable. It can store an unlimited amount of data and handle any amount of traffic.
- Durability: S3 is designed to provide 99.999999999% durability, which means that your data will remain safe and accessible even in the event of hardware failures, natural disasters, or other unforeseen events.
- Security: S3 provides multiple layers of security to ensure the safety and privacy of your data. It supports encryption of data both at rest and in transit. S3 also supports access control policies to restrict access to your data.
- Versioning: S3 supports versioning of objects, which means that you can keep multiple versions of an object in the same bucket. This is useful for applications that require version control.
- Lifecycle management: S3 provides lifecycle management policies that can be used to automatically transition objects to different storage classes or delete them after a certain period of time. 
- Cross-region replication: S3 provides cross-region replication that can be used to replicate data to different regions for disaster recovery and data center migration.
- Object tagging: S3 provides object tagging that can be used to categorize and organize objects for easier management.
- Performance: S3 is designed to provide high performance for both read and write operations. It can handle high traffic loads and provides low latency access to data.

## Bucket name convention

- Bucket names must be between 3 (min) and 63 (max) characters long.
- Bucket names can consist only of lowercase letters, numbers, dots (.), and hyphens (-).
- Bucket names must begin and end with a letter or number.
- Bucket names must not contain two adjacent periods.
- Bucket names must not be formatted as an IP address (for example, `192.168.5.4`).
- Bucket names must not start with the prefix `xn--`.
- Bucket names must not end with the suffix `-s3alias`. This suffix is reserved for access point alias names. For more information, see Using a bucket-style alias for your S3 bucket access point.
- Bucket names must not end with the suffix `--ol-s3`. This suffix is reserved for Object Lambda Access Point alias names. For more information, see How to use a bucket-style alias for your S3 bucket Object Lambda Access Point.
- **Bucket names must be unique across all AWS accounts in all the AWS Regions within a partition. A partition is a grouping of Regions**. AWS currently has three partitions: aws (Standard Regions), aws-cn (China Regions), and aws-us-gov (AWS GovCloud (US)).
- A bucket name cannot be used by another AWS account in the same partition until the bucket is deleted.
- **Buckets used with Amazon S3 Transfer Acceleration can't have dots (.) in their names**

## Accessing Objects

- You can access your bucket using the Amazon S3 console
- The URLs to access objects are as follows
  - In a virtual-hosted–style request, the bucket name is part of the domain name in the URL.
  `https://bucket-name.s3.region-code.amazonaws.com/key-name`
  - In Amazon S3, path-style URLs use the following format:
  `https://s3.region-code.amazonaws.com/bucket-name/key-name`


## Emptying a Bucket

- When you empty a bucket, you delete all the objects, but you keep the bucket
- After you empty a bucket, it cannot be undone.
- When you empty a bucket that has S3 Bucket Versioning enabled or suspended, all versions of all the objects in the bucket are deleted.

## Deleting a Bucket

- Bucket names are unique. If you delete a bucket, another AWS user can use the name
- Make sure the bucket is empty – You can only delete buckets that don't have any objects in them. Make sure the bucket is empty.
- Make sure there aren't any access points attached – You can only delete buckets that don't have any access points attached to them. Delete any access points that are attached to the bucket, before deleting the bucket.
- `s3:DeleteBucket` permissions – If you cannot delete a bucket, work with your IAM administrator to confirm that you have `s3:DeleteBucket` permissions. For information about how to view or update IAM permissions, see Changing permissions for an IAM user in the IAM User Guide.
- `s3:DeleteBucket` deny statement – If you have s3:DeleteBucket permissions in your IAM policy and you cannot delete a bucket, the bucket policy might include a deny statement for `s3:DeleteBucket`. Buckets created by ElasticBeanstalk have a policy containing this statement by default. Before you can delete the bucket, you must delete this statement or the bucket policy.
