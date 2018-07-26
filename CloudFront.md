# CloudFront

### What is a CDN?
A CDN (content delivery network) is a system of distributed servers (a network) that deliver webpages and other web content to a user based on the geographic locations of the user, the origin of the webpage, and a content delivery server.

### What is an Edge Location?
This is the location where the content will be cached. This is separate to an AWS Region/AZ.
- Edge locations are not just for READ only, you can write to them too.
- Objects are cahed for the life of the TTL (Time To Live)
- You can clear cached objects, but you will be charged.

### What is a Regional Edge Cache
- They are Edge Locations with more cache width
- If less popular content is pushed out of the Edge Location cache, it is stored in a Regional Edge Cache
- This reduces the need for CloudFront to go back to the S3 origin and optimizes transfer times
- Regional edge cache locations are currently used only for requests that need to go back to a custom origin
- If a request is going to an S3 origin, it will skip regional edge cache locations

### What is a Point of Presence?
- (121) Edge Locations and (11) Regional Edge Caches
- 59 cities across 26 locations

### What is an Origin?
This is the origin of all the files that the CDN will distribute. Theis can be either an **S3 Bucket**, an **EC2 Instance**, an **Elastic Load Balancer**, or **Route53**.

### What is a Distribution?
This is the name given to the CDN which consists of a collection of Edge Locations.

### Types of Distributions
#### Web
- Typically used for websites

#### RTMP
- Used for media streaming
- Specifically for Adobe Flash


#### Restrictions
Enable Geo-Restrictions. You can either whitelist or blacklist countries. You cannot do both.

#### Invalidations
- Invalidating objects removes them from CloudFront edge caches.
- A faster and less expensive method is to use versioned object or directory names.
- Instead of waiting the 24 hours for the TTL, you can create an invalidation to remove the object now
	- This costs money

### How long will CloudFront keep files
- If no cache control header is set, the edge location will check for an updated version from the origin if it has been longer than 24 hours since the last update/check
	- This is called the expiration period
- Cache control headers determine how frequently it needs to check the origin for an updated version
- 0 sec expiration dates will revalidate every request with the origin server