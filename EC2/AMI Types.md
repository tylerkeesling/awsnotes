# AMI Types

## You can select your AMI based on:
- Region (see Regions and Availability Zones)
- Operating System
- Architecture (32-bit or 64-bit)
- Launch Permissions
- Storage for the Root Device (Root Device Volume)
	- Instance Store (EPHEMERAL STORAGE)
	- EBS Backed Volumes

## EBS vs Instance Store
- All AMIs are categorized as either backed by Amazon EBS or backed by instance store
- For EBS Volumes:
	- The root device for an instance launched from the AMI is an Amazon EBS volume create from an EBS snapshot
- For Instance Store Volumes:
	- The root device for an instance launched from the AMI is an instance store volume created from a template stored in S3

- Instance Store Volumes are sometimes called Ephemeral Storage
- Instance store volumes cannot be stopped
	- If the underlying host fails, you will lose your data
- EBS backed instances can be stopped
	- You will not lise the data on this instance if it is stopped
- You can reboot both and will not lose data
- By default, both ROOT volumes will be deleted on termination, however with EBS volumes, you can tell AWS to keep the root device volume