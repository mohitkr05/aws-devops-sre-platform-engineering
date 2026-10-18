# Best Practices

## Day 26 Checklist

- [ ] Organizing objects with prefixes
- [ ] S3 performance optimizations
- [ ] Enabling multipart uploads
- [ ] Checking the metrics
- [ ] Storage lens dashboard

## Organizing objects with Prefixes

- You can use prefixes to organize the data that you store in Amazon S3 buckets
- A prefix is a string of characters at the beginning of the object key name
- A prefix can be any length, subject to the maximum length of the object key name (1,024 bytes)
- For example, if you were storing information about cities, you might naturally organize them by continent, then by country, then by province or state.
- Because these names don't usually contain punctuation, you might use slash (/) as the delimiter. The following examples use a slash (/) delimiter.
  - Europe/France/Nouvelle-Aquitaine/Bordeaux
  - North America/Canada/Quebec/Montreal
  - North America/USA/Washington/Bellevue


## S3 Performance Optimization

### Enabling multipart uploads

Initialize the multipart upload
`aws s3api create-multipart-upload --bucket my-bucket --key my-object`

`zip existing.zip --out new.zip -s 50m`


```json
{
    "ServerSideEncryption": "AES256",
    "Bucket": "100daysofaws",
    "Key": "original-zip.zip",
    "UploadId": "waJgNJ22kn9rdgouN2f5E_M18LxyKpdiEELJXvpXNcsR5LAgylcAD3LF2oO12vKQZ3VChviLm85VU_x1NFoQgzPqOVXkvcAdD_DM5wL_5mcHY1O5xpggQredjj2UG6bk"
}

```

Upload each part
`aws s3api upload-part --bucket 100daysofaws --key original.zip --upload-id 1JhEAi0j4_Q6yswLwZjQcTp4xgrKZJw0RTxhfMRwCtDl4Zy7kO4cjuAOD1r_DJP.cM8ZzvdPW6xQ7ae_2nBv6IDWOubNKmCJ0v2C4VlFcYMMqlQLdhRQfOH6twWy3Rgp --part-number 01 --body parts.zip`

Repeat the upload-part command for each part

`aws s3api list-parts --bucket 100daysofaws --key original.zip --upload-id "1JhEAi0j4_Q6yswLwZjQcTp4xgrKZJw0RTxhfMRwCtDl4Zy7kO4cjuAOD1r_DJP.cM8ZzvdPW6xQ7ae_2nBv6IDWOubNKmCJ0v2C4VlFcYMMqlQLdhRQfOH6twWy3Rgp"`

{
    "ServerSideEncryption": "AES256",
    "ETag": "\"bacc0fdfc06fac7e8f5f90a4424cdd25\""
}

{
    "ServerSideEncryption": "AES256",
    "ETag": "\"66b189d4bf87eec9561f6cc1c79725bb\""
}


Complete the multipart upload


`aws s3api complete-multipart-upload --bucket 100daysofaws --key original-zip.zip --upload-id "waJgNJ22kn9rdgouN2f5E_M18LxyKpdiEELJXvpXNcsR5LAgylcAD3LF2oO12vKQZ3VChviLm85VU_x1NFoQgzPqOVXkvcAdD_DM5wL_5mcHY1O5xpggQredjj2UG6bk"
--multipart-upload '{"Parts": [{ "PartNumber": 1,"ETag": "\"bacc0fdfc06fac7e8f5f90a4424cdd25\""},
                               { "PartNumber": 2,"ETag": "\"66b189d4bf87eec9561f6cc1c79725bb\""}]}'`

```json

{
    "ServerSideEncryption": "AES256",
    "VersionId": "HL_e5p08YMl5QMU9pl2pvwm89Ctw5nKi",
    "Location": "https://100daysofaws.s3.ap-south-1.amazonaws.com/original-zip.zip",
    "Bucket": "100daysofaws",
    "Key": "original-zip.zip",
    "ETag": "\"c726566b0e573b1237a16adfa5648cf1-2\""
}


```json
{
    "ServerSideEncryption": "AES256",
    "Bucket": "100daysaws-syd",
    "Key": "uploaded.zip",
    "UploadId": "YZUUi_OVKoV7_oJekPRNZ0VzJ3.bFfj7175UCHGMP3qs5I7Zu1P.9o9q8ORDmN2byi9SKDGQ_DExdf8gDSORpk0X0NyLgKKCMx4uCQQ4W9ze4UD.NP3DNTu9z9dIOmT0VK638bV_aWowm1JMyjbUbw--"
}


