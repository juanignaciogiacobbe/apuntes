# Amazon Relational Database Service(Amazon RDS)
- **Enables you to run relational databases in the AWS Cloud**.
- Managed service that **automates tasks such as hardware provisioning, database setup, patching, and backups**. 
- With these capabilities, **you can spend less time completing administrative tasks and more time using data to innovate your applications**. 
- You can integrate Amazon RDS with other services to fulfill your business and operational needs, such as using AWS Lambda to query your database from a [07A-Serverless Computing](../Module%202%20-%20Compute%20in%20the%20Cloud/07A-Serverless%20Computing.md)application.

## Amazon RDS database engines
- **Amazon RDS is available on six database engines**, which optimize for memory, performance, or input/output (I/O). Supported database engines include:
	- Amazon Aurora.
	- PostgreSQL.
	- MySQL.
	- MariaDB.
	- Oracle Database.
	- Microsoft SQL Server.

# Amazon Aurora
- **Enterprise-class relational database**. It is compatible with MySQL and PostgreSQL relational databases. **It is up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases**.
- **Helps to reduce your database costs by reducing unnecessary input/output (I/O) operations,** while ensuring that your database resources remain reliable and available.
- **Consider Amazon Aurora if your workloads require high availability**. It replicates six copies of your data across three Availability Zones and continuously backs up your data to [14B-Amazon Simple Storage Service(S3)](14B-Amazon%20Simple%20Storage%20Service(S3).md).