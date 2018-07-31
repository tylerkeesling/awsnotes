# EC2 Lab Summary
- Termination Protection is turned off by default and you must turn it on
- On an EBS-backed instance, the default action is for the root EBS volume to be deleted when the insance is terminated
- EBS Root Volumes of your DEFAULT AMI's cannot be encrypted
	- You can use a third party tool (such as bit locker) to encrypt the root volume
	- This can be done in the AWS console or using the API
- Additional volumes can be encrypted
- When an instance is terminated the instance is stopped and its resources are released

## Status Checks
- System Status Checks
	- Verifies that the instance is reachable
	- Are able to get network packets to your instance
- Instance Status Checks
	- Verifies that your instance's OS is accepting traffic



## AMI Amazon Machine Image
Provides the information required to launch an instance which is a virtual server in the cloud.
- A tmeplate for the root volume for the instance (ie an OS or app server)
- Launch permissions that control which AWS accounts can use the AMI to launch instances
- A block device mapping that specifies the volumes to attach to the instance when launched

