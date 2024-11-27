
> [!IMPORTANT] Elastic File System(EFS)
> - Managed NFS(network file system) that can be mounted on many [EC2](AWS/Cloud%20Practitioner%20(CLF-C02)/02-Compute%20in%20the%20Cloud/04A-Amazon%20Elastic%20Compute%20Cloud(EC2).md).
> - Works with EC2 instances in Multi-[AZ](AWS/Cloud%20Practitioner%20(CLF-C02)/03-Infrastructure%20and%20Realiability/08B-Availability%20Zones.md).
> - Highly available, scalable, expensive, pay per use.
> - Uses NFSv4.1 protocol.
> - Uses security group to control access to EFS.
> - Compatible with Linux based [AMI](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/02-EC2%20Instance%20Storage/02-AMI.md)(Not Windows).
> - Encryption at rest using KMS.
> - Use cases: Content management, web serving, data sharing, Wordpress.

![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241105095901.png)

# EFS Performance & Storage Classes
- EFS Scale:
	- 1000s of concurrent NFS clients, 10GB+ /s throughput.
	- Grow to Petabyte-scale NFS, automatically.
- Perfomance Mode(Set at EFS creation time)
	- General Purpose(default) - latency-sensitive cases(web server, CMS, etc ...)
	- Max I/O - Higher latency, throughput, highly parallel
- Throughput Mode
