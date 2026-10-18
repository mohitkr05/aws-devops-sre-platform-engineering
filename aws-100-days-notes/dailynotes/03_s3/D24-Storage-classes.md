# Storage classes in S3


## Day 24 Checklist

- [ ] Understand the storage classes
- [ ] The difference between the storage classes
- [ ] Lifecycle best practices
- [ ] Creating lifecycle policy



## Storage classes

- *S3 Standard* - S3 Standard is the default storage class in S3 and provides high durability, availability, and performance. S3 Standard is designed for frequently accessed data and is suitable for a wide range of use cases, including cloud applications, content distribution, and backups.

- *S3 Intelligent-Tiering* - S3 Intelligent-Tiering is a storage class that automatically moves objects between two access tiers based on changing access patterns. The access tiers include frequent access and infrequent access. S3 Intelligent-Tiering is ideal for data with unknown or changing access patterns.

- *S3 Standard-Infrequent Access (S3 Standard-IA)* - S3 Standard-Infrequent Access is designed for data that is accessed less frequently but requires rapid access when needed. S3 Standard-IA provides the same high durability and availability as S3 Standard but at a lower cost.

*S3 One Zone-Infrequent Access (S3 One Zone-IA)* - S3 One Zone-Infrequent Access is similar to S3 Standard-IA but stores data in a single availability zone. S3 One Zone-IA is suitable for data that can be easily reproduced, such as thumbnails or transcoded media files.

- *S3 Glacier* : S3 Glacier is a secure, durable, and low-cost storage class designed for long-term data archiving. S3 Glacier provides retrieval times from minutes to hours, making it ideal for data that is rarely accessed but must be retained for compliance or regulatory reasons.

- *S3 Glacier Deep Archive*: S3 Glacier Deep Archive is a low-cost storage class designed for long-term data archiving with retrieval times from 12 to 48 hours. S3 Glacier Deep Archive is suitable for data that is rarely accessed and can tolerate the longer retrieval times.

- *S3 Outposts* : S3 Outposts is a hybrid storage service that allows customers to store and manage data on-premises using the same APIs and tools as S3 in the cloud. S3 Outposts is suitable for customers who require low-latency access to data but need to store it on-premises for compliance or regulatory reasons.

| Storage Class | Durability | Availability | Min Storage Duration | Min Object Size | Max Object Size | Cost/GB/Month |
|---------------|------------|--------------|----------------------|----------------|----------------|---------------|
| Standard      | 99.999999999% (11 9's) | 99.99%       | N/A                  | 0B             | 5TB            | $0.0230       |
| Intelligent-Tiering | 99.999999999% (11 9's) | 99.9% | 30 days | 128KB | 5TB | $0.0230 - $0.0023 |
| Standard-IA   | 99.999999999% (11 9's) | 99.9%        | 30 days              | 128KB          | 5TB            | $0.0125       |
| One Zone-IA   | 99.999999999% (11 9's) | 99.5%        | 30 days              | 128KB          | 5TB            | $0.01         |
| Glacier       | 99.999999999% (11 9's) | N/A          | 90 days              | 0B             | 5TB            | $0.004        |
| Glacier Deep Archive | 99.999999999% (11 9's) | N/A   | 180 days             | 0B             | 5TB            | $0.00099      |


## Best practices

- Define a clear storage policy: Determine which data requires frequent access and which can be stored in the lower-cost storage class.
- Use a combination of storage classes: Use a combination of storage classes to optimize costs and performance. For example, you can use Standard storage for frequently accessed data, and Glacier Deep Archive for long-term archiving.
- Use S3 Lifecycle policies: Configure S3 Lifecycle policies to automatically transition objects to lower-cost storage classes as they age. This can help reduce storage costs and optimize performance.
- Use S3 Intelligent-Tiering: S3 Intelligent-Tiering is a cost-effective storage class that automatically moves data between two access tiers based on changing access patterns. This can help reduce storage costs while still providing high performance.
- Use S3 Object Lock: Use S3 Object Lock to prevent objects from being deleted or modified, ensuring that important data is protected and remains unchanged.

## S3 Lifecycle policy

This lifecycle policy applies to all objects with the prefix `logs/`. It transitions objects to Standard-Infrequent Access after `30 days`, to Glacier after `365 days`, and expires them after `3650 days (10 years)`. By using this policy, you can automatically move objects to lower-cost storage classes as they age, and ensure that they are automatically deleted after they are no longer needed.

```json
{
    "Rules": [
        {
            "Status": "Enabled",
            "Prefix": "logs/",
            "Transitions": [
                {
                    "Days": 30,
                    "StorageClass": "STANDARD_IA"
                },
                {
                    "Days": 365,
                    "StorageClass": "GLACIER"
                }
            ],
            "Expiration": {
                "Days": 3650
            }
        }
    ]
}
```


