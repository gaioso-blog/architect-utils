---
name: "aws-architect-utils"
displayName: "AWS Architect Utils"
description: "AWS architecture expert with pricing estimates, Well-Architected reviews, ADRs, diagrams, security assessments, cost optimization, and migration planning. Activates automatically when you talk about AWS."
keywords: ["aws", "architecture", "cloud", "infra", "infrastructure", "pricing", "cost", "estimate", "budget", "well-architected", "wa review", "waf", "pillar", "ec2", "s3", "lambda", "rds", "dynamodb", "ecs", "eks", "fargate", "cloudfront", "vpc", "iam", "sqs", "sns", "eventbridge", "terraform", "cdk", "cloudformation", "adr", "diagram", "drawio", "security", "compliance", "reliability", "performance", "sustainability", "migration", "reserved instances", "savings plan", "spot", "graviton"]
author: "Gaioso"
---
# AWS Architect Power

AWS architecture expert for Kiro. Brings pricing estimates, Well-Architected reviews, ADRs, diagrams, security assessments, cost optimization, and migration planning into your sessions — activated automatically when you talk about AWS.

## What This Power Does

| Skill | Command | What it does |
|---|---|---|
| WA Review | `/wa-review` | Full Well-Architected review across all 6 pillars |
| Cost Optimization | `/cost-optimization-audit` | Identify waste, right-sizing, and pricing model improvements |
| Architecture Decision Record | `/architecture-decision-record` | Generate WA-aligned ADRs with trade-off analysis |
| Security Assessment | `/security-assessment` | Deep-dive security posture against the WA Security pillar |
| Reliability Plan | `/reliability-improvement-plan` | Identify SPOFs and produce a remediation plan |
| Performance Efficiency | `/performance-efficiency` | Evaluate compute, caching, scaling, and data efficiency |
| Migration Readiness | `/migration-readiness` | Assess workload readiness with the 7 Rs framework |
| Sustainability | `/sustainability-optimization` | Reduce carbon footprint through resource efficiency |
| Architecture Diagram | `/aws-architecture-diagram` | Generate draw.io diagrams with official AWS icons |

## MCP Tools

- **aws-pricing-calculator** — Build shareable AWS Pricing Calculator estimates via `calculator.aws`
- **aws-pricing-api** — Real-time pricing data from the AWS Price List API

## Prerequisites

- **Node.js + npx** — for the AWS Pricing Calculator MCP
- **Python + uv/uvx** — for the AWS Pricing API MCP
  - Install: `pip install uv` or see https://docs.astral.sh/uv/getting-started/installation/
- **AWS credentials** configured (`~/.aws/credentials` or environment variables)
  - Minimum permissions: `pricing:GetProducts`, `pricing:DescribeServices`

## Usage Examples

```
# Estimate pricing
"How much would a serverless API with 10M requests/month cost on AWS?"

# Well-Architected review
/wa-review

# Cost audit
/cost-optimization-audit

# Document a decision
/architecture-decision-record Use Aurora Serverless v2 vs RDS Multi-AZ

# Generate a diagram
/aws-architecture-diagram serverless e-commerce backend

# Security assessment
/security-assessment

# Migration planning
/migration-readiness on-prem Java monolith to AWS
```
