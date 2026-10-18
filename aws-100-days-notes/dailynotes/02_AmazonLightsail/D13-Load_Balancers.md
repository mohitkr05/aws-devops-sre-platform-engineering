# Load balancers


## Day 13

- [ ] Understand what load balancer is 
- [ ] How load balancers help in Horizontal scaling
- [ ] What are the types of load balancers
- [ ] How load balancer works
- [ ] Creating a load balancer in Amazon Lightsail 

## What is a Load balancer

- A load balancer is a device or service that distributes network traffic across multiple servers to improve reliability, capacity, and scalability. 
- The main function of a load balancer is to ensure that all requests to the server are spread evenly across multiple resources to avoid overloading any one server.
- Load balancers can be hardware-based or software-based, and they can operate at different layers of the OSI model, including:
  - Layer 4: Transport Layer (TCP/UDP)
  - Layer 7: Application Layer (HTTP/HTTPS)

- A load balancer can be compared to a traffic cop who is directing vehicles at a busy intersection. 
- Just like how a traffic cop ensures that vehicles move smoothly without any congestion or delay, a load balancer distributes incoming traffic to multiple servers to ensure that the workload is evenly distributed and there is no server overload or downtime. 
- Load balancer plays a crucial role in horizontal scaling by distributing the incoming traffic to multiple servers or instances. 
- When the traffic on a single server exceeds its capacity, the load balancer detects this and redirects the incoming requests to other healthy servers. 
- This ensures that the system can handle high traffic without experiencing any downtime or latency issues. 
- Load balancers can be configured to use different algorithms to distribute the load evenly across multiple servers. 

## Types of Load Balancers

- Application Load Balancer (ALB): ALBs operate at the application layer (Layer 7) and are designed to route traffic to different servers based on the content of the request. They can distribute traffic based on HTTP headers, URLs, and other application-level information.
- Network Load Balancer (NLB): NLBs operate at the transport layer (Layer 4) and are designed to handle TCP/UDP traffic. They can distribute traffic based on IP address and port.
- Classic Load Balancer (CLB): CLBs are the original type of load balancer on AWS and can handle both Layer 4 and Layer 7 traffic. However, they lack the advanced features of ALBs and NLBs.

## How Load balancer works


1. Client sends a request to the load balancer.
2. The load balancer receives the request and evaluates which server it should be sent to based on the pre-defined routing algorithm.
3. The load balancer forwards the request to the chosen server.
4. The server processes the request and sends a response back to the load balancer.
5. The load balancer receives the response from the server and sends it back to the client.
