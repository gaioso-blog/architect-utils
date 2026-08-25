# AWS Architect Utils

AWS architecture expert power for Kiro. Brings pricing estimates, Well-Architected reviews, ADRs, diagrams, security assessments, cost optimization, and migration planning into your Kiro sessions — activated automatically when you talk about AWS.

## What's included

**MCPs (tools)**
- `aws-pricing-calculator` — Build shareable AWS Pricing Calculator estimates via `calculator.aws`
- `aws-pricing-api` — Real-time pricing data from the AWS Price List API

**Skills (slash commands)**
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

**Steering**
- `well-architected.md` — Always-on WA Framework context that shapes all architecture-related responses

## Prerequisites

- **Node.js + npx** — for the AWS Pricing Calculator MCP
- **Python + uv/uvx** — for the AWS Pricing API MCP
  - Install: `curl -LsSf https://astral.sh/uv/install.sh | sh`
- **AWS credentials** configured (`~/.aws/credentials` or environment variables)
  - Minimum permissions: `pricing:GetProducts`, `pricing:DescribeServices`

## Installation

### Kiro IDE

1. Open Kiro IDE
2. Open the Powers panel
3. Click **Add Custom Power**
4. Select **Import power from GitHub**
5. Enter: `https://github.com/gaioso-blog/architect-utils`
6. Click **Install**

### Manual

```bash
git clone https://github.com/gaioso-blog/architect-utils ~/.kiro/powers/architect-utils
```

Then in Kiro IDE: Powers panel → Add Custom Power → Import power from folder → select the directory.

## How it activates

The power activates automatically when your conversation contains any of the trigger keywords — `aws`, `architecture`, `pricing`, `cost`, `ec2`, `lambda`, `terraform`, `well-architected`, and many more.

You don't need to do anything. Mention "I want to estimate the cost of a serverless API" and the pricing tools load. Mention "let's do a WA review" and the review skill activates.

## Usage examples

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

## Structure

```
architect-utils/
├── plugin.json                          # Power manifest and activation keywords
├── mcp.json                             # MCP server configuration
├── README.md                            # This file
├── steering/
│   └── well-architected.md              # WA Framework steering context
└── skills/
    ├── wa-review/SKILL.md
    ├── cost-optimization-audit/SKILL.md
    ├── architecture-decision-record/SKILL.md
    ├── security-assessment/SKILL.md
    ├── reliability-improvement-plan/SKILL.md
    ├── performance-efficiency/SKILL.md
    ├── migration-readiness/SKILL.md
    ├── sustainability-optimization/SKILL.md
    └── aws-architecture-diagram/
        ├── SKILL.md
        └── references/                  # AWS icon reference files for draw.io
```
