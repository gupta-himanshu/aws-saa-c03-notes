# Security & Identity

## IAM
- Prefer IAM Roles over access keys.
- Root account should never have active access keys.

---

## AWS Organizations
- Use Service Control Policies (SCPs) to control services available to accounts.

---

## AWS STS
- Generates temporary credentials.

---

## AWS WAF
- Protects applications from common web vulnerabilities.
- Integrates with:
  - ALB
  - CloudFront

---

## Encryption

### Data at Rest
- EBS Encryption
- Server-Side Encryption
- Customer Managed KMS Keys

### Data in Transit
- SecureTransport bucket policies
- ACM Certificates

---

## Networking & Security

### Network ACLs (NACLs)
- NACLs are commonly used to block unwanted traffic at the subnet level.
- Since NACLs are stateless, rules must be configured in both inbound and outbound directions.
- NACLs are often preferred when explicit deny rules are required.
