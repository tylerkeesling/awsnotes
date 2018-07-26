# Storage Gateway

### What is AWS Storage Gateway?
It is a service that connects an on-premises software appliance with cloud-based storage to provide seamless and secure integration between an organization's on-premises IT environment and AWS's storage infrastructure. The service enables you to securely store data to the AWS cloud for scalable and cost-effective storage.
<br>

AWS Storage Gateway's software appliance is available for download as a VM image that you install on a host in your datacenter. SG supports either VMware ESXi or Microsoft Hyper-V. Once you've installed your gateway and associated it with your AWS account through the activation process, you can use the AWS Management Console to create the storage gateway option.

### The Four Types of Storage Gateways
1. **File Gateway (NFS Network File System or SMB)**
   - Files are stored as objects in S3 Buckets
   - Can only store flat files (PDFs, word files, images, media content, etc)
   - Ownership, permissions, and timestamps are stored in user-metadata
   - Once stored in S3, can be managed as native S3 objects (versioning, lifecycle, etc)
2. **Volume Gateway (iSCSI)*
  - The volume gateway interface presents your applications with disk volumes using the iSCSI *block* protocol
  - Things stored here are block based files (operating systems, etc)
  - Data written here are asynchronously backed up as point-in-time snapshots of your volumes
  - They are stored as EBS (Elastic Block Store) snapshots
  - Snapshots are incremental backups that capture only changed blocks
  - Snapshots storage is compressed to minimize your storage changes
	1. **Stored Volumes**
		- Allows you to store data locally, while asychronously backing up that data to AWS
		- On-premises applications have low-latency access to their entire datasets with offsite backups
		- A complete copy of the data is onsite
		- Stored on a virtual disk
		- Stored in the form of EBS
		- 1gb to 16tb in size for Stored Volumes
	2. **Cached Volumes**
		- Use S3 as your primary data storage
		- More frequently used data cached locally
		- 1gb to 32tb in size for Cached Volumes
3. **Tape Gateway (VTL)**
   - Tapes are mostly used for archival purposes
   - The VTL interface provides an interface to transfer phyiscal tape infrastructure to virtual tapes in **Glacier**
   - Each tape gateway is preconfigured with a media changed and tape drives
   - You can add tape cartridges as you need to achrive your data
   - Supported by NetBackup, Backup Exec, Veeam, etc

### Review
- File Gateway
	- For flat files, stored directly on S3
	- Not for operating systems
- Volume Gateway:
	- Stored Volumes
		- Entire dataset is stored on site and is backed up to S3
	- Cached Volumes
		- Entire dataset is stored on S3
		- Most frequently accessed data is cached on site
- Gateway Virtual Tape Library (VTL)
	- Used for backup and uses popular backup applications like NetBackup, etc