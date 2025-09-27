flowchart TD
    A[Start: Cloud Infrastructure Setup]

    subgraph Provisioning and Infrastructure
        A1[Define Requirements]
        A2[Choose Cloud Provider (AWS, Azure, GCP)]
        A3[Set up Physical Infrastructure (Data Centers)]
        A4[Create Virtual Machines/Instances]
        A5[Configure Networking (VPC, Subnets, Security Groups)]
        A6[Provision Storage (Block, Object, File)]
        A7[Implement Identity and Access Management (IAM)]
        A8[Infrastructure as Code (Terraform, CloudFormation, ARM)]
    end

    subgraph Environment Configuration and Deployment
        B1[Install OS and Middleware]
        B2[Configure Security Policies]
        B3[Deploy Applications (Containers/Docker/Kubernetes)]
        B4[Set up Monitoring and Logging Tools]
        B5[Automate CI/CD Pipelines]
    end

    subgraph Environment Uses
        C1[Web Hosting]
        C2[Data Storage and Backup]
        C3[Application Development and Testing]
        C4[Big Data and Analytics]
        C5[AI/ML Model Training]
        C6[Disaster Recovery]
    end

    subgraph Working and Maintenance
        D1[Monitor Infrastructure Performance]
        D2[Scale Resources Dynamically (Auto-scaling)]
        D3[Apply Security Updates and Patch Management]
        D4[Backup and Disaster Recovery Operations]
        D5[Cost Management and Optimization]
        D6[Decommission and Resource Cleanup]
    end

    %% Flow Connections
    A --> A1 --> A2 --> A3 --> A4 --> A5 --> A6 --> A7 --> A8 --> B1
    B1 --> B2 --> B3 --> B4 --> B5 --> C1
    B3 --> C2
    B3 --> C3
    B3 --> C4
    B3 --> C5
    B3 --> C6
    C1 --> D1 --> D2 --> D3 --> D4 --> D5 --> D6
    C2 --> D1
    C3 --> D1
    C4 --> D1
    C5 --> D1
    C6 --> D1
