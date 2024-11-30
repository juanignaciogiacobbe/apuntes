> [!IMPORTANT] Elastic Block Store(EBS) Volume
> - A network drive you can attach to your instances while they run. -> It uses the network to communicate to the instance, which means there might be a bit of [latency](Redes/Chapter%201/03-Delay,%20Loss%20and%20Throughput.md).
> - It allows your instances to persist data, even after their termination.
> - They can only be mounted to one instance at a time.
> - They are bound to a specific [Availability Zone](AWS/Cloud%20Practitioner%20(CLF-C02)/03-Infrastructure%20and%20Realiability/08B-Availability%20Zones.md).
> - Have a provisioned capacity -> You get billed for all the provisioned capacity, and you can increase the capacity of the drive over time.


![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241105084929.png)

# Delete on Termination attribute
- Controls the EBS behaviour when a [EC2](AWS/Cloud%20Practitioner%20(CLF-C02)/02-Compute%20in%20the%20Cloud/04A-Amazon%20Elastic%20Compute%20Cloud(EC2).md) instance terminates.
	- By default, the root EBS volume is deleted(attribute enabled).
	- By default, any other attached EBS volume is not deleted(attribute disabled).
- This can be controlled by the AWS console/ AWS CLI.
- Use case: Preserve root volume when instance is terminated.

![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241105085254.png)



> [!IMPORTANT] EBS Snapshots
> - Make a backup(snapshot) of your EBS volume at a point in time.
> - Not necessary to detach volume to do snapshot, but recommended.
> - Can copy snapshots across AZ or Regions.

![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241105090036.png)

# EBS Snapshots Features

> [!IMPORTANT] EBS Snapshot Archive
> - Move a Snapshot to an "archive tier" that is 75% cheaper.
> - Takes within 24 to 72 hours for restoring the archive.

![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241105090310.png)



> [!IMPORTANT] Recycle Bin for EBS Snapshots
> - Setup rules to retain deleted snapshots so you can recover them after an accidental deletion.
> - Specify retention(from 1 day to 1 year).

![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241105090442.png)

> [!IMPORTANT] Fast Snapshot Restore(FSR)
> - Force full initialization of snapshot to have no latency on the first use.


# EBS Volume Types

> [!IMPORTANT] General Purpose SSD 
> - Cost effective storage, low-latency.
> - System boot volumes, Virtual desktops, Development and test environments.
> - gp3: Baseline of 3000 IOPS and throughput of 125 MiB/s. Can increase IOPS up to 16000 and throughput up to 100MiB/s independently. 
> - gp2: Small gp2 volumes can burst IOPS to 3000. Size of the volume and IOPS are linked, max IOPS is 16000. 3 IOPS per GB, means at 5334 GB we are at the max IOPS.


> [!IMPORTANT] Provisioned IOPS(PIOPS) SSD
> - Critical business aplications with sustained IOPS performance or applications that need more than 16000 IOPS.
> - Great for databases workloads(sensitive to storage perf and consistency).
> - Supports EBS multi-attach.



> [!IMPORTANT] Hard Disk Drives(HDD)
> Cannot be a boot volume.
> 


![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241105094154.png)


> [!IMPORTANT] EBS Multi-Attach - io1/ io2 Family
> - Attach the same EBS volume to multiple EC2 instances in the same AZ.
> - Each instance has full read & write permissions to the high-performance volume.
> - Use case: Achieve higher application availability in clustered Linux applications. Applications must manage concurrent write operations.


![](AWS/AWS%20Solutions%20Architect%20Associate%20Certification%20SAA-C03/img/Pasted%20image%2020241105094356.png)


# EBS Encryption
- When you create an encrypted EBS volume, you get the following:
	- Data at rest is encrypted inside the volume.
	- All the data in flight moving between the instance and the volume is encrypted.
	- All Snapshots are encrypted.
	- All volumes created from the snapshot.
- Encryption and decryption are handled transparently(you have nothing to do).
- Encryption has a minimal impact on latency.
- EBS Encryption leverages keys from KMS(AES-256).
- Copying an unencrypted snapshot allows encryption.
- Snapshots of encrypted volumes are encrypted.