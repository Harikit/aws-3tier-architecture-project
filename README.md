\# AWS 3-Tier Architecture — Enterprise Django Application



!\[AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge\&logo=amazonaws\&logoColor=white)

!\[Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge\&logo=django\&logoColor=white)

!\[Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge\&logo=docker\&logoColor=white)

!\[MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge\&logo=mysql\&logoColor=white)

!\[Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge\&logo=terraform\&logoColor=white)



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

