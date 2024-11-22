# Mongo DB Documentation

A brief description of MongoDB commands

## MongoDB Atlas

MongoDB Atlas is a fully managed cloud database service provided by MongoDB. It simplifies the deployment, scaling, and operation of MongoDB databases in the cloud, offering high availability, security, and performance. Atlas supports multiple cloud providers, including AWS, Google Cloud, and Azure, and integrates seamlessly with modern application stacks. Features include automated backups, advanced data analytics, and built-in security measures like encryption and access control.

## MongoDB Compass 

MongoDB Compass is a graphical user interface (GUI) tool provided by MongoDB for visualizing, managing, and querying MongoDB databases. It allows users to explore data, build queries with ease, and perform database operations without requiring extensive knowledge of the MongoDB query language.

## MongoDB Shell 


The MongoDB Shell (mongosh) is an interactive JavaScript-based command-line interface for MongoDB. It allows users to interact directly with MongoDB databases, perform administrative tasks, and execute queries in real time.


## MongoDB 


MongoDB is a popular open-source, NoSQL database management system that stores data in a flexible, document-oriented format called BSON (Binary JSON). It is designed to handle unstructured or semi-structured data, making it highly scalable, performant, and suitable for modern application development.It came from the word Humongous.


# SQL vs MongoDB

A comparison between SQL and MongoDB to help understand their differences.

| **Aspect**                 | **SQL (Relational Databases)**                               | **MongoDB (NoSQL Database)**                          |
|----------------------------|-------------------------------------------------------------|------------------------------------------------------|
| **Data Model**             | Relational, table-based (rows and columns).                 | Document-oriented, uses BSON (JSON-like) documents. |
| **Schema**                 | Fixed schema; structure must be defined beforehand.         | Schema-less; allows dynamic fields and flexibility.  |
| **Query Language**         | SQL (Structured Query Language).                            | MongoDB Query Language (MQL), JavaScript-based.      |
| **Relationships**          | Uses joins to relate tables.                                | Embeds or references documents to handle relations.  |
| **Scaling**                | Vertical scaling (adding resources to a single server).     | Horizontal scaling (sharding across servers).        |
| **Transaction Support**    | Full ACID compliance (Atomicity, Consistency, Isolation, Durability). | ACID compliance for multi-document transactions introduced in later versions. |
| **Performance**            | Optimized for structured data with complex queries.         | Faster for unstructured or semi-structured data.     |
| **Use Cases**              | Banking, e-commerce, and systems requiring complex relationships. | Real-time analytics, IoT, and applications with evolving schemas. |
| **Examples of Databases**  | MySQL, PostgreSQL, Oracle DB, Microsoft SQL Server.         | MongoDB, Couchbase, Cassandra.                      |
| **Storage**                | Table-based storage.                                        | Collection of documents stored as key-value pairs.  |
| **Normalization**          | Data is normalized (minimized redundancy).                 | Data is often denormalized for faster access.        |
| **Installation**           | Requires database management software.                     | Standalone or hosted services like MongoDB Atlas.    |


 

 ## SQL Database Structure

 # Database Tables

## Students Table
| **Student ID** | **First Name** | **Last Name** | **Date of Birth** | **Email**               |
|----------------|----------------|---------------|-------------------|-------------------------|
| 1              | John           | Doe           | 2000-05-12        | john.doe@example.com    |
| 2              | Jane           | Smith         | 2001-09-20        | jane.smith@example.com  |
| 3              | Alice          | Johnson       | 1999-03-15        | alice.johnson@example.com |

## Subjects Table
| **Subject ID** | **Subject Name**     | **Credits** |
|----------------|----------------------|-------------|
| 101            | Mathematics          | 4           |
| 102            | Physics              | 3           |
| 103            | Computer Science     | 4           |

## Grades Table
| **Grade ID** | **Student ID** | **Subject ID** | **Grade** |
|--------------|----------------|----------------|-----------|
| 1            | 1              | 101            | A         |
| 2            | 1              | 102            | B+        |
| 3            | 2              | 103            | A-        |
| 4            | 3              | 101            | B         |
| 5            | 3              | 103            | A         |


