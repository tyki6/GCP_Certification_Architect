# Database in gcp
## Database Category
### Relational Database - OLTP (Online Transaction Processing)
Applications where large number of users make large number of small transactions.(equivalent: MySQL, Oracle, Sql Server)
GCP Services:
- [Cloud SQL](cloud_sql.md): Supports PostgreSQL, Mysql, SQL Server for regional relational databases(upto a few TBs)
- [Cloud Spanner](cloud_spanner.md): Unlimited Scale and best availability for global applications with horizontal scaling
### Relational Database - OLAP( Online Analytics Processing)
Applications allowing users to analyse petabyte of data.
GCP Services:
- [BigQuery](big_query.md): PetaByte-scale distributed data ware house
### NoSQL Database
New approch to building your db 
GCP Services:
- [DataStore](cloud_datastore.md): Managed Serverless NoSQL document database(**Recommended** for small or medium database)
- [BigTable](cloud_big_table.md): Managed, Scalable NoSQL wide column database(**Recommended** for big database)
### In Memory Databases
Retrieving data from memory is much faster than retrieving data from disk
GCP Services:
- [Memory Store](memory_store.md): Caching, session management, gaming leader boards, etc...