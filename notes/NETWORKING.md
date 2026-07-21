# Networking

## VPC

### Internet Access
To access EC2 instances from the internet:
- Internet Gateway (IGW) attached to VPC.
- Route `0.0.0.0/0` pointing to IGW.
- Public subnet configuration.

### NAT Gateway
- Enables outbound internet access for private subnets.
- Blocks inbound traffic.
- Must be deployed in a public subnet.
- Requires Elastic IP.

### Transit Gateway
- Centralizes connectivity and monitoring across multiple VPCs.

### Direct Connect
- Provides dedicated connectivity from on-premises to AWS.
- Can be combined with VPN for secure communication.

### Site-to-Site VPN
Requires:
- Virtual Private Gateway (VPG)
- Customer Gateway with public IP

---

## Security Groups vs NACLs

### Security Groups
- Stateful.
- Allow only required traffic.
- Application isolation through inbound rules.

### NACLs
- Stateless.
- Rules must exist in both directions.
- Used to block specific IP addresses.

---

## Route 53

### Routing Policies
- Latency
- Weighted
- Geolocation
- Geoproximity

### Health Checks
- Can monitor public resources both inside and outside AWS.

### Failover
- Route 53 can fail over to S3-hosted websites.
- Route 53 requires endpoints for health checks and cannot directly fail over to ASGs.
