# Amazon Elastic File System(EFS)
- Scalable file system used with AWS Cloud services and on-premises resources. 
- As you add and remove files, Amazon EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications.

## Comparing Amazon EFS and Amazon EBS
- An Amazon EBS volume stores data in a **single** Availability Zone. To attach an Amazon EC2 instance to an EBS volume, both the Amazon EC2 instance and the EBS volume must reside within the same Availability Zone.
- Amazon EFS is a regional service. It stores data in and across **multiple** Availability Zones. The duplicate storage enables you to access data concurrently from all the Availability Zones in the Region where a file system is located. Additionally, on-premises servers can access Amazon EFS using AWS Direct Connect.