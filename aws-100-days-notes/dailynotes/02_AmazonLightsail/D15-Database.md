# Three tier architecture & Databases


## Day 15

- [ ] Understand the three tier architecture
- [ ] Types of Databases
- [ ] Databases in AWS
- [ ] Creating a Database in AWS with Amazon Lightsail

## Three tier architecture

Three-tier architecture, also known as multi-tier architecture, is a software architecture design pattern that separates an application into three distinct layers or tiers: presentation, application, and data.

### Presentation Tier (Client Tier)

- This is the topmost layer that interacts directly with users or clients.
- It handles the user interface (UI) components and presentation logic.
- Its primary purpose is to present information to users and collect input from them.
- Examples of presentation tier technologies include web browsers, mobile apps, and desktop applications.

### Application Tier (Logic Tier or Business Tier)

- This layer contains the business logic and handles the processing and manipulation of data.
- It acts as an intermediary between the presentation tier and the data tier.
- The application tier processes requests from the presentation tier, performs required operations, and generates responses.
- It encapsulates the core functionality of the application, including validation, calculations, and rules.
- Examples of technologies used in the application tier include programming languages, frameworks, and application servers.

### Data Tier (Persistence Tier)

- This layer is responsible for storing, retrieving, and managing data.
- It handles the storage and retrieval of data from databases or other data storage systems.
- The data tier ensures data integrity, security, and persistence.
- It provides methods and interfaces for accessing and manipulating data.
- Examples of technologies used in the data tier include databases (such as SQL or NoSQL), data access frameworks, and storage systems.

The three-tier architecture promotes modularity, scalability, and reusability by separating concerns into distinct layers. Each layer has its own responsibilities and can be developed, maintained, and scaled independently, facilitating ease of maintenance and flexibility. This architecture also enhances security by enforcing separation of concerns and reducing direct access to critical data.

## What is a database

A database is an organized collection of structured data that can be easily accessed, managed, and updated. It allows users to store, organize, and retrieve data in a variety of ways. Databases are commonly used in business, education, healthcare, and many other fields to manage and store large amounts of information. They can be classified into different types based on the structure of data they store, such as relational databases, NoSQL databases, graph databases, and more.


## Types of Databases

- Relational databases: A type of database that stores and organizes data in tables, with relationships between the tables defined by common fields.
- NoSQL databases: A type of database that stores and retrieves data without using a tabular relational model. Instead, NoSQL databases use different data models, such as key-value, document, or graph.
- Object-oriented databases: A type of database that is designed to work with object-oriented programming languages. In this type of database, data is stored as objects, which can have properties and methods like objects in the programming language.
- Graph databases: A type of database that stores data as nodes and edges in a graph, allowing for more complex relationships between data points to be modeled.
- Time-series databases: A type of database that is optimized for storing and retrieving time-stamped data. This type of database is often used for storing data from sensors or other IoT devices.
- In-memory databases: A type of database that stores data in memory instead of on disk, allowing for faster access and retrieval of data.
- Spatial databases: A type of database that is optimized for storing and retrieving data related to geographic locations or spatial relationships between data points.
- Columnar databases: A type of database that stores data by column rather than by row, allowing for more efficient storage and retrieval of large data sets.

## Databases in AWS

AWS provides a wide range of database services, including:

- Amazon RDS (Relational Database Service)
- Amazon Aurora
- Amazon DocumentDB
- Amazon DynamoDB
- Amazon ElastiCache
- Amazon Neptune
- Amazon QLDB (Quantum Ledger Database)
- Amazon Timestream
- Amazon Keyspaces (for Apache Cassandra)
- Amazon Managed Apache Cassandra Service


