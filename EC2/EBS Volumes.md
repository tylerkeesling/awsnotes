# EBS Volume Lab Notes

## Volume vs Snapshot
- Volumes exist on EBS
	- Virtual HDD
	- Where your OS is installed
- Snapshots exist on S3
	- Point in time copy of a Volume
	- They are incremental - this means that only the blocks that have changed since your last snapshot are moved to S3

- To create a snapshot for an EBS volume that serve as root devices, you should stop the instance before taking the snapshot
- However, you can take the snapshot while it is running
- You can create AMI's from EBS-backed Instances and Snapshots
- You can change EBS volume sizes on the fly, including changing the size and storage type
- Volumes **will always** be in the same AZ as the EC2 instance
- To move an EC2 volume from one AZ/Region to another, take a snapshot or an image of it, then copy it to the new AZ/Region

- Snapshots of encrypted volumes are encrypted automatically
- Volumes restored from encrypted snapshots are encrypted automatically
- You can share snapshots, but only if they are unencrypted
	- These snapshots can be shared with other AWS accounts or made public


- Snapshots of encrypted volumes are encrypted automatically
- VOlumes restored from encrypted snapshots are encrypted automattically
- Snapshots, to be shared, must be unencrypted