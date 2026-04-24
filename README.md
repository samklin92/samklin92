<div align="center">

# Hi, I'm Ogaji Igwe Samuel
### Cloud & DevOps Engineer

**I build production-ready cloud systems on AWS — automated, secure, and scalable.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Igwe%20Ogaji-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/igwe-ogaji)
[![GitHub](https://img.shields.io/badge/GitHub-samklin92-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/samklin92)
[![Email](https://img.shields.io/badge/Email-samklinofficial91%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:samklinofficial91@gmail.com)
[![Location](https://img.shields.io/badge/📍-Lagos%2C%20Nigeria-4CAF50?style=for-the-badge)](https://github.com/samklin92)

</div>

---

## 👨‍💻 About Me

I'm a **Cloud & DevOps Engineer** with hands-on experience designing, deploying, and automating infrastructure across **AWS** — turning applications into reliable, production-grade systems using Infrastructure as Code, CI/CD pipelines, containerization, and Kubernetes.

My focus is on building systems that are:
- 🔁 **Repeatable** — version-controlled, auditable, IaC-driven
- 🔒 **Secure** — least-privilege IAM, encrypted storage, zero-trust networking
- 📈 **Scalable** — multi-AZ, highly available, auto-healing
- 📄 **Documented** — clean handover-ready documentation teams can actually use

> *"Infrastructure that only works in a demo isn't infrastructure — it's theatre."*

---

## 🛠️ Technical Skills

### ☁️ Cloud Platforms
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![EC2](https://img.shields.io/badge/EC2-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![S3](https://img.shields.io/badge/S3-569A31?style=flat-square&logo=amazons3&logoColor=white)
![RDS](https://img.shields.io/badge/RDS-527FFF?style=flat-square&logo=amazonrds&logoColor=white)
![EKS](https://img.shields.io/badge/EKS-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![ECR](https://img.shields.io/badge/ECR-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![Route53](https://img.shields.io/badge/Route53-8C4FFF?style=flat-square&logo=amazonaws&logoColor=white)
![IAM](https://img.shields.io/badge/IAM-DD344C?style=flat-square&logo=amazonaws&logoColor=white)
![CloudWatch](https://img.shields.io/badge/CloudWatch-FF4F8B?style=flat-square&logo=amazonaws&logoColor=white)
![Lambda](https://img.shields.io/badge/Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white)
![DynamoDB](https://img.shields.io/badge/DynamoDB-4053D6?style=flat-square&logo=amazondynamodb&logoColor=white)

### ⚙️ Infrastructure as Code
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white)

### 🐳 Containers & Orchestration
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Kops](https://img.shields.io/badge/Kops-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white)

### 🔁 CI/CD & GitOps
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=flat-square&logo=argo&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

### 🌐 Networking & Security
![NGINX](https://img.shields.io/badge/NGINX-009639?style=flat-square&logo=nginx&logoColor=white)
![HAProxy](https://img.shields.io/badge/HAProxy-106DA9?style=flat-square&logo=haproxy&logoColor=white)
![Istio](https://img.shields.io/badge/Istio-466BB0?style=flat-square&logo=istio&logoColor=white)
![Let's Encrypt](https://img.shields.io/badge/Let's%20Encrypt-003A70?style=flat-square&logo=letsencrypt&logoColor=white)
![Calico](https://img.shields.io/badge/Calico%20CNI-FB8C00?style=flat-square&logo=linux&logoColor=white)

### 📊 Monitoring & Observability
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Datadog](https://img.shields.io/badge/Datadog-632CA6?style=flat-square&logo=datadog&logoColor=white)
![CloudWatch](https://img.shields.io/badge/CloudWatch-FF4F8B?style=flat-square&logo=amazonaws&logoColor=white)

### 💻 OS & Scripting
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

---

## 🚀 Featured Projects

---

### 🏆 Cloud-Native TaskApp — Production Kubernetes on AWS
> *Multi-master HA Kubernetes cluster built entirely with IaC — zero manual changes*

**The flagship project.** Designed and deployed a full production-grade cloud-native application on AWS from scratch using Kops, Terraform, and GitOps.

```
Internet → Route53 → NLB → NGINX Ingress → React Frontend
                                          → Flask Backend → PostgreSQL (EBS)
```

**What was built:**
- ✅ VPC with 6 subnets across 3 AZs — 3 NAT Gateways (no SPOF)
- ✅ 3 control-plane + 3 worker nodes — all in private subnets, zero public IPs
- ✅ etcd distributed across 3 masters — encrypted at rest
- ✅ Calico CNI with NetworkPolicy — default deny, scoped allow rules
- ✅ Automated HTTPS via cert-manager + Let's Encrypt
- ✅ GitOps with ArgoCD — auto-sync + self-heal from GitHub
- ✅ Kustomize overlays — base + prod environments
- ✅ All 25 AWS resources provisioned via Terraform — zero console changes

| Stack | Tools |
|-------|-------|
| Infrastructure | Terraform, Kops, AWS |
| Orchestration | Kubernetes v1.28.15, Helm |
| GitOps | ArgoCD, Kustomize |
| Security | Calico, cert-manager, NetworkPolicy |
| App | React + Flask + PostgreSQL |

🔗 [Infrastructure Repo](https://github.com/samklin92/samklin92-taskapp-capstone) • [App Repo](https://github.com/samklin92/taskapp-app) • [Live Demo](https://taskapp.samklin.online)

---

### 🏦 Production 3-Tier Banking Application (AWS EKS)
> *terraform-eks-banking-app*

Deployed a production-grade 3-tier online banking application on AWS using IaC, Kubernetes, and GitOps principles.

**Architecture:**
```
React (NGINX) → Spring Boot API (JWT) → Amazon RDS MySQL (Multi-AZ, Encrypted)
```

**Key achievements:**
- Provisioned complete AWS infrastructure with Terraform (VPC, EKS, RDS, IAM)
- Implemented GitOps with ArgoCD for automated application delivery
- Built CI/CD pipelines with GitHub Actions (build → push → deploy)
- Enforced KMS encryption, TLS, and least-privilege IAM policies
- Multi-AZ architecture for high availability

| Stack | Tools |
|-------|-------|
| Infrastructure | Terraform, AWS EKS, RDS |
| CI/CD | GitHub Actions, ArgoCD |
| Security | KMS, TLS, IAM Least Privilege |
| App | React, Spring Boot, MySQL |

---

### 🔧 End-to-End DevOps Platform (EKS + Istio + Observability)
> *Production DevOps Platform on AWS*

Built a complete DevOps platform covering infrastructure, deployment automation, service mesh security, and full observability.

**Key achievements:**
- Provisioned an Amazon EKS cluster with Terraform
- CI/CD pipeline with GitHub Actions (build → push → deploy)
- Helm charts for Kubernetes package management
- Istio service mesh with mTLS for secure service-to-service communication
- Canary deployments for controlled releases
- Full observability stack — Prometheus + Grafana + Alertmanager
- Custom alerts for CPU, memory, and application health

| Stack | Tools |
|-------|-------|
| Orchestration | EKS, Helm, Istio |
| CI/CD | GitHub Actions |
| Observability | Prometheus, Grafana, Alertmanager |
| Security | mTLS, RBAC |

---

### 🏥 Medplus Cloud Deployment (3-Tier Architecture)
> *Containerised 3-tier app on AWS with automated CI/CD*

- Deployed containerised 3-tier application on AWS
- CI/CD pipelines with GitHub Actions for automated deployment
- Container image management via Amazon ECR
- HAProxy as reverse proxy with HTTPS (Let's Encrypt)
- Secure networking and controlled traffic flow across tiers

---

### ☁️ AWS 3-Tier Terraform Deployment
> *[AWS-3-Tier-Terraform-Deployment](https://github.com/samklin92)*

Structured 3-tier AWS architecture using Terraform modules with automation-friendly repo organisation and remote state management.

---

### ⚡ Serverless Todo API (AWS Lambda + DynamoDB)
> *[AWS-Serverless-Todo-API](https://github.com/samklin92)*

Scalable serverless backend using Lambda + DynamoDB + IAM — demonstrating event-driven architecture with fully managed AWS services.

---

### 🤖 DevOps Automation — AWS EC2 Deployments
> *[DevOps-automation-project](https://github.com/samklin92)*

Automated application deployment on AWS EC2 using Bash scripting and GitHub Actions CI/CD. Server automation, repeatable deployment workflow, Linux fundamentals.

---

### 🌐 Portfolio Website with CI/CD
> *(https://github.com/samklin92)*

---

### 🔐 Private Repositories *(Available on Request)*

| Repo | Description |
|------|-------------|
| `Frontend-Bank-App` | React frontend, Docker, deployed to AWS EKS via CI/CD and GitOps |
| `Backend` | Backend API, Docker, deployed to AWS EKS via CI/CD and GitOps |
| `Kubernetes-Manifests` | GitOps deployments with ArgoCD on AWS EKS |

---

## 💼 Work Experience

### Cloud / DevOps Engineer Intern — Digital Witch Community
- Provisioned and managed AWS infrastructure using Terraform
- Designed and maintained CI/CD pipelines using GitHub Actions and Jenkins
- Containerised and deployed applications using Docker on EC2 and Kubernetes (EKS)
- Configured reverse proxy and load balancing using NGINX and HAProxy with SSL/TLS
- Monitored infrastructure using AWS CloudWatch and Datadog

---

## 🎓 Education & Certifications

| Certification | Issuer |
|---------------|--------|
| 🏅 AWS Certified Cloud Practitioner | Amazon Web Services |
| 🏅 DevOps & Cloud Security Certification | Digital Witch Community |

**B.Sc. Political Science** — Ebonyi State University

---

## 📊 GitHub Stats

<div align="center">

![Samuel's GitHub Stats](https://github-readme-stats.vercel.app/api?username=samklin92&show_icons=true&theme=tokyonight&hide_border=true&count_private=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=samklin92&layout=compact&theme=tokyonight&hide_border=true)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=samklin92&theme=tokyonight&hide_border=true)

</div>

---

## 🤝 Let's Connect

I'm actively seeking opportunities with **automation-driven engineering teams** where reliability, security, and scalability are non-negotiable.

If you're building platforms that engineers depend on — **let's talk.**

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/igwe-ogaji)
[![Email](https://img.shields.io/badge/Email-Hire%20Me-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:samklinofficial91@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/samklin92)

**Open to:** DevOps Engineer · Cloud Engineer · Platform Engineer · SRE · Infrastructure Engineer

**Available for:** Remote · Hybrid · Relocation

</div>

---

<div align="center">

*📍 Lagos, Nigeria • 🌍 Open to Global Opportunities*

**`Infrastructure as Code` • `GitOps` • `Zero-Trust Networking` • `High Availability` • `Automated TLS`**

![Profile Views](https://komarev.com/ghpvc/?username=samklin92&color=brightgreen&style=flat-square)

</div>
