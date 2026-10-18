# Understanding storage

## Day 12

- [ ] Understand what storage is
- [ ] Understand the types of storage
- [ ] Create an S3 bucket and attach it
- [ ] Create a block storage and attach it


## Storage

- Storage refers to the process of storing digital data for future use. 
- Primary Storage: It is the storage that is directly accessible by the computer's CPU, such as Random Access Memory (RAM) and cache memory. It is volatile and is used to store data that the computer is currently using.
- Secondary Storage: It is the storage that is not directly accessible by the CPU and includes all forms of external storage such as hard disks, solid-state drives, CDs, DVDs, flash drives, and magnetic tapes. It is non-volatile and is used to store data for future use.
- Secondary storage can be further divided into the following types:
  - Block Storage: It is a type of storage that stores data in fixed-sized blocks and is accessed using block-level protocols such as iSCSI, Fibre Channel, and ATA over Ethernet. It is commonly used for databases, virtual machines, and other applications that require low-latency access to data.
  - Object Storage: It is a type of storage that stores data as objects and is accessed using object-level protocols such as Simple Storage Service (S3), OpenStack Swift, and Ceph. It is commonly used for storing unstructured data such as images, videos, and other multimedia files.
  - File Storage: It is a type of storage that stores data in a hierarchical structure and is accessed using file-level protocols such as Network File System (NFS) and Server Message Block (SMB). It is commonly used for storing files that require shared access such as documents, spreadsheets, and other office files.


## Differences between storage


|                | Block Storage                             | Object Storage                              |
|----------------|-------------------------------------------|---------------------------------------------|
| Data Type      | Fixed size blocks of data                 | Files and unstructured data                 |
| Data Access    | Low latency, fast and random access       | High latency, sequential and batch access   |
| Scalability    | Limited scalability without disruption    | Highly scalable without disruption          |
| Management     | High degree of management and control      | Low degree of management and control         |
| Use Case       | Used for transactional data and databases | Used for backup, archiving, and data lakes   |
| Example Service| Amazon Elastic Block Store (EBS)           | Amazon Simple Storage Service (S3)           |


## S3 buckets 

- Amazon S3 (Simple Storage Service) is a highly scalable, secure, and durable cloud object storage service provided by Amazon Web Services. 
- An S3 bucket is a container for storing objects in the Amazon S3 storage service. 
- It can be thought of as a folder or directory within the S3 storage system that can store an unlimited amount of data, including photos, videos, audio files, documents, and other digital assets.
- S3 bucket provides features such as lifecycle policies, versioning, access controls, and encryption to ensure the security, compliance, and durability of stored data. 

## EBS volumes

- Amazon Elastic Block Store (EBS) volumes are network-attached block-level storage devices that can be attached to instances. 
- They provide persistent storage volumes for data that can outlive the lifecycle of instance. 
- They support a variety of use cases, from boot volumes to data storage volumes, and offer several storage options, such as General Purpose SSD (GP2), Provisioned IOPS SSD (IO1), Throughput Optimized HDD (ST1), and Cold HDD (SC1).
- EBS volumes can be easily created, attached, and detached from instances, and can be resized on-the-fly without any disruption to the application running on the instance. 
- They also offer several advanced features, such as snapshots for backup and disaster recovery, encryption for data at rest, and multi-attach support for high-availability workloads.