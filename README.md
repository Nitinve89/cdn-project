AWS CloudFront CDN with Node.js, EC2 & S3
The project demonstrates how CloudFront can distribute application traffic across multiple origins using path-based routing, while CloudWatch is used for monitoring and CDN logging.

**Architecture**
                         Users
                           │
                           ▼
                    ┌─────────────┐
                    │ CloudFront  │
                    │     CDN     │
                    └──────┬──────┘
                           │
                    Path-Based Routing
                     ┌─────┴─────┐
                     │           │
                 /api/*      /static/*
                     │           │
                     ▼           ▼
              ┌──────────┐  ┌──────────┐
              │   EC2    │  │    S3    │
              │ Node.js  │  │  Static  │
              │   App    │  │ Content  │
              └──────────┘  └──────────┘
                     │
                     ▼
              ┌──────────────┐
              │  CloudWatch  │
              │ Logs/Monitor │
              └──────────────┘
