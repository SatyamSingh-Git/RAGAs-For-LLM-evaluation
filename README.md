# RAGAs-For-LLM-evaluation

## Overview
This repository provides a production-grade implementation of **Retrieval-Augmented Generation Assessment (RAGAs)** for evaluating LLM logs Google’s **Gemini 2.5 Flash** model and **models/embedding-001**. It computes three core metrics—**faithfulness**, **answer relevancy**, and **context precision**—for each log entry in `logs.json`.

## Repository Structure
```
├── logs.json                       # Input LLM log file
├── ragas_integration.py            # Standalone Python script
├── ragas_integration.ipynb         # Interactive Jupyter notebook
├── requirements.txt                # Python dependencies
├── Output.json                     # Detailed per-sample scores
├── Output_summary_report.json      # Aggregated statistics and summary
└── README.md                       # This file
```

## Setup

1. Clone the repo:  
   ```bash
   git clone https://github.com/your-org/ragas-gemini-integration.git
   cd ragas-gemini-integration
   ```

2. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```

3. Set your Google API key (Gemini access):  
   ```bash
   export GOOGLE_API_KEY="YOUR_GOOGLE_API_KEY"
   ```

## Usage

### Python Script
Run end-to-end evaluation on your logs:
```bash
python ragas_integration.py logs.json
```
Results will be written to `Output.json` and `Summary_summary_report.json`.

### Jupyter Notebook
Launch interactive analysis:
```bash
jupyter notebook ragas_integration.ipynb
```
Step through cells to load logs, compute metrics, and view detailed statistics.

## Outputs

- **Output.json**: Array of per-sample metric scores  
- **Output_summary_report.json**: Overall averages, min/max/std, and detailed results  

Sample JSON entry:
```json
{
  "id": "80e8a1e6-6ba2-4b38-9397-56b89564ca00",
  "faithfulness": 1.0000,
  "answer_relevancy": 0.8416,
  "context_precision": 1.0000
}
```

## Metrics Computed

- **Faithfulness**: Factual consistency between response and context  
- **Answer Relevancy**: Alignment of response to user query via embeddings  
- **Context Precision**: Proportion of relevant context chunks  

## Notes

- Implements **async** processing with delay handling for Google API rate limits.  
- Graceful error handling assigns fallback scores of 0.0 on failures.  
- Designed for English-language logs; extendable to other use cases.  

## License
This project is released under the [MIT License](LICENSE).

flowchart TD
    A[Start: Cloud Infrastructure Setup]

```mermaid
flowchart TD
    A[Start: Cloud Infrastructure Setup]

    subgraph Provisioning and Infrastructure
        A1[Define Requirements]
        A2[Choose Cloud Provider - AWS, Azure, GCP]
        A3[Set up Physical Infrastructure - Data Centers]
        A4[Create Virtual Machines or Instances]
        A5[Configure Networking - VPC, Subnets, Security Groups]
        A6[Provision Storage - Block, Object, File]
        A7[Implement Identity and Access Management - IAM]
        A8[Infrastructure as Code - Terraform, CloudFormation, ARM]
    end

    subgraph Environment Configuration and Deployment
        B1[Install OS and Middleware]
        B2[Configure Security Policies]
        B3[Deploy Applications - Containers, Docker, Kubernetes]
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
        D2[Scale Resources Dynamically - Auto-scaling]
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


```


