
> [!IMPORTANT] [Amazon S3](AWS/Cloud%20Practitioner%20(CLF-C02)/05-Storage%20and%20Databases/01-Amazon%20Simple%20Storage%20Service(S3).md): Moving between Storage Classes
> - You can transition object between storage classes.
> 	- For infrequently accessed object, move them to Standard IA.
> 	- For archive objects that you don't need fast access to, move them to Glacier or Glacier Deep Archive.
> - Moving objects can be automated using a Lifecycle Rules.

![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241203103038.png)



> [!IMPORTANT] Amazon S3 Lifecycle Rules
> - Transition Actions: Configure objects to transition to another storage class
> 	- Move objects to Standard IA class 60 days after creation.
> 	- Move to Glacier for archiving after 6 months.
> - Expiration Actions: Configure objects to expire(delete) after some time
> 	- Access log files can be set to delete after a 365 days.
> 	- Can be used to delete old versions of files(if versioning is enabled).
> 	- Can be used to delete incomplete Multi-Part uploads.
> - Rules can be created to a certain Prefix or for certain objects Tags.


> [!IMPORTANT] Amazon S3 Analytics - Storage Class Analysis
> - Help you decide when to transition objects to the right storage class.
> - Recommendations for Standard and Standard IA(Does NOT work for One-Zone IA or Glacier).
> - Report is updated daily.
> - 24 to 48 hours to start seeing data analysis.