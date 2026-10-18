# Containers

## Day 16

- [ ] Understand what containers are
- [ ] Difference between a VM and container
- [ ] What are containerization platforms available?
- [ ] Create a container with Amazon lightsail 

## What are containers?


- Containers are a technology that allows for the creation of lightweight, portable, and self-contained environments that can run applications and their dependencies. 
- Containers work by using a combination of kernel features such as namespaces and cgroups to isolate the resources used by each container, such as network interfaces, file systems, and process trees. 
- Each container has its own file system, network stack, and process space, but all containers on a host share the same kernel.
- Containers use container images, which are read-only templates that contain all the necessary files and settings to run an application. 
- These images are built using containerization tools such as Docker, and can be easily shared and deployed to any system that supports containers.
- Containers can be easily moved between environments, such as development, testing, and production, without requiring changes to the underlying application.
- Containerization technology has become increasingly popular in recent years, with Docker being one of the most widely used containerization platforms.


## Difference between VM and Containers

| Virtual Machine                                            | Container                                               |
|------------------------------------------------------------|---------------------------------------------------------|
| Hypervisor technology used to create multiple VMs         | OS-level virtualization that allows multiple containers |
| Each VM requires its own guest OS                           | Shares host operating system                            |
| Each VM consumes its own system resources                    | Share the host system's resources                       |
| VMs are slower to deploy and start-up                         | Containers are quicker to deploy and start-up           |
| Hardware-level isolation                                    | Software-level isolation                               |
| More suitable for long-running applications or services   | More suitable for microservices or single processes     |
| Takes up more disk space                                      | Takes up less disk space                                |
| More suitable for testing different OS environments       | More suitable for deploying and scaling applications    |


## Containerization platforms

Some famous containerization platforms are: 

- Docker
- Kubernetes
- Apache Mesos
- LXC
- CoreOS
- OpenShift
- Rancher
- Google Container Engine (GKE)
- AWS Elastic Container Service (ECS)
- Microsoft Azure Container Service


## Containers with Lightsail

- One of the key advantages of Lightsail Containers is that it offers a simple, easy-to-use interface that is well-suited for users who are new to containerization. 
- Users can launch containers directly from the Lightsail console, without the need to set up a separate container registry or orchestration platform. 
- Lightsail Containers also integrates with other Lightsail services, such as load balancers and DNS management, to provide a comprehensive solution for deploying containerized applications.
- Lightsail Containers also offers a high level of customization and control for users who are more experienced with containerization. Users can choose from a range of container images, including popular options like Ubuntu, CentOS, and Node.js, or they can upload their own custom images. 
- Lightsail Containers also supports Kubernetes, which allows users to manage containers at scale and take advantage of advanced features like automatic scaling and load balancing.