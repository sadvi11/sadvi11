# Sadhvi Sharma

**Cloud & AI Engineer** · Calgary, Alberta, Canada

I spent 2.5 years keeping **Bell Canada's and T-Mobile US's** 5G core running.
Now I build on AWS and Azure with the habits that job forces on you.

> **Open to Cloud · DevOps · Platform · AI Engineering roles.**
> Calgary · remote across Canada · open to relocation.
> **Authorized to work in Canada. Available immediately.**
>
> 📧 **sadhvisharma763@gmail.com** · 💼 **[LinkedIn](https://www.linkedin.com/in/sadhvi-sharma-5789a6249)**

---

## Why my background is different

Most cloud engineers learn high availability from a course. I learned it on call, on a
telecom core network, against a **99.9% SLA** — where the failure mode isn't a red build,
it's someone's call dropping mid-sentence.

At Nokia I operated Cloud-Native 5G Core network functions — AMF, SMF, UPF, CBIS, CBAM,
NRF — across **10+ operator deployments** at roughly **100,000+ subscribers each**, running
as containerized network functions on Kubernetes and OpenStack. Zero-downtime rolling
upgrades were a contractual requirement, not an aspiration. *(Nokia appreciation award.)*

Then I noticed the thing that made everything since easier: **5G Service-Based Architecture
and AWS microservices are the same patterns wearing different names.** Service discovery,
horizontal scaling, event streaming, traffic routing, container lifecycle. I wrote the
mapping out function by function:

### → **[Nokia 5G Core → AWS: A Production Migration Case Study](https://github.com/sadvi11/nokia-5g-to-aws-migration)**

AMF → ALB · SMF → Lambda + Step Functions · UPF → VPC/NAT · CBAM → EKS/ECS ·
NRF → Cloud Map · OAM bus → Kinesis · UDM → DynamoDB — with Terraform modules and
SOC 2 / PCI DSS control mappings.

**If you read one thing here, read that.** Telecom infrastructure depth *and* shipped AI
systems is an unusual pair in this market — that repo is where the two meet.

---

## Featured work

Every project below is deployed and verified. Not tutorials, not clones.

### Cloud infrastructure & DevOps

| Project | One line | Stack |
|---|---|---|
| **[nokia-5g-to-aws-migration](https://github.com/sadvi11/nokia-5g-to-aws-migration)** | Carrier-grade 5G network functions mapped to production AWS, with 7 Terraform modules and compliance controls | Terraform · ECS · Kinesis · DynamoDB |
| **[aws-vpc-terraform](https://github.com/sadvi11/aws-vpc-terraform)** | Multi-tier VPC across two AZs — NAT, tiered security groups, NACLs, least-privilege IAM. One command up, one command down | Terraform · AWS · IAM |
| **[multi-cloud-terraform](https://github.com/sadvi11/multi-cloud-terraform)** | One codebase, two clouds, identical network — and the three places AWS and Azure stop being interchangeable | Terraform · AWS · Azure |
| **[flask-ecs-fargate-cicd](https://github.com/sadvi11/flask-ecs-fargate-cicd)** | Push to `main` → build, tag by commit SHA, push to ECR, deploy to Fargate. Zero manual steps · **[live](https://flask-ecs-fargate-cicd.onrender.com/health)** | ECS Fargate · ECR · GitHub Actions |
| **[docker-flask-ai-app](https://github.com/sadvi11/docker-flask-ai-app)** | Test-gated CI/CD — tests run before the build, images scanned before they reach ECR | Docker · GitHub Actions · ECR |
| **[prometheus-monitoring-stack](https://github.com/sadvi11/prometheus-monitoring-stack)** | Pull-model observability, deliberately isolated from what it watches — a watcher that dies with its host never alerts | Prometheus · Grafana · Docker Compose |

### AI & machine learning

| Project | One line | Stack |
|---|---|---|
| **[bedrock-rag-app](https://github.com/sadvi11/bedrock-rag-app)** | RAG over verified Canadian tax rules — grounded answers, because a confident wrong answer about contribution limits is worse than none | Bedrock · Titan V2 · Claude · pgvector |
| **[smart-ai-agent](https://github.com/sadvi11/smart-ai-agent)** | Autonomous agent with tool use, persistent memory and RAG — plus an eval suite covering prompt-injection and SQL-injection robustness | Claude API · pgvector · Flask |
| **[ai-chatbot-with-memory](https://github.com/sadvi11/ai-chatbot-with-memory)** | Stateful conversation persisted in DynamoDB, partitioned so the hot-partition trap doesn't bite under load | FastAPI · DynamoDB · Claude API |
| **[canadian-financial-sentiment](https://github.com/sadvi11/canadian-financial-sentiment)** | End-to-end SageMaker pipeline — train, deploy, serve, tear down. The pipeline is the deliverable | SageMaker · S3 · Flask |
| **[f1-telemetry-pipeline](https://github.com/sadvi11/f1-telemetry-pipeline)** | Real-time telemetry through a decoupled queue-and-consumer pipeline with DLQ and retry | SQS · Lambda · DynamoDB |
| **[aws-python-automation](https://github.com/sadvi11/aws-python-automation)** | boto3 automation suite — EC2 control, S3, Lambda scheduling, CloudWatch, SNS alerting | Python · boto3 |

---

## Most repos here ship a `WHY.md`

Not what was built — **why**, and what the alternatives would have cost.

Why event-driven instead of polling. Why DynamoDB instead of Postgres. Why a managed model
instead of self-hosting. What I'd change if it carried real traffic, and which failure mode
worries me most.

Anyone can follow a tutorial. The `WHY.md` files are where the engineering judgement is, and
they're the fastest way to tell whether I'd be useful on your team.

---

## What I work with

**Cloud** — AWS (ECS Fargate, EKS, Lambda, VPC, ECR, S3, DynamoDB, Kinesis, SQS, SNS,
API Gateway, CloudWatch, IAM, Config, SageMaker, Bedrock) · Azure (AZ-900 certified,
building Azure equivalents of my AWS work)

**Infrastructure as code** — Terraform (modules, multi-provider, remote state) · Docker ·
Kubernetes · OpenStack

**CI/CD & observability** — GitHub Actions · Prometheus · Grafana · CloudWatch ·
test-gated pipelines · image scanning

**AI/ML** — AWS Bedrock · SageMaker · Claude API · RAG · pgvector · agent tool-use ·
LLM evaluation and red-teaming

**Languages** — Python (boto3, Flask, FastAPI, scikit-learn) · HCL · Bash · SQL

**Telecom** — Nokia 5G Core (AMF, SMF, UPF, NRF, PCF, UDM) · CBIS/CBAM · CPAN/ZPS ·
CNFs on Kubernetes · 3GPP SBA · ETSI MANO

---

## Background

**Nokia** — 5G Packet Core infrastructure, 2.5 years. Bell Canada and T-Mobile US.
Kubernetes, OpenStack, CPAN/ZPS. Nokia appreciation award.

**Certifications** — Microsoft Azure Fundamentals (AZ-900)

**Education** — B.Tech

---

## Get in touch

I'm looking for a Cloud, DevOps, Platform or AI Engineering role where infrastructure is
treated as a product rather than a cost centre. If the work above looks relevant to what
your team is building, I'd like to hear from you.

📧 **sadhvisharma763@gmail.com**
💼 **[linkedin.com/in/sadhvi-sharma-5789a6249](https://www.linkedin.com/in/sadhvi-sharma-5789a6249)**
📍 Calgary, Alberta · authorized to work in Canada · open to relocation
