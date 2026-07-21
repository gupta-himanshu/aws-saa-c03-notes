# Content Delivery

## CloudFront
- Caches static content at edge locations.
- Enable access logs and CloudTrail logging for monitoring.

---

## CloudFront Distribution Configuration

### Origin Configuration
- Every CloudFront distribution requires an origin to be specified.
- The origin represents the backend location where content is stored, such as:
  - Amazon S3
  - Application Load Balancer (ALB)
  - EC2-hosted web application
  - Custom HTTP/HTTPS endpoint
- CloudFront retrieves content from the configured origin and caches it at edge locations.
