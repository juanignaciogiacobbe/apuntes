# Storage Layer
- Persistent and infinitely scalable cloud storage residing in cloud providers blob storage service, such as [[AWS/AWS Cloud Practitioner CLF-C02/05-Storage and Databases/01-Amazon Simple Storage Service S3|AWS S3]].
- Snowflake users by proxy get the availability & durability guarantees of the cloud providers blob storage.
- Data loaded into Snowflake is organized by databases, schemas and accessible primarily as tables.
- Both structured and semi-structured data files can be loaded and stored in Snowflake.

## What is Snowflake storing in blob storage when data is loaded into a table?
- When data files are loaded or rows inserted into a table, Snowflake reorganizes the data into its proprietary compressed, columnar table file format.
- The data that is loaded or inserted is also partitioned into what Snowflake call micro-partitions.
- Storage is billed by how much is stored based on a flat rate per TB calculated monthly.
- Data is not directly accessible in the underlying blob storage, only via SQL commands.