# EC2 Placement Groups

- If the exam mentions a placement group, it is a clustered placement group
- 

## Two Types of Placement Groups

### Clustered Placement Group
- A cluster pg is a grouping of instances within a *single* Availability Zone 
- PG's are recommended for applications that need:
  - Low network latency,
  - High network throughput,
  - or both
- Only certain instances can be launched into a Clustered Placement Group

### Spread Placement Group
- A spread placement group is a group of instances that are each placed on *distinct* underlying hardware
- SPG's are recommended for applications that have a small number of critical instances that should be separate from each other

## Exam tips
- If the exam mentions a placement group, it is a clustered placement group
- CPG's cannot span multiple AZ's, whereas SPG's can
- The name of a PG must be unique within your AWS account
- Only certain types of instances can be launched in a placement group
  - Compute Optimized
  - GPU
  - Memory Optimized
  - Storage Optimized
- AWS recommends homogenous instances within PG's
  - The instance size and family should be the same
- PG's cannot be merged
- An existing instance cannot be moved into a PG
  - To do this, one would create an AMI from your existing instance
  - Then launch the instance from the AMI into a PG