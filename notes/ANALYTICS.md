# Analytics & Data Streaming

## Amazon Kinesis

### Data Streams
- Collect logs and streaming data.
- Scale by increasing shard count.

### Firehose
- Deliver streaming data into S3.
- Supports:
  - Transformation
  - Encryption

---

## CloudSearch
- Provides full-text search for data stored in S3.

---

## Amazon Redshift Enhanced VPC Routing

### Benefits
- Forces traffic between Redshift and other AWS services to stay within the VPC network.
- Improves security posture by avoiding unnecessary public network traversal.
- Commonly used with Amazon S3 for secure COPY and UNLOAD operations.
- Helps organizations meet network security and compliance requirements.
