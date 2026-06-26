<div align="center">

# Hi, I'm Ogaji Igwe Samuel
### Cloud & DevOps Engineer | AI-Augmented Infrastructure

**I design, deploy, and automate production-grade infrastructure on AWS — and increasingly, I build the AI-driven tooling that makes that infrastructure easier to operate, troubleshoot, and govern..**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Igwe%20Ogaji-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/igwe-ogaji)
[![GitHub](https://img.shields.io/badge/GitHub-samklin92-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/samklin92)
[![Email](https://img.shields.io/badge/Email-samklinofficial91%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:samklinofficial91@gmail.com)
[![Location](https://img.shields.io/badge/📍-Lagos%2C%20Nigeria-4CAF50?style=for-the-badge)](https://github.com/samklin92)

</div>

## About me

I'm a Cloud & DevOps Engineer with hands-on experience designing, deploying, and automating infrastructure across AWS — turning applications into reliable, production-grade systems using Infrastructure as Code, CI/CD pipelines, containerization, and Kubernetes.

More recently, I've been building **AI-augmented operational tooling** — agents and automation that use Claude to reason about infrastructure state, triage findings, and assist with diagnosis, rather than just executing static scripts.

My focus is on systems that are:

- 🔁 **Repeatable** — version-controlled, auditable, IaC-driven
- 🔒 **Secure** — least-privilege IAM, encrypted storage, zero-trust networking
- 📈 **Scalable** — multi-AZ, highly available, auto-healing
- 🧠 **Intelligent where it earns its place** — AI reasoning layered on top of deterministic infrastructure logic, not replacing it
- 📄 **Documented** — clean, handover-ready documentation teams can actually use

> "Infrastructure that only works in a demo isn't infrastructure — it's theatre."

---

## Technical skills

**☁️ Cloud Platforms** — AWS (EC2, S3, RDS, EKS, ECR, Route53, IAM, CloudWatch, Lambda, DynamoDB)

**⚙️ Infrastructure as Code** — Terraform, Ansible

**🐳 Containers & Orchestration** — Docker, Kubernetes, Kops, Helm

**🔁 CI/CD & GitOps** — GitHub Actions, Jenkins, ArgoCD, Git

**🌐 Networking & Security** — NGINX, HAProxy, Istio, Let's Encrypt, Calico

**📊 Monitoring & Observability** — Prometheus, Grafana, Datadog, CloudWatch

**🤖 AI & Automation** — Claude API (agentic tool-use, structured reasoning), n8n, Make.com, Python

**💻 OS & Scripting** — Linux, Bash, Python

---

## 🤖 AI-Augmented DevOps

Where I build AI directly into infrastructure operations — not as a chatbot bolted on top, but as a reasoning layer over deterministic, testable systems.

### Kubernetes Troubleshooting Agent
**[k8s-troubleshooting-agent](https://github.com/samklin92/k8s-troubleshooting-agent)** · Public

An agentic diagnostic tool. Claude investigates unhealthy pods the way an engineer would during a real incident — gathering evidence, deciding what to check next, and producing a specific root cause and fix rather than a generic "pod is unhealthy" report.

Built and verified against a local `kind` cluster with deliberately injected faults (`CrashLoopBackOff`, `ImagePullBackOff`, unschedulable/insufficient-resource pods). Each diagnostic tool was tested independently against real cluster behavior before being wired into the agent's decision loop.

**What made this project worth doing:** real Kubernetes behaves differently from textbook examples. A few things only surfaced through hands-on testing:
- A pod stuck in `CrashLoopBackOff` still reports `phase=Running` — health checks based on phase alone would miss it entirely.
- Image-pull failures alternate between `ImagePullBackOff` and `ErrImagePull` depending on the exact moment you poll — fault classification has to normalize across both, or detection becomes non-deterministic.
- The official Kubernetes Python client's log-fetching method, under default settings, returned corrupted output (a string containing the literal repr of bytes instead of decoded text). Found by comparing against the raw HTTP response, fixed by decoding manually.

**Stack:** Kubernetes, Python, Claude API (agentic tool-use), Docker, `kind`, Kubernetes Python Client

**Safety:** the agent's reasoning loop is hard-capped at 6 tool-call iterations to bound API/token spend; read-only RBAC scoping for the agent's service account is a documented next step, not yet implemented.

---

### Terraform Drift Detector
**[terraform-drift-detector](https://github.com/samklin92/terraform-drift-detector)** · Private

`terraform plan` tells you infrastructure has drifted. It doesn't tell you whether that drift is a security exposure or harmless noise — and in real environments, that gap is exactly why engineers stop reading drift reports.

This tool compares Terraform's desired state against live AWS state, runs a deterministic structural diff with explicit severity classification (security / structural / cosmetic), then uses Claude to explain what changed, why it likely happened, and what to do next — in either a direct technical format or a Slack-ready summary.

**Deliberately separated:** drift detection and severity classification are rule-based and unit-tested (`differ.py`, `COMPARABLE_FIELDS`) — if something's misclassified, that's a code bug. Explanation and remediation guidance are Claude's job — if that's unclear, that's a prompt issue. Keeping these apart keeps the system debuggable.

**Verified against a live AWS sandbox, not mocks** — including deliberately opening RDP (3389) to `0.0.0.0/0` on a real security group and confirming detection, correct severity, and resolution end-to-end. That process surfaced four real bugs before they could ship: a missing egress-rule check, an AWS/Terraform port-normalization mismatch for "allow all" rules, a schema mismatch between the two data sources that caused false positives on every run, and an order-sensitive sorting bug.

**Stack:** Terraform, AWS (EC2, S3, Security Groups), Python, boto3, Claude API

---

## ☸️ Kubernetes & Production Infrastructure

### Cloud-Native TaskApp — Production Kubernetes on AWS
**Flagship project.** Multi-master HA Kubernetes cluster built entirely with IaC — zero manual changes.

```
Internet → Route53 → NLB → NGINX Ingress → React Frontend
                                          → Flask Backend → PostgreSQL (EBS)
```

- VPC with 6 subnets across 3 AZs — 3 NAT Gateways, no single point of failure
- 3 control-plane + 3 worker nodes, all in private subnets, zero public IPs
- etcd distributed across 3 masters, encrypted at rest
- Calico CNI with NetworkPolicy — default deny, scoped allow rules
- Automated HTTPS via cert-manager + Let's Encrypt
- GitOps with ArgoCD — auto-sync and self-heal from GitHub
- All 25 AWS resources provisioned via Terraform — zero console changes

| Layer | Tools |
|---|---|
| Infrastructure | Terraform, Kops, AWS |
| Orchestration | Kubernetes v1.28.15, Helm |
| GitOps | ArgoCD, Kustomize |
| Security | Calico, cert-manager, NetworkPolicy |
| App | React + Flask + PostgreSQL |

🔗 [Infrastructure Repo](https://github.com/samklin92/TaskApp-Production-Grade-Cloud-Native-Deployment-) · Live Demo

---

### Production 3-Tier Banking Application
**[terraform-eks-banking-app](https://github.com/samklin92/terraform-eks-banking-app)** · Public

```
React (NGINX) → Spring Boot API (JWT) → Amazon RDS MySQL (Multi-AZ, Encrypted)
```

- Complete AWS infrastructure provisioned with Terraform (VPC, EKS, RDS, IAM)
- GitOps delivery via ArgoCD
- CI/CD with GitHub Actions (build → push → deploy)
- KMS encryption, TLS, least-privilege IAM throughout
- Multi-AZ for high availability

| Layer | Tools |
|---|---|
| Infrastructure | Terraform, AWS EKS, RDS |
| CI/CD | GitHub Actions, ArgoCD |
| Security | KMS, TLS, least-privilege IAM |
| App | React, Spring Boot, MySQL |

---

### End-to-End DevOps Platform (EKS + Istio + Observability)

A complete platform spanning infrastructure, deployment automation, service mesh security, and observability.

- EKS cluster provisioned with Terraform
- CI/CD with GitHub Actions
- Helm charts for package management
- Istio service mesh with mTLS for service-to-service security
- Canary deployments
- Full observability: Prometheus + Grafana + Alertmanager with custom alerts

| Layer | Tools |
|---|---|
| Orchestration | EKS, Helm, Istio |
| CI/CD | GitHub Actions |
| Observability | Prometheus, Grafana, Alertmanager |
| Security | mTLS, RBAC |

---

## 🏗️ Infrastructure as Code & Platform Engineering

- **[investment-order-platform-architecture](https://github.com/samklin92/investment-order-platform-architecture)** — Production-grade cloud-native investment order platform architecture using AWS, Kubernetes, Terraform, PostgreSQL, Redis, and observability tooling.
- **[sentinel-gitops-platform](https://github.com/samklin92/sentinel-gitops-platform)** — GitOps platform tooling.
- **[kubernetes-delivery-platform](https://github.com/samklin92/kubernetes-delivery-platform)** — Kubernetes delivery platform (Go templating).
- **[pyops](https://github.com/samklin92/pyops)** — AI-powered cloud operations platform: an agentic ops agent (FastAPI, Prometheus integration, RAG over runbooks, GitHub correlation) deployed to EKS via Terraform and Helm. ⭐
- **[AWS-3-Tier-Terraform-Deployment](https://github.com/samklin92/AWS-3-Tier-Terraform-Deployment)** — Structured 3-tier AWS architecture using Terraform modules with automation-friendly repo organization and remote state.
- **Medplus Cloud Deployment** — Containerized 3-tier app on AWS with HAProxy reverse proxy, HTTPS via Let's Encrypt, automated CI/CD via GitHub Actions.
- **[AWS-Serverless-Todo-API](https://github.com/samklin92/AWS-Serverless-Todo-API)** — Serverless backend: Lambda + DynamoDB + IAM, event-driven architecture.
- **[DevOps-automation-project](https://github.com/samklin92/devops-challenge-Jenkin)** — Automated EC2 deployment with Bash scripting and GitHub Actions CI/CD.

---

## 🔐 Private repositories (available on request)

| Repo | Description |
|---|---|
| Frontend-Bank-App | React frontend, Docker, deployed to AWS EKS via CI/CD and GitOps |
| Backend | Backend API, Docker, deployed to AWS EKS via CI/CD and GitOps |
| Kubernetes-Manifests | GitOps deployments with ArgoCD on AWS EKS |
| terraform-drift-detector | AI-augmented Terraform drift detection (see AI-Augmented DevOps above) |

---

## 💼 Work experience

**Cloud / DevOps Engineer (Independent Contractor)**
- Designed, built, and tested AI-augmented infrastructure tooling (agentic Kubernetes troubleshooting, Terraform drift detection with Claude-powered triage)
- Built and validated multiple AI automation pipelines (n8n, Make.com) integrating Claude, CRM, and notification systems for client and internal use

**Cloud / DevOps Engineer Intern — Digital Witch Community**
- Provisioned and managed AWS infrastructure using Terraform
- Designed and maintained CI/CD pipelines using GitHub Actions and Jenkins
- Containerized and deployed applications using Docker on EC2 and Kubernetes (EKS)
- Configured reverse proxy and load balancing using NGINX and HAProxy with SSL/TLS
- Monitored infrastructure using AWS CloudWatch and Datadog

---

## 🎓 Education & certifications

| Certification | Issuer |
|---|---|
| 🏅 AWS Certified Cloud Practitioner | Amazon Web Services |
| 🏅 DevOps & Cloud Security Certification | Digital Witch Community |
| B.Sc. Political Science | Ebonyi State University |

---

## 🤝 Let's connect

I'm actively seeking remote opportunities with engineering teams where reliability, security, and scalability are non-negotiable — and where AI-augmented tooling is treated as a serious engineering discipline, not a gimmick.

If you're building platforms that engineers depend on, let's talk.

[LinkedIn](#) · [Email](#) · [GitHub](https://github.com/samklin92)

**Open to:** DevOps Engineer · Cloud Engineer · Platform Engineer · SRE · AI Automation Engineer · Infrastructure Engineer
**Available for:** Remote · Hybrid · Relocation

<div align="center">

*📍 Lagos, Nigeria • 🌍 Open to Global Opportunities*

**`Infrastructure as Code` • `GitOps` • `Zero-Trust Networking` • `High Availability` • `Automated TLS`**

![Profile Views](https://komarev.com/ghpvc/?username=samklin92&color=brightgreen&style=flat-square)

</div>
