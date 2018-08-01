# Elastic Load Balancers
Balances a load around to various web servers

## The three types of ELB's
1. `Application Load Balancers`
   - Best suited for load balancing of HTTP and HTTPS traffic
   - They operate at *Layer 7* and are application-aware
   - They are intelligiesnt and you can create advanced request routing, sending specified requests to specific web servers
2. `Network Load Balancers`
   - Best suited for loading balancing of TCP traffic where extreme performance is required
   - Operates at the connection level, *Layer 4*
   - Capable of handinglg millions of requests per second
   - Maintains ultra-low latencies
   - Extreme performance!
3. `Classic Load Balancers`
   - Legacy Elastic Load Balancers
   - What Amazon still refers to as ELB's
   - You can load balance HTTP/HTTPS apps and use Layer 7-specific features
   - Features include X-Forwarded and sticky sessions
   - Can also use strict Layer 4 load balancing for apps that rely on purely the TCP protocol

## Load Balancer Errors
- `Classic Load Balancers`
	- If app stops responding, the ELB responds with `504 error`
	- This means that the app is having issues
	- It could be at the Web Server layer or at the Database layer
	- Identify where the app is failing and scale it up or out where possible

## X-Forwarded-For Header
- User IP address connects to load balancer
- Load balancer connects to EC2 instance
- EC2 instance sees ELB IP address and not user
- *X-Forwarded-For* Header on the ELB sends the User IP address

## ELB Exam Tips
- Three types of Load Balancers
	- `Application LB`
	- `Network LB`
	- `Classic LB`
- `504 Error` means the g*ateway has timed out*
	- The app is not repsonding within the idle timeout period
	- Troubleshoot -> *is it Web Server or Database*?
- *If you need IPv4 address* of end user, look for `X-Forward-For header`