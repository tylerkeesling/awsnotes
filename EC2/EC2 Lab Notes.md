# EC2 Lab Summary
- Termination Protection is turned off by default and you must turn it on
- On an EBS-backed instance, the default action is for the root EBS volume to be deleted when the insance is terminated
- EBS Root Volumes of your DEFAULT AMI's cannot be encrypted
	- You can use a third party tool (such as bit locker) to encrypt the root volume
	- This can be done in the AWS console or using the API
- Additional volumes can be encrypted