# Identity Access Management (IAM)
Managing identity across the AWS cloud

### What is IAM?
> IAM allows you to manage users and their level of access to the AWS Console. It is important to understand IAM and how it works, both for the exam and for administrating a company's AWS account in real life.

### Functionality
AWS IAM allows you to:
- Manage IAM users and their access
	- You can create users in IAM
	- Assign them individual security credentials (access keys, passwords, MFA)
	- Request temp security credentials to provide users access to AWS services and resources
	- Manage permissions in order to control which operations a user can perform

- Manage IAM roles and their permissions
	- Create roles in IAM and manage permissions to control which operations can be performed by the entity
	- Define which entity is allowed to assume a role
	- Use service-linked roles to deletegate permissions to AWS services that create and manage AWS resources on your behalf

- Manage federated (logged on and identified through FB or LinkedIn, etc) and their permissions
	- Enable identity federation to allow existing identities (users, groups, and roles) to access AWS

### What are Users?
- Users are *people or resources* who need access to AWS resources
- They can be:
	- Privedged admins who need console acces to manage your AWS
	- End users who need acces to content in AWS
	- Systems that need privileges to programmatically access data in AWS

### What are Groups
- A collection of users under one set of permissions

### What are Roles?
- Roles allow one to delegate access to *users or services* that normally don't have access to AWS resources
- Users or AWS Services can assume roles based on temporary security credentials

## What does IAM give you?
* Centralised control of your AWS account
* Shared access to your AWS account
* Granular Permissions
* Identity Federation (log in with FB or LinkedIn)
* MFA
* Give users temp access for devices and services
* Password rotation policy
* Integrates with AWS services
* Supports PCI DSS Compliance

### Critical Terms:
* **Users** - End Users (think people)
* **Groups** - A collection of users under one set of permissions
* **Roles** - You create roles and can then assign them to AWS resources
* *Policies* - A document that defines one or more permissions (in JSON)
	* Sits on top of Users, Groups, and Roles

Root Account is the email address assigned to the account.

Two types of access:
1. Programmatic Access
	1. For like storing
2. AWS Management Console Access

What is a IAM role?
* Roles are a secure way to grant permissions to entities that you trust
* UAN yser ub abitger account
* Application code running on an EC2 instance that needs to perform actions on AWS resources
* An AWS service that needs to act on resources in your account to provide its features
* Users from a corporate directory who use identity federation with SAML

Creating a billing alarm
* Bill goes over a certain threshold and it sends you a notification

* IAM is universal. It does not apply to regions.
* The root account is the account created when first setup your AWS account. It has complete Admin access
* New users have no permissions
* New users are assigned Access Key ID & Scret Access keys
* These are not the same as passwords and cannot use them to Login to the console. It can be used for access in AWS APIs or CLI
* Only get the credentials once
* Always have to set up MFA on root acccount
* Create and customize password and password rotation policies
* Root account has `Administrator Access`
* `Power User Access` is access to all AWS services except the management of groups and users within IAM
* You can implement MFA for all accounts


