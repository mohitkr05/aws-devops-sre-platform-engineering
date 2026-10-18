# Distributions

## Day 14

- [ ] What is a distribution or CDN
- [ ] How CDN Works?
- [ ] Types of CDN 
- [ ] Creating a CDN with Amazon Lightsail


## CDN - Content delivery/distribution network

- A content delivery network (CDN), also known as a content distribution network, is a geographically distributed network of proxy servers and data centers. 
- The goal of a CDN is to distribute content, such as web pages, images, videos, and other media, to end-users with high availability and performance. 
- The CDN stores cached content on its servers and delivers it to users from the nearest location, which minimizes the distance the data needs to travel and reduces latency. 
- This results in faster page load times and a better user experience.


## How CDN works

- The content provider (such as a website) stores their content on one or more origin servers.
- A user requests the content from the CDN.
- The CDN identifies the server closest to the user (edge server) and sends the content from the origin server to the edge server
- The edge server caches the content and delivers it to the user.
- If another user requests the same content, the CDN will deliver it from the edge server cache instead of requesting it from the origin server again.
- The CDN continually monitors traffic and adjusts its distribution of content to ensure optimal performance.


## Types of CDN

- Push CDN: In this type, the content is directly pushed to the edge server by the content provider or origin server. The edge server then caches the content and delivers it to the users when requested.

- Pull CDN: In this type, when the content is requested by the user, it is first delivered from the origin server to the edge server. The edge server then caches the content and delivers it to the user.


## CDN in AWS

Amazon CloudFront: It is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally. CloudFront integrates with other AWS services to give developers and businesses an easy way to distribute content to end users with low latency, high data transfer speeds, and no minimum usage commitments.

