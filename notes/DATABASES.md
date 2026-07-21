# Databases

## Amazon RDS

### Multi-AZ
- Improves availability.
- Creates synchronous standby.

### Read Replica
- Improves read performance.
- Asynchronous replication.

### Cross-Region Read Replica
- Helps protect against regional outages.

### Parameter Groups
- Useful for database configuration tuning.
- Can address maximum connection issues.

---

## Amazon Aurora
- Highly scalable.
- MySQL compatible.
- High performance and fault tolerant.

---

## DynamoDB

### Features
- Fully serverless.
- No infrastructure maintenance.

### Streams
- Captures real-time table changes.
- Can trigger Lambda functions.

### Capacity Modes
- Use On-Demand mode for sudden workload increases.

### Hot Partition Resolution
- Add randomness to partition keys.

---

## ElastiCache
Supports:
- Redis
- Memcached

Common use cases:
- Gaming
- IoT
- High-speed caching

---

## Amazon Redshift

### Cost Optimization
- Delete unused manual snapshots.
- Reduce snapshot retention period.

### Disaster Recovery
- Use snapshot schedules.
- Replicate snapshots to another region.
