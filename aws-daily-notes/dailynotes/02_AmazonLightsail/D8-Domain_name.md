# Understanding the Domain names

## Day 8

- [ ] How the URLs are structured
- [ ] What is a domain name?
- [ ] Booking a domain name using Lightsail
- [ ] How computer will find that domain?


## How are URL structured

A URL (Uniform Resource Locator) has the following structure:

- Protocol: The protocol used to access the resource, such as HTTP, HTTPS, FTP, etc.
- Domain name: The domain name identifies the server where the resource is located, such as "www.example.com".
- Port: The port number is used to identify the process on the server that is handling the request. For example, "http://www.example.com:80".
- Path: The path is used to identify the resource on the server, such as "/path/to/resource".
- Query string: The query string is used to pass additional information to the server in the form of key-value pairs, such as "?key1=value1&key2=value2"
- Fragment identifier: The fragment identifier is used to identify a specific portion of the resource, such as "#section1".

A complete URL might look something like this:

```bash
https://www.example.com:443/path/to/resource?key1=value1&key2=value2#section1
```

## What is a Domain name?

1. A domain name is a unique name that identifies a website on the internet.
2. It is used to address web servers and web pages on the internet, much like a street address is used to locate a physical building.
3. A domain name consists of two parts: the actual name (also known as the label or the hostname) and the top-level domain (TLD), which is the extension that follows the label, such as .com, .org, or .net.
4. The domain name system (DNS) is responsible for translating domain names into IP addresses, which are used to locate web servers on the internet.
5. Domain names are registered with domain name registrars, which are accredited by the Internet Corporation for Assigned Names and Numbers (ICANN).
6. A domain name registration is typically valid for a period of one to ten years, and must be renewed in order to remain in use.
7. Domain names can be used to create email addresses and to host websites, web applications, and other internet services.
8. The availability of a domain name depends on whether or not it has already been registered by someone else.
9. The cost of a domain name registration can vary depending on the TLD and the domain name registrar.
10. A domain name can have significant impact on a website's search engine optimization (SEO) and branding efforts.

A domain name is composed of several parts, including:

- Subdomain: This is the part of the domain name that precedes the main domain name. For example, in "blog.example.com", "blog" is the subdomain.
- Main domain: This is the central part of the domain name that identifies the website or organization, and is usually the most memorable part of the domain. For example, in "blog.example.com", "example" is the main domain.
- Top-level domain (TLD): This is the suffix at the end of the domain name, which identifies the type of website or organization associated with the domain. Common TLDs include .com, .org, .net, .edu, and .gov. For example, in "blog.example.com", ".com" is the TLD.
- Second-level domain: This is the portion of the domain name that is directly to the left of the TLD, and is often used to provide additional information about the website or organization. For example, in "blog.example.com", "example" is the second-level domain.
- Country code TLD: Some TLDs are specific to certain countries, such as .uk for the United Kingdom or .au for Australia. These are known as country code top-level domains, or ccTLDs.

## List of most common TLDs

- .com - commercial businesses
- .org - non-profit organizations
- .net - network infrastructure providers
- .edu - educational institutions
- .gov - government agencies
- .co - company, corporation or commercial ventures
- .io - technology and startup companies
- .me - personal websites and blogs
- .info - informational websites
- .biz - business or commercial use


## Booking a domain name with Lightsail

Booking a domain name with Lightsail is a simple process. Follow the below steps to book a domain name with Lightsail:

1. Log in to your AWS Management Console.
2. Go to the Lightsail console and select the region where you want to create your domain.
3. Click on the "Networking" tab.
4. Select the "Create DNS zone" option.
5. Enter the domain name that you want to register and click on the "Create DNS zone" button.
6. After creating the DNS zone, you will see a list of records for that domain name.
7. Click on the "Create record" button to create a new record for the domain.
8. Enter the record details, such as the record type, value, and TTL.
9. Click on the "Create record" button to create the record.
10. Finally, update the domain name's nameservers to point to the Lightsail nameservers, which will be displayed on the "Networking" tab.

Once the domain name is registered, you can use it to host your website or any other web application on the Lightsail platform.
