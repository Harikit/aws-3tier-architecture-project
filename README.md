AWS 3-Tier Architecture — Enterprise Application

VPC Configuration
<img width="1205" height="608" alt="Screenshot 2026-04-02 122945" src="https://github.com/user-attachments/assets/e9ccafe2-6bc7-442b-b837-14c69131414c" />

EC2 App LB
<img width="1357" height="600" alt="ec2-app-lb" src="https://github.com/user-attachments/assets/d01b4e92-61db-4b43-b111-322e15bad2d1" />

Security Group
<img width="1361" height="637" alt="security-group" src="https://github.com/user-attachments/assets/d411b832-6cbe-46b7-8736-7a3419f19c27" />

EC2 Auto Scaling Group
<img width="1365" height="632" alt="asg-instances" src="https://github.com/user-attachments/assets/ac36a12e-f5f0-4cb1-9a3b-42d398fc21b2" />
<img width="1364" height="636" alt="asg-instances-management" src="https://github.com/user-attachments/assets/70a46c2b-2929-4791-a6e5-1b6ba57c0557" />


ALB Target Group
<img width="1357" height="632" alt="alb-traget-group" src="https://github.com/user-attachments/assets/79925d2c-5aac-4fa6-84d2-49ee51550594" />

App Frontend in S3
<img width="1361" height="455" alt="s3-frontend" src="https://github.com/user-attachments/assets/866a25c7-6c44-46d8-9c21-0424b9d4ef03" />

App Cloudfront
<img width="1352" height="627" alt="cloudfront" src="https://github.com/user-attachments/assets/86c5ca0c-1f38-4033-9e77-934a5bf707b9" />
<img width="1362" height="689" alt="image" src="https://github.com/user-attachments/assets/f0b8911a-8902-4b90-ae6d-4fba7a368fa8" />


RDS Dashboard
<img width="1354" height="631" alt="rds-dashboard" src="https://github.com/user-attachments/assets/b5ff6a47-d4f1-49f8-9d9c-4b46dc1e2cb7" />
<img width="1362" height="567" alt="image" src="https://github.com/user-attachments/assets/21680448-511b-4aae-8dee-240182e3f93a" />

Cloud Watch
<img width="1365" height="479" alt="cloudwatch-alarms" src="https://github.com/user-attachments/assets/e8987a0a-2302-44b6-a30d-bc989c5ff030" />








\## Architecture Overview

```

Users → CloudFront

     ├──  → S3 (React Frontend)

     └──  → ALB → EC2 Auto Scaling (Django) → RDS MySQL

```



\## AWS Services Used



| Service | Purpose |

|---------|---------|

| VPC | Isolated network with public/private subnets |

| EC2 + ASG | App servers with auto scaling |

| RDS MySQL | Multi-AZ managed database |

| S3 + CloudFront | Static frontend with CDN |

| ALB | Load balancing across EC2 instances |

| IAM | Roles and policies (least privilege) |

| CloudWatch | Logs and alarms |

| SSM | Secure EC2 access without SSH |



\## Infrastructure Phases



\- Phase 1 — VPC + Networking

\- Phase 2 — Security Groups

\- Phase 3 — S3 + CloudFront

\- Phase 4 — RDS MySQL (Multi-AZ)

\- Phase 5 — EC2 + Auto Scaling

\- Phase 6 — Application Load Balancer



\## Security Highlights



\- All EC2 instances in private subnets

\- RDS in isolated private subnet

\- Security Groups chained by ID

\- SSM Session Manager instead of open SSH

\- CloudFront OAC for private S3 access

