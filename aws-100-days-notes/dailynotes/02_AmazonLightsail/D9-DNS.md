# Understanding DNS

## Day 9 

- [ ] What is a DNS
- [ ] How DNS works
- [ ] What are the type of DNS records
- [ ] Create a DNS record for the booked domain
- *Our website is up, but is it secure?*


## What is DNS

- There are two concepts here, Domain name server and the DNS Protocol.
- DNS stands for Domain Name System, which is a system that converts domain names into IP addresses. 
- The DNS server is like a phonebook for the internet, where instead of looking up phone numbers for people, you're looking up IP addresses for websites.
- Let's say you want to visit the website www.google.com. When you type that address into your web browser, your computer sends a request to a DNS server to translate the domain name (www.google.com) into an IP address (such as 216.58.194.174). 
- The DNS server looks up the IP address associated with the domain name and sends it back to your computer. Your computer then uses that IP address to connect to the web server hosting the website.

## How DNS works?

- When you type a domain name into your web browser (like www.google.com).
- Your computer sends a request to a DNS resolver (usually provided by your internet service provider) to translate the domain name into an IP address.
- The DNS resolver first checks its cache to see if it has a record of the domain name and IP address. If it does, it returns the IP address to your computer.
- If the DNS resolver doesn't have a cached record of the domain name, it sends a request to the DNS root server to find the authoritative nameserver for the top-level domain of the domain name (in this case, the .com TLD).
- The DNS root server responds with the IP address of the authoritative nameserver for the .com TLD.
- The DNS resolver sends a request to the authoritative nameserver for the .com TLD to find the authoritative nameserver for the second-level domain (in this case, google.com).
- The authoritative nameserver for the .com TLD responds with the IP address of the authoritative nameserver for google.com.
- The DNS resolver sends a request to the authoritative nameserver for google.com to find the IP address associated with the domain name.
- The authoritative nameserver for google.com responds with the IP address associated with the domain name.
- The DNS resolver caches the IP address for future requests, and returns it to your computer.
- Your computer uses the IP address to connect to the web server hosting the website.


## Types of DNS Records

- A (Address) Record - maps a domain name to an IPv4 address
- AAAA (IPv6 Address) Record - maps a domain name to an IPv6 address
- CNAME (Canonical Name) Record - maps a domain name to another domain name (often used for subdomains)
- MX (Mail Exchange) Record - specifies the mail server responsible for accepting email messages on behalf of a domain
- TXT (Text) Record - stores arbitrary text data associated with a domain, often used for domain verification or anti-spam measures
- NS (Name Server) Record - specifies the authoritative nameservers for a domain
- SOA (Start of Authority) Record - contains administrative information about a DNS zone, including the primary nameserver and other settings
- SRV (Service) Record - specifies the location of services such as SIP or LDAP
- PTR (Pointer) Record - used for reverse DNS lookups to map an IP address to a domain name
- SSHFP (SSH Fingerprint) Record - stores the fingerprint of an SSH public key for authentication purposes
- TLSA (TLS Authentication) Record - used to associate a TLS server certificate with a domain name
- CAA (Certification Authority Authorization) Record - specifies which certificate authorities are authorized to issue certificates for a domain


## Creating a DNS record in Lightsail

1. Go to the Lightsail console and select the DNS zone where you want to create the record.
2. Click on the "Create record" button.
3. Select the record type you want to create from the dropdown menu. The options include A record, AAAA record, CNAME record, MX record, and TXT record.
4. Enter the required information for the record, such as the IP address for the A record, the domain name for the CNAME record, or the email server for the MX record.
5. Click on the "Create record" button to create the new record.
6. Once the record is created, it may take some time for the changes to propagate across the internet.