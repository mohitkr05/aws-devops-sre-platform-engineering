# HTTPS

## Day 10 Checklist

- [ ] What is HTTPS?
- [ ] Difference between HTTP & HTTPS
- [ ] SSL vs TLS
- [ ] Using Let'sEncrypt for certificate generation


## What is HTTPS?

- HTTPS, or HyperText Transfer Protocol Secure, is an extension of HTTP that is used to secure online communication and protect sensitive data. 
- It adds an additional layer of security to HTTP by encrypting the data that is transmitted between a client and a server. 
- HTTPS provides encryption through the use of SSL, or Secure Sockets Layer, which has been replaced by TLS, or Transport Layer Security. 
- SSL/TLS creates a secure connection between the client and the server by establishing an encrypted link, and then encrypting all data that is transmitted over the connection. 
- In order to use HTTPS, a digital certificate is required. 
- Digital certificates are issued by trusted third-party organizations, known as Certificate Authorities, and are used to verify the identity of the website or server. 
- When a client connects to a website using HTTPS, the website presents its digital certificate to the client, which verifies the website's identity.

## HTTP vs HTTPS

|           | HTTP                                                     | HTTPS                                                     |
|-----------|----------------------------------------------------------|-----------------------------------------------------------|
| Acronym   | HyperText Transfer Protocol                              | HyperText Transfer Protocol Secure                         |
| Port      | 80                                                       | 443                                                       |
| Encryption| Not encrypted                                            | Encrypted                                                 |
| Security  | Not secure                                               | Secure                                                    |
| Data      | Data transmitted in plain text                            | Data transmitted in encrypted form                         |
| Authentication | No authentication                                     | Server authentication using digital certificates            |
| Certificate | Not required                                            | Required                                                  |
| Browser warning| No warning                                            | Browser warns users if the site's certificate is invalid   |
| SEO       | Lower search engine ranking due to unsecured connection   | Higher search engine ranking due to secure connection      |
| Performance| Faster, as it doesn't require encryption overhead         | Slower, as it requires encryption overhead                  | 


## Difference between SSL and TLS

- SSL (Secure Sockets Layer) is a security protocol that provides secure communication between clients and servers over the internet. It creates a secure channel between the two parties by encrypting the data transmitted between them, preventing unauthorized access and tampering

- TLS operates at the transport layer of the OSI model and provides end-to-end encryption between the client and the server. It is widely used to secure web traffic, including online transactions, email, and messaging applications. As with SSL, TLS requires the use of digital certificates to authenticate the server and the client. These certificates are issued by trusted third-party organizations, known as certificate authorities (CAs).

| SSL | TLS |
| --- | --- |
| Developed by Netscape in the 1990s | Developed as an upgrade to SSL in the late 1990s |
| Uses weaker encryption algorithms | Uses stronger encryption algorithms |
| Handshake process uses less secure key exchange algorithms | Handshake process uses a more secure key exchange algorithm |
| Client and server do not have to agree on a mutually supported version of the protocol | Client and server must agree on a mutually supported version of the protocol |
| No longer in use due to security vulnerabilities | Widely used to secure online communication between clients and servers |
| Not forwards-compatible with TLS | Backwards-compatible with SSL |
| Name is deprecated | Current and widely used protocol for secure communication over the internet |


## Generating certificate using Let's Encrypt

```bash
sudo apt update
sudo /opt/bitnami/bncert-tool
```

