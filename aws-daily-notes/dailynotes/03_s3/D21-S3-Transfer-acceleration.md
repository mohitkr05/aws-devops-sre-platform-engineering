# S3 Transfer Acceleration

## Day 21 Checklist

- [ ] Understand S3 Transfer Acceleration
- [ ] What is an edge location?
- [ ] Use cases of S3 Transfer Acceleration
- [ ] Testing S3 Transfer Acceleration
- [ ] Cost of S3 Transfer Acceleration


## S3 Transfer acceleration

- S3 Transfer Acceleration is a feature that enables fast, easy, and secure transfers of files over the internet. 
- It uses Amazon CloudFront’s globally distributed edge locations to accelerate transfers of files over the public internet, reducing transfer times by up to 50-500%.
- When you enable Transfer Acceleration for an S3 bucket, AWS creates a distinct CloudFront distribution called an Accelerate endpoint for your bucket.
- When you upload data to the bucket through the endpoint, the data is transferred through an optimized network path to the nearest edge location for the endpoint.
- From the edge location, the data is routed through AWS's internal network to the S3 bucket in the appropriate region.

This optimized network path reduces the number of network hops and minimizes the effect of network congestion, resulting in faster upload speeds for your data.


## What is an edge location?

- An edge location is a point of presence (PoP) in a network infrastructure that is strategically located in various cities and regions around the world.
- In the context of AWS, edge locations are an integral part of the AWS global network and are used to improve the performance, latency, and availability of AWS services.
- AWS CloudFront - One of the primary use cases of edge locations is for content delivery, it caches content at edge locations
- Edge locations serve as caching points where frequently accessed content is stored.
- Some AWS compute services, such as AWS Lambda and Amazon API Gateway, can be configured to run in edge locations.
- AWS Global Accelerator utilizes edge locations to optimize network routes and improve the performance of globally distributed applications.
- Edge locations are used by Amazon Route 53, the DNS service, to provide fast and reliable DNS resolution

## S3 Transfer acceleration use-cases

- Uploading large files: S3 Transfer Acceleration is ideal for uploading large files to S3, especially over long distances or across geographically dispersed locations. This can be useful for industries such as media and entertainment, where large files like videos and high-resolution images are frequently shared.
- Disaster recovery: Transfer Acceleration can also be used for disaster recovery, allowing you to quickly move large amounts of data from one region to another in the event of a disaster. This can be useful for businesses with critical applications and data that need to be up and running quickly after a disaster.
- Cross-region replication: S3 Transfer Acceleration can also be used for cross-region replication, allowing you to replicate data between regions quickly and efficiently. This can be useful for businesses that need to keep data up-to-date in multiple regions for compliance or disaster recovery purposes.
- IoT data ingestion: IoT devices generate a large amount of data, which needs to be ingested and processed in near real-time. S3 Transfer Acceleration can be used to upload this data quickly and efficiently, allowing for faster processing and insights.
- Sharing files with partners or customers: S3 Transfer Acceleration can also be used to share large files with partners or customers across the globe, ensuring faster and more reliable delivery of the files.



## Enable S3 Transfer Acceleration

Once you have created the bucket, you can enable S3 Transfer Acceleration on it. There are two ways to enable it: via the S3 console or AWS CLI.

- Via S3 console: To enable S3 Transfer Acceleration via the S3 console, navigate to your bucket and click on the “Properties” tab. Then click on the “Transfer acceleration” option and enable it.

- Via aws cli: Use the following command

    ```bash
    aws s3api put-bucket-accelerate-configuration --bucket my-bucket --accelerate-configuration Status=Enabled
    ```

## Testing S3 Transfer acceleration

### Uploading file using S3 TA

- After enabling S3 Transfer Acceleration, you can test it by uploading a file to the bucket using an S3 Transfer Acceleration endpoint URL. 
- The endpoint URL has a specific format: “https://bucket-name.s3-accelerate.amazonaws.com/object-key”.

    ```bash
    aws s3 cp /path/to/local/file s3://bucket-name/object-key --endpoint-url https://bucket-name.s3-accelerate.amazonaws.com
    ```

### Cost of S3 TA

- S3 Transfer Acceleration does not have any additional charges apart from S3 and CloudFront data transfer charges.
- You can use the AWS Simple Monthly Calculator to estimate the cost of S3 Transfer Acceleration based on your expected usage.

