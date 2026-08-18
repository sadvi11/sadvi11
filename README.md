# Sadhvi Sharma

**Cloud & Platform Engineer** · Calgary, Alberta, Canada

I spent 2.5 years keeping **Bell Canada's, T-Mobile US's and Orange's** 5G core running
against a 99.9% SLA. Now I build on AWS and Azure with the habits that job forces on you.

> **Open to Cloud · DevOps · Platform · SRE · AI Engineering roles.**
> Calgary · remote across Canada · open to relocation.
> **Permanent Resident — no sponsorship required. Available immediately.**
>
> 📧 **sadhvisharma763@gmail.com** · 💼 **[LinkedIn](https://www.linkedin.com/in/sadhvi-sharma-5789a6249)**

---

## Why my background is different

Most cloud engineers learn high availability from a course. I learned it on call, on a
telecom core network, where the failure mode isn't a red build — it's someone's call
dropping mid-sentence.

At Nokia I operated Cloud-Native 5G Core network functions — AMF, SMF, UPF, CBIS, CBAM,
NRF — as containerized workloads on Kubernetes and OpenStack, across deployments for
international operators. Zero-downtime rolling upgrades were a contractual requirement,
not an aspiration. I delivered a wave-based multi-site 4G→5G migration with **zero
subscriber downtime**. *(Nokia appreciation award.)*

Then I noticed the thing that made everything since easier: **5G Service-Based
Architecture and cloud microservices are the same patterns wearing different names.**
Service discovery, horizontal scaling, event streaming, container lifecycle.

---

## Three things worth your time

Everything here is public. These three are where the engineering actually is.

### 1. [Three-tier e-commerce on AWS EKS](https://github.com/sadvi11/eks-ecommerce-microservices) — 13 workloads, proven on every commit

8 microservices in 5 languages, 2 databases, a cache and a message broker. Terraform
builds the cluster; one templated Helm topology renders all 13 workloads rather than 24
copy-pasted manifests.

**What makes it different from the hundreds of other three-tier EKS repos:** CI deploys
the entire stack to a throwaway cluster on every commit — free, no AWS account — then
**writes a cart key, deletes the Redis pod, and asserts the key came back.** The
persistence claim is tested, not stated.

It also took nine CI runs to get green, and the commit history says why: a container
running as uid 0 with all capabilities dropped **is not root** and fails with
`chown: Operation not permitted`; a Java service that looked broken was actually
cascading from MySQL being down; and the vendor MySQL image genuinely cannot initialise,
which four identical error messages proved.

### 2. [The same ML service, shipped to both clouds](https://github.com/sadvi11/mlops-sentiment-eks)

| | **[AWS — EKS](https://github.com/sadvi11/mlops-sentiment-eks)** | **[Azure — Container Apps](https://github.com/sadvi11/azure-sentiment-containerapp)** |
|---|---|---|
| Runtime | EKS — Kubernetes I control | Container Apps — serverless, scales to zero |
| IaC | Terraform | Bicep |
| Scaling | HPA on Prometheus metrics | HTTP autoscaling, zero to five |
| Registry auth | IRSA | Managed identity, `AcrPull` only |
| Credentials stored | none — OIDC federation | none — OIDC federation |

**What running both actually taught me:** identical code, different exposure. `/metrics`
is an in-cluster scrape on EKS and an internet-facing endpoint on Container Apps — the
same Prometheus default that is harmless on one cloud publishes your interpreter version
on the other. I found that by opening the URL, not by reading the docs.

> **Try it: https://sentiment-api-6nhl.onrender.com** — ask it about financial
> results, then ask it something in French and watch it return `uncertain` with its
> vocabulary coverage rather than guessing.
>
> The Azure deployment is the primary path and is currently offline — that subscription's
> free-trial credits ran out. Rather than leave a dead link labelled "live", the same
> service now also runs on a free tier, so the demo survives any one provider's billing
> state. The Azure pipeline and Bicep templates are unchanged.

### 3. [Nokia 5G Core → AWS migration study](https://github.com/sadvi11/nokia-5g-to-aws-migration)

Carrier network functions mapped to AWS service by service — AMF→ALB, CBAM→ECS,
NRF→Cloud Map, OAM bus→Kinesis — across 7 Terraform modules with SOC 2 and PCI DSS
control mappings.

It's an architecture study with working Terraform, not a production migration, and the
README says so. What's real is the source side: I operated these functions, so the
mapping is grounded in what they do rather than what their names suggest — including
being explicit that the **user plane doesn't map cleanly**, because a UPF forwarding
subscriber packets at line rate is not an ECS task.

---

## Everything else

**Infrastructure, delivery and reliability**

| Project | One line | Stack |
|---|---|---|
| **[gitops-argocd-kubernetes](https://github.com/sadvi11/gitops-argocd-kubernetes)** | Pull-based delivery with **no cluster credential in CI**. The pipeline scales prod down by hand and fails unless Argo CD heals it — self-heal confirmed in ~10s every run | Argo CD · Kustomize · kind |
| **[iac-security-guardrails](https://github.com/sadvi11/iac-security-guardrails)** | Checkov + custom OPA/Rego for Canadian data residency and cost tags. Tested in **both directions** — which caught a policy that had silently stopped matching anything | OPA · Rego · Checkov · Terraform |
| **[sre-incident-practice](https://github.com/sadvi11/sre-incident-practice)** | Blameless postmortems from **my own real incidents**, an SLO with an error-budget policy, and the argument for 99.5% over 99.9% because the architecture can't hold the higher number | SRE · SLO · runbooks |
| **[azure-finops-guardrails](https://github.com/sadvi11/azure-finops-guardrails)** | Finds unattached disks, orphaned IPs, and VMs stopped-but-not-deallocated; forecasts month-end from run rate using median absolute deviation so one spike can't hide inside it | Azure · Bicep · Python |
| **[azure-devops-pipelines](https://github.com/sadvi11/azure-devops-pipelines)** | Multi-stage pipelines with environment gates that live **outside** the repo, so a developer can't bypass production approval by editing YAML | Azure DevOps · templates |
| **[multi-cloud-terraform](https://github.com/sadvi11/multi-cloud-terraform)** | One codebase, two clouds, identical network — and the three places AWS and Azure stop being interchangeable | Terraform · AWS · Azure |
| **[aws-vpc-terraform](https://github.com/sadvi11/aws-vpc-terraform)** | Multi-tier VPC across two AZs — NAT, tiered security groups, NACLs, least-privilege IAM | Terraform · AWS · IAM |
| **[flask-ecs-fargate-cicd](https://github.com/sadvi11/flask-ecs-fargate-cicd)** | Containerized API on Fargate, SHA-tagged images, **OIDC — no stored AWS keys** · [live demo](https://flask-ecs-fargate-cicd.onrender.com/health) | ECS Fargate · ECR · Actions |
| **[docker-flask-ai-app](https://github.com/sadvi11/docker-flask-ai-app)** | Test-gated CI/CD where the Trivy scan **fails the build** on HIGH/CRITICAL rather than reporting and moving on | Docker · Trivy · ECR |
| **[prometheus-monitoring-stack](https://github.com/sadvi11/prometheus-monitoring-stack)** | Pull-model observability, deliberately isolated from what it watches — a watcher that dies with its host never alerts | Prometheus · Grafana |

**AI and machine learning**

| Project | One line | Stack |
|---|---|---|
| **[bedrock-rag-app](https://github.com/sadvi11/bedrock-rag-app)** | RAG over financial documents — measured at 195 ms embedding, 225 ms retrieval, ~$0.0003/query. Grounded, so it reports missing context instead of inventing a number | Bedrock · Titan V2 · pgvector |
| **[smart-ai-agent](https://github.com/sadvi11/smart-ai-agent)** | Agent with tool use, persistent memory and RAG, plus an eval suite for **prompt injection and SQL injection** | Claude API · pgvector · Flask |
| **[structured-test-agent](https://github.com/sadvi11/structured-test-agent)** | Forced tool choice against a strict JSON Schema, with tests asserting the schema stays strict rather than advisory | Claude API · JSON Schema |
| **[canadian-financial-sentiment](https://github.com/sadvi11/canadian-financial-sentiment)** | End-to-end SageMaker pipeline — train, deploy, serve, tear down | SageMaker · S3 · Flask |
| **[ai-chatbot-with-memory](https://github.com/sadvi11/ai-chatbot-with-memory)** | Cross-session memory in DynamoDB, with a circuit breaker around the model API | FastAPI · DynamoDB |
| **[f1-telemetry-pipeline](https://github.com/sadvi11/f1-telemetry-pipeline)** | Event-driven telemetry through a decoupled queue-and-consumer pipeline with DLQ and retry | SQS · Lambda · DynamoDB |
| **[aws-python-automation](https://github.com/sadvi11/aws-python-automation)** | boto3 automation — EC2 control, S3, Lambda scheduling, CloudWatch, SNS alerting | Python · boto3 |

---

## What I'd want you to notice

**The bugs I found in my own work**, because that's harder to fake than a green badge:

- A REST endpoint that returned a **placeholder instead of calling the agent** — valid
  JSON, HTTP 200, and lint and type-checks both passed. Linting proves code is
  well-formed, not that it does anything.
- A **Rego policy matching nothing** while the test suite stayed green, because
  Terraform emits `"tags": null` and `not r.values.tags` is false for `null`. Fixed the
  rule, then restructured the tests so one dead policy can't hide behind its neighbours.
- A **green CI badge over a red test suite** — `continue-on-error: true` with a comment
  claiming credentials were needed. Eleven of twelve passed offline.
- A deployed sentiment model scoring **2/6 on real inputs** at ~0.52 confidence while
  cross-validation said 0.471 — worse than random. It now abstains when the input is
  outside its vocabulary instead of guessing.

A check that cannot fail is worse than no check, because it produces confidence without
coverage. Most of my repos ship a `WHY.md` for the same reason.

---

## What I work with

**Cloud** — AWS (EKS, ECS Fargate, Lambda, VPC, ECR, S3, DynamoDB, Kinesis, SQS, SNS,
IAM, CloudWatch, Bedrock, SageMaker) · Azure (Container Apps, ACR, Bicep, managed
identity, Log Analytics, workload identity federation)

**Infrastructure as code** — Terraform · Bicep · Helm · Kustomize · Docker · Kubernetes ·
OpenStack

**CI/CD & delivery** — GitHub Actions · Azure DevOps · Argo CD (GitOps) · OIDC federation

**Security & governance** — OPA/Rego policy-as-code · Checkov · Trivy · IRSA ·
least-privilege IAM · SOC 2 / PCI DSS control mapping

**Observability & SRE** — Prometheus · Grafana · CloudWatch · SLOs and error budgets ·
blameless postmortems · production on-call

**AI/ML** — Bedrock · SageMaker · Claude API · RAG · pgvector · agent tool use ·
LLM evaluation, prompt-injection testing

**Languages** — Python (boto3, FastAPI, Flask, scikit-learn) · Bash · HCL · SQL

**Telecom** — Nokia 5G Core (AMF, SMF, UPF, NRF, PCF, UDM) · CBIS/CBAM · CNFs on
Kubernetes · 3GPP SBA · ETSI MANO

---

## Background

**AI Hardware & Technology Specialist** — Meta (via Influence Marketing), Calgary ·
Oct 2025 – present
Technical enablement on Meta AI products and XR hardware. Built and delivered training
for 50+ retail staff, reducing escalated issues ~30%. The infrastructure work above is
built outside working hours.

**Solution Engineer, Cloud Core Network** — Nokia, Delhi · Dec 2022 – Jul 2025
5G core in carrier production at 99.9% SLA on OpenStack and Kubernetes, for Bell Canada,
T-Mobile US and Orange. Wave-based multi-site 4G→5G migration with zero subscriber
downtime. Production on-call with structured root cause analysis.

**RF & Systems Engineer** — AA Electro Magnetic Test Labs, India · 2018 – 2020

**Education** — M.Tech, Electronics & Communication Engineering, University of Delhi
(full merit scholarship) · B.Tech, Shri Mata Vaishno Devi University

**Certifications** — Microsoft Azure Fundamentals (AZ-900) · AWS Solutions Architect
Associate (in progress)

---

## Get in touch

I'm looking for a Cloud, DevOps, Platform or SRE role where infrastructure is treated as
a product rather than a cost centre. If the work above looks relevant to what your team
is building, I'd like to hear from you.

📧 **sadhvisharma763@gmail.com**
💼 **[linkedin.com/in/sadhvi-sharma-5789a6249](https://www.linkedin.com/in/sadhvi-sharma-5789a6249)**
📍 Calgary, Alberta · **Permanent Resident, no sponsorship required** · open to relocation
