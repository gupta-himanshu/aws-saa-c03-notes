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
