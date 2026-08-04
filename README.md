# Sadhvi Sharma

**Cloud & AI Engineer** · Calgary, Alberta, Canada

I spent two years operating Nokia's cloud-native 5G core — Kubernetes-based network
functions carrying live traffic for European mobile operators, where a bad deploy is a
dropped call for real people. I now build on AWS, and I bring that same operational
standard: infrastructure as code, observability before you need it, and nothing shipped
that I haven't verified myself.

> **Open to Cloud / DevOps / Platform / AI Engineering roles.**
> Calgary · remote across Canada · open to relocation.
> **Canadian Permanent Resident — no sponsorship required, available immediately.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sadhvi-sharma-5789a6249/)
&nbsp;
![Location](https://img.shields.io/badge/Calgary-Canada-red?style=flat)
&nbsp;
![Status](https://img.shields.io/badge/Status-Open%20to%20work-2ea44f?style=flat)

---

## The thing that makes my background unusual

Most cloud engineers learn high availability from documentation. I learned it on call,
on a telecom core network, where the architecture had no tolerance for downtime.

**5G Service-Based Architecture and AWS microservices solve the same problems with
different tooling.** Service discovery, horizontal scaling, event streaming, traffic
routing, container lifecycle — the same engineering, different names. I wrote that
mapping out in full, function by function:

### → **[Nokia 5G Core → AWS: A Production Migration Case Study](https://github.com/sadvi11/nokia-5g-to-aws-migration)**

AMF → ALB · SMF → Lambda + Step Functions · UPF → VPC/NAT · CBAM → EKS/ECS ·
NRF → Cloud Map · OAM bus → Kinesis · UDM → DynamoDB — with Terraform modules and
SOC 2 / PCI DSS control mappings.

*If you read one thing here, read that.*

---

## Featured work

Everything below is built, deployed and verified — not tutorial follow-alongs.

### Infrastructure & DevOps

| Project | What it does | Stack |
|---|---|---|
| **[nokia-5g-to-aws-migration](https://github.com/sadvi11/nokia-5g-to-aws-migration)** | Carrier-grade 5G network functions mapped to production AWS, 7 Terraform modules, compliance controls | Terraform · ECS · Kinesis · DynamoDB · Cloud Map |
| **[aws-vpc-terraform](https://github.com/sadvi11/aws-vpc-terraform)** | Multi-tier VPC across 2 AZs — NAT, IGW, route tables, tiered SGs, NACLs, least-privilege IAM. One command up, one command down | Terraform · AWS · IAM |
| **[multi-cloud-terraform](https://github.com/sadvi11/multi-cloud-terraform)** | One codebase, two clouds, identical network — and documentation of the three places AWS and Azure stop being interchangeable | Terraform · AWS · Azure |
| **[flask-ecs-fargate-cicd](https://github.com/sadvi11/flask-ecs-fargate-cicd)** | Containerized API on ECS Fargate. Every push to `main` builds, tags by commit SHA, pushes to ECR and deploys — zero manual steps · **[live](https://flask-ecs-fargate-cicd.onrender.com/health)** | Docker · ECS Fargate · ECR · GitHub Actions |
| **[docker-flask-ai-app](https://github.com/sadvi11/docker-flask-ai-app)** | Test-gated CI/CD — tests run before the build, images are scanned before they reach ECR | Docker · GitHub Actions · ECR · scikit-learn |
| **[prometheus-monitoring-stack](https://github.com/sadvi11/prometheus-monitoring-stack)** | Pull-model observability, deliberately isolated from what it watches — because a watcher that dies with its host never alerts | Prometheus · Grafana · Node Exporter · Docker Compose |
| **[kubernetes-flask-deployment](https://github.com/sadvi11/kubernetes-flask-deployment)** | Replicated Flask deployment on Kubernetes with NodePort service, images from ECR | Kubernetes · Docker · ECR |

### AI & Machine Learning

| Project | What it does | Stack |
|---|---|---|
| **[bedrock-rag-app](https://github.com/sadvi11/bedrock-rag-app)** | RAG over verified Canadian tax and financial rules — grounded answers, not hallucinated, not generic-American | Bedrock · Titan Embeddings V2 · Claude · pgvector · Flask |
| **[smart-ai-agent](https://github.com/sadvi11/smart-ai-agent)** | Autonomous agent with tool use, persistent memory and RAG — plus an automated eval suite covering prompt-injection and SQL-injection robustness | Claude API · pgvector · Flask |
| **[canadian-financial-sentiment](https://github.com/sadvi11/canadian-financial-sentiment)** | Sentiment classifier trained and deployed on SageMaker, served through a real-time endpoint | SageMaker BlazingText · S3 · Flask |
| **[ai-chatbot-with-memory](https://github.com/sadvi11/ai-chatbot-with-memory)** | Stateful chatbot — conversation history persisted, model versioning, built for latency and scale | FastAPI · Claude API · DynamoDB |
| **[serverless-image-recognition](https://github.com/sadvi11/serverless-image-recognition)** | Event-driven content moderation triggered on upload | Lambda · Rekognition · DynamoDB · SNS |
| **[serverless-ai-summarizer](https://github.com/sadvi11/serverless-ai-summarizer)** | Documents land in S3, come back summarized, no servers involved | Lambda · S3 · Claude |

### Data & Automation

| Project | What it does | Stack |
|---|---|---|
| **[f1-telemetry-pipeline](https://github.com/sadvi11/f1-telemetry-pipeline)** | Real-time race telemetry streaming through a decoupled queue-and-consumer pipeline | SQS · Lambda · DynamoDB · CloudWatch |
| **[aws-python-automation](https://github.com/sadvi11/aws-python-automation)** | boto3 automation suite — EC2 control, S3 upload, Lambda scheduling, CloudWatch monitoring, SNS alerting | Python · boto3 |
| **[Event-announcement-system](https://github.com/sadvi11/Event-announcement-system)** | Fan-out notifications to thousands of subscribers with no infrastructure to manage | SNS · Lambda · API Gateway · S3 |
| **[netflix-video-processing-monitor](https://github.com/sadvi11/netflix-video-processing-monitor)** | Pipeline monitoring with AI-assisted alert triage | Python · CloudWatch |

---

## What I actually work with

**Cloud** — AWS (ECS Fargate, EKS, Lambda, VPC, ECR, S3, DynamoDB, Kinesis, SQS, SNS,
API Gateway, CloudWatch, IAM, Config, Rekognition, SageMaker, Bedrock) · Azure (network
fundamentals, via Terraform)

**Infrastructure as Code** — Terraform (modules, multi-provider, remote state) ·
Docker · Kubernetes · Docker Compose

**CI/CD & Observability** — GitHub Actions · Prometheus · Grafana · CloudWatch ·
test-gated pipelines · image scanning

**AI/ML** — AWS Bedrock · SageMaker · Claude API · RAG pipelines · pgvector ·
agent tool-use · LLM evaluation & red-teaming

**Languages** — Python (boto3, Flask, FastAPI, scikit-learn) · HCL · Bash · SQL

**Telecom** — Nokia 5G Core (AMF, SMF, UPF, NRF, PCF, UDM) · CBIS/CBAM ·
CNFs on Kubernetes · 3GPP SBA · ETSI MANO

---

## How I build

Three habits, learned from production rather than from courses:

**Verify against something already known.** Every number I publish is checked against
another number I already trust. That practice is what has caught most of my own bugs.

**Probe before you build.** I confirm what a system actually returns before I write the
layer on top of it — assumptions that look plausible are the expensive kind.

**Document the failure modes, not just the happy path.** The useful part of any README
is where it says what breaks and why.

---

## Get in touch

I'm looking for a Cloud, DevOps, Platform or AI Engineering role where infrastructure is
treated as a product. If any of the work above is relevant to what your team is building,
I'd like to hear about it.

**[LinkedIn](https://www.linkedin.com/in/sadhvi-sharma-5789a6249/)** · Calgary, Canada ·
Permanent Resident · available immediately
