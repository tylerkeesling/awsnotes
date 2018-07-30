# S3 Labs

## Create an S3 Bucket

- Handle buckets globally
- DNS namespace for buckets (web address)
- By default, all buckets are private
- Encryption - Client Side Encryption - Server Side Encryption - SSE with Amazon S3 Managed Keys (SSE-S3) - SSE with KMS (SSE-KMS) (did not cover) - SSE with Customer Provided Keys (SSE-C)
- Control access to buckets using either a bucket ACL (Access Control Log) or using Bucket Policies
- By default, buckets are private and all objects stored inside of them are private

## Versioning

- Stores all versions of an object (including all writes and even if you delete an object)
- Objects stored in bucket before versioning have a version ID of _null_
- When versioning is enabled, the objects do not change but the way S3 handles the objects does
- Great backup tool
- Buckets can be in one of three states: - unversioned (the default) - versioning-enabled - versioning-suspended
- Once enabled, Versioning _cannot be disabled, only suspended_
- Integrates with **Lifecycle rules** - Object expiration policy - If you have an object expriation lifecycle polocy in your non-versioned bucket and you want to maintain the same permanent delete behavior when you enable versioning, you must add a noncurrent expiration policy - The noncurrent expiration policy will manage the dletes of the noncurrent object versions in the version-anbled bucket - A version-enabled bucket maints one current and zero or more noncurrent object versions - Transition to one type of storage to another
- Versioning's MFA Delete capability can be used to provide an additional layor of security
- When versioning

## Cross Region Replication

- Versioning must be enabled on both the source and destination buckets
- Regions must be unique
- Files in an existing bucket are not replicated automatically - Easiest way to replicate is via the command line - `aws s3 copy s3://bucketToCopySource s3://bucketToCopyDestination` - All subsequent updated files will be replicated automatically
- You cannot replicate to mulitple buckets or use daisy chaining (at this time)
- Delete markers are replicated
- Deleting individual versions or delete markets will not be replicated
- Understand what Cross Region Replication is at a high level

## Lifecycle Management

- Can be used in conjunction with versioning
- Can be applied to current versions and previous versions
- Can transfer to Standard-IA after 30 days as (Standard)
- Can transfer to Glacier after 30 days as (Standard-IA)
- Can transfer to Glacier after any days if object is transferred to One Zone-IA
- Following actions can now be done: - Transition to the Standard - Infrequent Access Storage Class (30 days after the creation date) - Archive to the Glacier Storage Class (30 days after IA, if relevant) - Permanently delete
- Actions performed by lifecycle configuration are not replicated in CRR

## Host a Static Website

- Within a bucket, go to **Properties**
- You will see _Static website hosting_ as one option
- You can do three things:
  1.  _Use this bucket to hose a website_
  2.  _Redirect requests_
  3.  _Disable website hosting_

The bucket name must be the name of the website if you want to use it to host a static website.