## MongoDB Data Example

Below is an example of how student data can be structured in MongoDB with embedded documents for subjects and grades.

```json
[
  {
    "_id": "unique_id_1",
    "first_name": "John",
    "last_name": "Doe",
    "date_of_birth": "2000-05-12",
    "email": "john.doe@example.com",
    "subjects": [
      {
        "subject_id": "unique_subject_id_1",
        "subject_name": "Mathematics",
        "credits": 4,
        "grade": "A"
      },
      {
        "subject_id": "unique_subject_id_2",
        "subject_name": "Physics",
        "credits": 3,
        "grade": "B+"
      }
    ]
  },
  {
    "_id": "unique_id_2",
    "first_name": "Jane",
    "last_name": "Smith",
    "date_of_birth": "2001-09-20",
    "email": "jane.smith@example.com",
    "subjects": [
      {
        "subject_id": "unique_subject_id_3",
        "subject_name": "Computer Science",
        "credits": 4,
        "grade": "A-"
      }
    ]
  },
  {
    "_id": "unique_id_3",
    "first_name": "Alice",
    "last_name": "Johnson",
    "date_of_birth": "1999-03-15",
    "email": "alice.johnson@example.com",
    "subjects": [
      {
        "subject_id": "unique_subject_id_1",
        "subject_name": "Mathematics",
        "credits": 4,
        "grade": "B"
      }
    ]



# Key Features of MongoDB

## 1. Flexible Schema Design
- **Schema-less**: MongoDB allows documents within the same collection to have different structures, which gives flexibility to handle evolving data models.
- **Rapid Development**: With dynamic schemas, developers can quickly iterate and change the structure of their data without the need for migrations.
- **Supports Complex Data Types**: MongoDB natively supports arrays, embedded documents, and other complex data types, making it ideal for hierarchical data.

## 2. Scalability and Performance
- **Horizontal Scaling**: MongoDB can scale across multiple servers using sharding, distributing data across machines to handle large-scale applications.
- **High Throughput**: MongoDB offers high performance for both read and write operations, thanks to its efficient indexing and in-memory storage engine.
- **Auto-sharding and Load Balancing**: MongoDB automatically balances data across clusters, optimizing resource usage and ensuring high availability for large datasets.

## 3. Document-Oriented Storage
- **BSON Format**: MongoDB stores data in BSON (Binary JSON), which allows for richer, more complex data types than traditional relational databases.
- **Natural Data Modeling**: The document model aligns closely with how developers think about data, making it intuitive to work with.
- **Embedded Data**: Related data can be embedded within a single document, reducing the need for joins and improving read performance.

## 4. Dynamic Queries
- **Rich Query Language**: MongoDB supports a powerful query language, allowing developers to perform complex queries on data, including deep document searches.
- **Flexible Filters**: Developers can query by a wide variety of conditions, including range queries, regular expressions, and geospatial data.
- **Real-time Querying**: MongoDB is designed to handle real-time queries efficiently, making it ideal for interactive applications.

## 5. Aggregation Framework
- **Data Transformation**: MongoDB’s aggregation framework allows you to transform data and perform operations like filtering, grouping, and sorting within the database.
- **Multiple Stages**: The framework supports a pipeline of stages, where each stage performs a specific transformation on the data, improving performance.
- **Powerful Operations**: It supports operations such as `$group`, `$match`, `$sort`, and `$project`, enabling complex data analysis directly in the database.

## 6. Open Source and Community
- **Free and Open Source**: MongoDB is released under the SSPL (Server Side Public License), making it open-source and accessible to developers and organizations.
- **Active Community**: MongoDB has a large and active community of developers, providing open forums, guides, and solutions to common problems.
- **Extensive Documentation**: MongoDB offers comprehensive documentation, tutorials, and a wide range of community resources, making it easy for newcomers to learn and integrate MongoDB.




