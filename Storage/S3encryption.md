# S3 Security & Encryption
- Be default, all newly created buckets are *private*
- You can setup access control to your buckets using:
	- Bucket Policies
		- Bucket wide; permissions applied bucket wide
	- Access Control Lists
		- Drill down to individual objects
- S3 buckets can be configured to create access logs which log all requests made to the S3 bucket. This can be done to another bucket.

### Encryption for S3
- In Transit
	- **SSL**, or Secure Sockets Layer
		- Encrypts data transferred between users and sites, or two systems
	- **TLS**, or Transport Layer Security
		- Updated, more secure, version of SSL
- At Rest
	- Server side encryption
		1. S3 Managed Keys - **SSE-S3** AES256 encryption (most common)
		2. AWS Key Management Service, Managed Keys - **SSE-KMS**
			- Comes with additional benefits
			- Separate permissions for an Envelope Key
				- A key that protects your datas encryption key
			- Audit trail of key usage
			- Can create and manage encryption keys yourself
		3. SSE with Customer Provided Keys - **SSE-C**
			- You manage encyption keys
			- Amazon manages encryption
	- Client Side Encryption