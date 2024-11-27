# Amazon Simple Storage Service(S3)
- Provides **object-level storage**. -> **S3 stores data as objects in buckets**. 
- By default, buckets and their contents are private.
- Essentially unlimited storage that can hold millions of objects per bucket.
- **Regional service**, but bucket names must be globally unique.
- Durability: Objects are never lost or compromised.
- Availability: You can access your data quickly when you need it.
- You can set permissions to control visibility and access to the uploaded files. 
- You can also use the Amazon S3 versioning feature to track changes to your objects over time.
- You can set security at the bucket level or individual object level using access control lists (ACLs), bucket policies, or access point policies.

## Amazon S3 Storage Classes
- **You only pay for what you use.**
- When selecting an Amazon S3 storage class, you have to consider these two factors:
	- How often you plan to retrieve your data.
	- How available you need your data to be.

### S3 Standard
- Designed for **frequently accessed data**.
- Stores data in a minimum of three Availability Zones.
- Provides **high availability for objects**. This makes it a good choice for a wide range of use cases, such as websites, content distribution, and data analytics. 
- Amazon S3 Standard has a higher cost than other storage classes intended for infrequently accessed data and archival storage.

### S3 Standard-Infrequent Access(S3 Standard-IA)
- Ideal for **infrequently accessed data**.
- Similar to Amazon S3 Standard but has a lower storage price and higher retrieval price.
- **Ideal for data infrequently accessed but requires high availability when needed**. Both Amazon S3 Standard and Amazon S3 Standard-IA store data in a minimum of three Availability Zones. Amazon S3 Standard-IA provides the same level of availability as Amazon S3 Standard but with a lower storage price and a higher retrieval price.}

## S3 One Zone-Infrequent Access(S3 One Zone-IA)
- **Stores data in a single Availability Zone**.
- **Has a lower storage price than Amazon S3 Standard-IA**.
- This makes it a good storage class to consider if the following conditions apply:
	- You want to save costs on storage.
	- You can easily reproduce your data in the event of an Availability Zone failure.


## S3 Intelligent-Tiering
- Ideal for **data with unknown or changing access patterns**.
- **Requires a small monthly monitoring and automation fee per object**.
- Amazon S3 monitors objects’ access patterns.
- If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA. If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, S3 Standard.

## S3 Glacier Instant Retrieval
- Works well for **archived data that requires immediate access**.
- **Can retrieve objects within a few milliseconds**.
- You can retrieve objects stored in the S3 Glacier Instant Retrieval storage class within milliseconds, with the same performance as S3 Standard.

## S3 Glacier Flexible Retrieval
- **Low-cost storage designed for data archiving**.
- **Able to retrieve objects within a few minutes to hours**.
- For example, you might use this storage class to store archived customer records or older photos and video files. You can retrieve your data from S3 Glacier Flexible Retrieval from 1 minute to 12 hours.

## S3 Glacier Deep Archive
- **Lowest-cost object storage class ideal for archiving**.
- **Able to retrieve objects within 12 hours**.
- S3 Deep Archive supports long-term retention and digital preservation for data that might be accessed once or twice in a year.
- All objects from this storage class are replicated and stored across at least three geographically dispersed Availability Zones.

## S3 Outposts
- Creates S3 buckets on Amazon S3 Outposts.
- Makes it easier to retrieve, store, and access data on AWS Outposts.
- Amazon S3 Outposts delivers object storage to your on-premises AWS Outposts environment.
- Designed to store data durably and redundantly across multiple devices and servers on your Outposts.