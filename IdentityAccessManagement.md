# Identity Access Management (IAM)

IAM enables one to securely control access to AWS services and resources for your users. <br>
Using IAM, you can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources.

* Manage IAM users and their access. You can create users in IAM, assign them to individual security credentrials (access keys, passwords, and MFA), or request temp security credentials to provide users access to AWS services and resources. You can manage permissions in order to control which operations a user can perform
* Manage IAM roles and their permissions. You can create roles in IAM and manage permissions to control which operations can be performed by the entity, or AWS service, that assumes the role. you can also define which entity is allowed to assume the role
* Manage federated users and their permissions. you can enable identity federation to allow exisiting identities (users, groups, and roles) in your enterprise to access the AWS Management Console, call AWS APIs, and access resources, w/o the need to create an IAM user for each identity

## What is IAM?
> Iam allows you to manage users and their level of access to the AWS Console. It is important to understand IAM and how it works, both for the exam and for administrating a company's AWS account in real life.

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
* Users - End Users (think people)
* Groups - A collection of users under one set of permissions
* Roles - You create roles and can then asign them to AWS resources
* Policies - A document that defines one or more permissions (JSON)
	* Sits on top of Users, Groups, and Roles

Root Account is the email address assigned to the account.

Two types of access:
1. Programmatic Access
	1. For like storing
2. AWS Management Console Access

ACCESS KEY JbPzl9CAZBkhXXnKL+NfHYaUJrZUgF6GyXIn1Mr0
PW 9E9ZoSZhLWR]

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
* New ueser have no permissions
* New users are assigned Access Key ID & Scret Access keys
* These are not the same as passwords and cannot use them to Login to the console. It can be used for access in AWS APIs or CLI
* Only get the credentials once
* Always have to set up MFA on root acccount
* Create and customize password and password rotation policies
* Root account has `Administrator Access`
* `Power User Access` is access to all AWS services except the management of groups and users within IAM
* You can implement MFA for all accounts
