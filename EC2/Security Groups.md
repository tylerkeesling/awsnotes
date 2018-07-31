# Securtiy Groups
- Any rules you apply to a security group apply immediately
- Security Groups are *stateful*
	- Inbound rules will automatically apply its outbound rules

- All inbound traffic is blocked by default
- All outbound traffic is allowed by default
- Changes to Security Groups are applied immediately
- You can have any number of EC2 instances within a security group
- You can have multiple sucurity goups attached to EC2 Instances
- Securuty Groups are **STATEFUL**
	- If you create an inbound rule allowing traffic in, that traffic is authomattically allowed back out again
- You cannot block specific IP addresses using Security Groups, insread use Network Access Control Lists
- You can specifiy allow rules, but not deny rules