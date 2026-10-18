# Cross Region Replication


## Day 22 Checklist

- [ ] Understand S3 Cross region replication
- [ ] Advantages of using Cross region replication
- [ ] Enable Cross Region replication
- [ ] Testing cross region replication

## What is Cross Region replication

- Cross-Region Replication is a feature of Amazon S3 that allows automatic, asynchronous copying of objects across different AWS Regions.
- This means that the data can be replicated across different geographic locations, ensuring data availability and compliance with data residency requirements.


## Use cases

There are several use cases for cross-region replication, including:

- Disaster Recovery: Replicating data to another region can help ensure data availability in case of natural disasters, power outages, or other events that could impact the primary data center.
- Compliance and Data Residency: In some cases, data residency regulations require that data must be stored in a specific geographic location. Cross-region replication allows organizations to comply with these regulations while maintaining data availability.
- Reduced Latency: Replicating data to a region closer to the users can help reduce latency and improve application performance.


## How to enable Cross Region Replication

To set up cross-region replication, you need to create a replication configuration in your source bucket. This configuration specifies the destination bucket and the AWS Region where it resides. Once replication is enabled, all new objects uploaded to the source bucket will be automatically replicated to the destination bucket.

```json
{
  "Rules": [
    {
      "Status": "Enabled",
      "Destination": {
        "Bucket": "arn:aws:s3:::destination-bucket"
      }
    }
  ]
}

```

`aws s3api put-bucket-replication --bucket source-bucket --replication-configuration file://replication-config.json`

`aws s3api get-bucket-replication --bucket source-bucket`


## Testing replication

To test cross-region replication, you can follow these steps:

- Create two S3 buckets in different regions, one for the source and one for the destination.
- Enable versioning on both buckets.
- Configure cross-region replication on the source bucket by specifying the destination bucket and region.
- Upload a new object to the source bucket and verify that it is replicated to the destination bucket.
- Modify or delete the object in the source bucket and verify that the changes are replicated to the destination bucket.

It's important to note that cross-region replication incurs additional costs for data transfer and storage in the destination region. You should also consider the impact on data consistency and access latency when replicating data across regions.


## Reference

- [Put Bucket Replication - s3api](https://docs.aws.amazon.com/cli/latest/reference/s3api/put-bucket-replication.html)
- [Gut Bucket Replication - s3api](https://docs.aws.amazon.com/cli/latest/reference/s3api/get-bucket-replication.html)