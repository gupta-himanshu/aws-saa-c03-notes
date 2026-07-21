# AWS Study Notes & Architecture Best Practices

## Compute Services

### EC2
- Use **Instance Profiles (IAM Roles)** instead of hardcoded credentials.
- Spot Instances are ideal for interruptible and non-critical workloads.
- Improve fault tolerance by using:
  - Multiple EC2 instances
  - Auto Scaling Groups (ASG)
- User Data can be used to execute initialization scripts.
- For development environments, prefer Spot Instances and Free Tier resources.

### Auto Scaling Groups (ASG)
- If scaling is not occurring:
  - Verify scaling thresholds.
  - Verify scaling policies.
  - Check EC2 service limits.
- Scheduled Actions are useful when future capacity requirements are known in advance.

### AWS Lambda
- Best for stateless applications.
- SDK clients should be created outside the handler function.
- Useful for administration and automation jobs.
- Retries failed events automatically.
- No DLQ is configured by default.

### AWS Step Functions
- Orchestrates AWS services using state machines.
- Supports:
  - Error handling
  - Retries
  - Parallel execution

### Elastic Beanstalk
- Supports Docker-based deployments.
- Faster deployment of 3-tier applications than building CloudFormation templates manually.

### ECS & Fargate
- ECS Task Definitions contain:
  - Image
  - CPU/Memory
  - Environment variables
  - Logging
  - Health checks
  - Secrets
- ECS on EC2 allows mixing Reserved and Spot Instances.
- Use IAM Roles for Tasks for container isolation.
- AWS Fargate enables container execution without managing EC2 servers.

---

# EC2 Placement Groups

Placement Groups influence performance, fault tolerance, and availability of EC2 workloads.

## Cluster Placement Group

### Characteristics
- Instances are located close together within a single Availability Zone.
- Designed for very low network latency and high network throughput.

### Best Use Cases
- High Performance Computing (HPC)
- Machine Learning workloads
- Scientific simulations
- Low-latency distributed systems

### Primary Goal
- Maximum performance.

---

## Partition Placement Group

### Characteristics
- Instances are distributed across logical partitions.
- Each partition has isolated networking, power, and hardware resources.

### Best Use Cases
- Hadoop
- Kafka
- Cassandra
- Large distributed data-processing systems

### Primary Goal
- Performance with fault isolation at scale.

---

## Spread Placement Group

### Characteristics
- Each instance is placed on distinct underlying hardware.
- Minimizes the risk of simultaneous hardware failures.

### Best Use Cases
- Mission-critical applications
- High-availability architectures
- Small groups of sensitive workloads

### Primary Goal
- Maximum availability and fault tolerance.

---

## Placement Group Summary

| Placement Group | Primary Goal | Placement Strategy | Best For |
|----------------|-------------|-------------------|----------|
| Cluster | Performance | Instances close together in one AZ | HPC, ML, low-latency applications |
| Partition | Fault Isolation + Performance | Separate partitions | Hadoop, Kafka, Cassandra |
| Spread | Availability | Separate hardware per instance | Critical workloads, HA systems |

### Quick Rule of Thumb

- **Cluster** = Maximum Performance
- **Partition** = Performance + Fault Isolation
- **Spread** = Maximum Availability