{
    "ServerSideEncryption": "AES256",
    "ETag": "\"66b189d4bf87eec9561f6cc1c79725bb\""
}

{
    "ServerSideEncryption": "AES256",
    "ETag": "\"bacc0fdfc06fac7e8f5f90a4424cdd25\""
}


```
```
### Bucket and Object Naming

- Choose a unique bucket name to avoid conflicts with other users.
- Avoid using sequential or timestamp-based naming patterns that could lead to hotspots and throttling.
- Consider using a hierarchical key structure for your objects to distribute the workload across multiple keys.

### Data Transfer, throughput & Latency

- You can easily achieve thousands of transactions per second in request performance when uploading and retrieving storage from Amazon S3. Amazon S3 automatically scales to high request rates with at least 3,500 PUT/COPY/POST/DELETE or 5,500 GET/HEAD requests per second per partitioned prefix
- Use multipart upload for large objects to parallelize data transfer and improve upload/download performance.d
- There are no limits to the number of prefixes in a bucket
- You can increase your read or write performance by using parallelization
  - For example, if you create 10 prefixes in an Amazon S3 bucket to parallelize reads, you could scale your read performance to 55,000 read requests per second
  - Similarly, you can scale write operations by writing to multiple prefixes
  - The scaling, in the case of both read and write operations, happens gradually and is not instantaneous
  - While Amazon S3 is scaling to your new higher request rate, you may see some 503 (Slow Down) errors
  - These errors will dissipate when the scaling is complete. For more information about creating and using prefixes, see Organizing objects using prefixes.
- If you want higher transfer rates over a single HTTP connection or single-digit millisecond latencies, use Amazon CloudFront or Amazon ElastiCache for caching with Amazon S3.
- If you want fast data transport over long distances between a client and an S3 bucket, use Configuring fast, secure file transfers using Amazon S3 Transfer Acceleration

### Data compression

- Compress your data before uploading it to S3, especially for text-based files, to reduce storage costs and improve transfer speed.
- Consider using compression formats like GZIP or ZIP for efficient storage and faster data retrieval


## Metrics

- Bucket Size: This metric provides the total size of the bucket, including all objects stored within it. Monitoring bucket size helps you understand your storage usage and plan for capacit
- Request Metrics: These metrics include the number of requests made to your S3 bucket, such as GET, PUT, DELETE, and HEAD requests. Monitoring request metrics helps you analyze the traffic and usage patterns of your bucke
- Data Transfer Metrics: These metrics track the amount of data transferred in and out of your S3 bucket. They include metrics like Bytes Uploaded, Bytes Downloaded, and Bytes Transferred. Monitoring data transfer metrics helps you understand the data flow and analyze cost
- Availability Metrics: These metrics measure the availability of your S3 bucket, including metrics like 4xx Errors and 5xx Errors. Monitoring availability metrics helps you identify any issues that might impact the accessibility of your bucke
- Replication Metrics: If you have enabled cross-region replication for your S3 bucket, you can monitor metrics related to replication lag and replication status. These metrics provide insights into the replication process and ensure data consistency across region
- Storage Class Analysis: S3 offers various storage classes, such as Standard, Intelligent-Tiering, Glacier, etc. Monitoring storage class analysis metrics helps you evaluate the cost-effectiveness of your storage choices and optimize storage cost
- CloudWatch Metrics: Amazon S3 integrates with Amazon CloudWatch, allowing you to collect additional metrics for your buckets. CloudWatch provides metrics like bucket-level data events, bucket-level API latency, and more. These metrics can provide deeper visibility into your S3 usage.