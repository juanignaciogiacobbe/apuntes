
> [!IMPORTANT] Scalability
> Involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in. 
> - You don’t have to worry about a lack of computing capacity to meet your customers’ needs.

> [!WARNING] Kinds of Scalability
> - Vertical Scalability -> Increasing the size of the instance. There's usually a limit to how much you can vertically scale(hardware limit).
> - Horizontal Scalability -> Increasing the number of instances/systems for your application. It's easy to horizontally scale thanks the Cloud offerings.


> [!NOTE] High Availability
> Running your application/system in at least 2 Data Centers(== [Availability Zones](AWS/Cloud%20Practitioner%20(CLF-C02)/03-Infrastructure%20and%20Realiability/02-Availability%20Zones.md)).
> - It's goal is to survive a data center loss.


> [!IMPORTANT] Amazon [EC2](AWS/Cloud%20Practitioner%20(CLF-C02)/02-Compute%20in%20the%20Cloud/01-Amazon%20Elastic%20Compute%20Cloud(EC2).md) Auto Scaling
> - Enables you to automatically add or remove Amazon EC2 instances in response to changing application demand. -> You can maintain a greater sense of application availability.


> [!IMPORTANT] Auto Scaling Group
> - Scale out to match an increased load.
> - Scale in to match a decreased load.
> - Ensure we have a minimum and a maximum number of EC2 instances running.
> - Automatically register new instances to a load balancer.
> - Re-create an EC2 instance in case a previous one is terminated.

![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241202122835.png)


> [!WARNING] Auto Scaling Group Attributes
- Launch Template:
	- [AMI](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/02-EC2%20Instance%20Storage/02-AMI.md) + Instance Type.
	- EC2 User Data.
	- [EBS](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/02-EC2%20Instance%20Storage/01-EBS.md) Volumes.
	- Security Groups.
	- SSH Key Pair.
	- IAM Roles for the EC2 instances.
	- Network + Subnets Information.
	- [Load Balancer](AWS/Cloud%20Practitioner%20(CLF-C02)/02-Compute%20in%20the%20Cloud/02-Elastic%20Load%20Balancing(ELB).md) Information.
- Min Size / Max Size / Initial Capacity.
- Scaling Policies.

> [!PDF|yellow] [AWS Certified Solutions Architect Slides v39, p.155](AWS/Slides/AWS%20Certified%20Solutions%20Architect%20Slides%20v39.pdf#page=155&selection=8,0,12,27&color=yellow)
> > Auto Scaling - CloudWatch Alarms & Scaling



> [!IMPORTANT] Auto Scaling Instance Refresh
> Update launch template and then re-creating all EC2 instances.
> - Setting of minimum healthy percentage.
> - Specify warm-up time(how long until the instance is ready to use).

![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241204092509.png)