AWS 3-Tier Architecture — Enterprise Application

VPC Configuration
<img width="1205" height="608" alt="Screenshot 2026-04-02 122945" src="https://github.com/user-attachments/assets/e9ccafe2-6bc7-442b-b837-14c69131414c" />







\## Architecture Overview

```

Users → CloudFront

     ├── /\* → S3 (React Frontend)

     └── /api/\* → ALB → EC2 Auto Scaling (Django) → RDS MySQL

```



\## AWS Services Used



| Service | Purpose |

|---------|---------|

| VPC | Isolated network with public/private subnets |

| EC2 + ASG | Django app servers with auto scaling |

| RDS MySQL | Multi-AZ managed database |

| S3 + CloudFront | Static frontend with CDN |

| ALB | Load balancing across EC2 instances |

| IAM | Roles and policies (least privilege) |

| Secrets Manager | Secure credential storage |

| CloudWatch | Logs and alarms |

| SSM | Secure EC2 access without SSH |



\## Infrastructure Phases



\- Phase 1 — VPC + Networking

\- Phase 2 — Security Groups

\- Phase 3 — S3 + CloudFront

\- Phase 4 — RDS MySQL (Multi-AZ)

\- Phase 5 — EC2 + Auto Scaling

\- Phase 6 — Application Load Balancer

\- Phase 7 — CI/CD + Monitoring



\## Security Highlights



\- All EC2 instances in private subnets

\- RDS in isolated private subnet

\- No hardcoded credentials (Secrets Manager)

\- Security Groups chained by ID

\- SSM Session Manager instead of open SSH

\- CloudFront OAC for private S3 access

