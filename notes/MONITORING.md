# Monitoring & Logging

## CloudWatch Logs
- Central repository for application logs.

## CloudTrail
- Records AWS API activity.

## EventBridge
- Capture AWS events and trigger workflows.

### Example
Track EC2 restarts:
1. CloudTrail → EventBridge → Lambda → Database
2. EventBridge → Lambda → Database
