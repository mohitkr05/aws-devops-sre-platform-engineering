# Static website hosting with S3

- [ ] Understand how the static site hosting works with S3
- [ ] Configuring the permission for the S3 bucket
- [ ] Activating the static site hosting with S3 bucket
- [ ] Using a CloudFront distribution with S3 bucket
- [ ] Mapping a domain with the CloudFront distribution


## How to create a S3 bucket

- Create an S3 Bucket: Sign in to the AWS Management Console, navigate to the S3 service, and create a new bucket. Choose a unique name for your bucket, enable static website hosting, and provide the index document (e.g., index.html) and error document (optional).

- Upload Website Files: Upload your static website files, including HTML, CSS, JavaScript, images, and any other necessary assets, to the S3 bucket. You can use the AWS Management Console, AWS CLI, or SDKs/APIs to upload the files.

- Configure Bucket Permissions: Set the bucket permissions to allow public read access to the objects. This ensures that the website files are accessible to visitors. You can configure this by updating the bucket's access control list (ACL) or using a bucket policy.

- Enable Static Website Hosting: In the S3 bucket properties, enable static website hosting and provide the index and error documents you specified earlier. This configures the bucket to serve the website files as a static website.

- Set Up DNS: To map your custom domain or subdomain to the S3 bucket, you need to configure the DNS settings. Create a DNS record (such as a CNAME or Alias record) in your DNS provider's settings to point the domain/subdomain to the S3 website endpoint.

- Test Your Website: Once the DNS changes propagate, you can test your website by accessing it using the custom domain/subdomain. You should be able to see your static website content.


###  S3 policy 

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
    }
  ]
}
```