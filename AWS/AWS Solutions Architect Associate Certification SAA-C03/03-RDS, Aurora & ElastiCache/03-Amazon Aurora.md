# Amazon Aurora
- Helps to reduce your database costs by reducing unnecessary input/output (I/O) operations, while ensuring that your database resources remain reliable and available.
- **Consider Amazon Aurora if your workloads require high availability**. It replicates six copies of your data across three Availability Zones and continuously backs up your data to [[AWS/AWS Cloud Practitioner CLF-C02/05-Storage and Databases/01-Amazon Simple Storage Service S3|S3]].



> [!IMPORTANT] Aurora Global Database
> Designed for globally distributed applications, allowing a single Amazon Aurora database to span multiple AWS regions. It replicates your data with no impact on database performance, enables fast local reads with low latency in each region, and provides disaster recovery from region-wide outages.


> [!IMPORTANT] Amazon Aurora
> - It is compatible with MySQL and PostgreSQL relational databases. 
> - **Up to 5x faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases**.
> - Failover is instantaneous -> It's High Availability native.


![[AWS/AWS Solutions Architect Associate Certification SAA-C03/img/Pasted image 20241202131417.png]]


> [!NOTE] Features of Aurora
- Automatic Failover.
- Backup and Recovery.
- Isolation and Security.
- Industry Compliance.
- Push-Button scaling.
- Automated Patching with Zero Downtime.
- Advanced Monitoring.
- Routine Maintenance.
- Backtrack: Restore data at any point of time without using backups.

![[AWS/AWS Solutions Architect Associate Certification SAA-C03/img/Pasted image 20241202131825.png]]


> [!IMPORTANT] Aurora Custom Endpoints
> - Define a subset of Aurora Instances as a Custom Endpoint.
> - The Reader Endpoint is generally not used after defining Custom Endpoints.

---

> [!IMPORTANT] Aurora Serverless
> - Automated database instantiation and autoscaling based on actual usage.
> - Good for infrequent,intermittent of unpredictable workloads.
> - No capacity planning needed.
> - Pay per second, can be more cost-effective.

![[AWS/AWS Solutions Architect Associate Certification SAA-C03/img/Pasted image 20241202132125.png]]