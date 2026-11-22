<p align="center"><img src="assets/banners/_hub.svg" width="100%" alt="DevOps Docs"></p>

<p align="center">
  <img src="https://img.shields.io/badge/topics-14-00f5ff?style=for-the-badge&labelColor=0a0e17" alt="topics">
  <img src="https://img.shields.io/badge/docs-88%20files-7c4dff?style=for-the-badge&labelColor=0a0e17" alt="docs">
  <img src="https://img.shields.io/badge/diagrams-166-ff2bd6?style=for-the-badge&labelColor=0a0e17" alt="diagrams">
  <img src="https://img.shields.io/badge/level-beginner%20to%20pro-39ff14?style=for-the-badge&labelColor=0a0e17" alt="level">
</p>

## What is this?

One repo, 14 DevOps topics. Every doc has a plain-English explanation with a real-life analogy, Mermaid diagrams, hands-on commands, common mistakes and a recap. GitHub renders the diagrams automatically.

## 🗺️ Learning path

```mermaid
flowchart TD
    A["🧭 devops-fundamentals"] --> B["🐧 linux-for-devops"]
    B --> C["🌿 git-and-github"]
    B --> D["🌐 networking-for-devops"]
    C --> E["🐍 scripting-bash-python"]
    D --> E
    E --> F["🔁 cicd-pipelines"]
    F --> G["🐳 docker-containers"]
    G --> H["☸️ kubernetes-guide"]
    H --> I["⛵ helm-and-gitops"]
    F --> J["🏗️ infrastructure-as-code"]
    J --> K["☁️ cloud-fundamentals"]
    I --> L["📊 monitoring-observability"]
    K --> L
    L --> M["🛡️ devsecops-security"]
    M --> N["🗺️ devops-roadmap-and-interviews"]
```

## 📚 Topics

| | Topic | What you will learn |
|---|---|---|
| 🧭 | [devops-fundamentals](devops-fundamentals) | Culture, lifecycle, Agile, deployment strategies, DORA, SRE |
| 🐧 | [linux-for-devops](linux-for-devops) | Filesystem, permissions, systemd, cron, grep/sed/awk, SSH |
| 🌿 | [git-and-github](git-and-github) | Git internals, branching, PRs, GitFlow, trunk-based, GitHub features |
| 🌐 | [networking-for-devops](networking-for-devops) | OSI, TCP/IP, subnets, DNS, TLS, load balancers, troubleshooting |
| 🐍 | [scripting-bash-python](scripting-bash-python) | Bash, Python, boto3, YAML/JSON |
| 🔁 | [cicd-pipelines](cicd-pipelines) | GitHub Actions, Jenkins, GitLab CI, quality gates |
| 🐳 | [docker-containers](docker-containers) | Images, Dockerfile, multi-stage, networking, Compose, security |
| ☸️ | [kubernetes-guide](kubernetes-guide) | Architecture, Pods, Services, storage, HPA, RBAC, kubectl |
| ⛵ | [helm-and-gitops](helm-and-gitops) | Helm, GitOps, Argo CD, Kustomize |
| 🏗️ | [infrastructure-as-code](infrastructure-as-code) | Terraform, Ansible, CloudFormation, Pulumi |
| ☁️ | [cloud-fundamentals](cloud-fundamentals) | Cloud models, AWS core services, VPC, IAM, Azure/GCP, cost |
| 📊 | [monitoring-observability](monitoring-observability) | Prometheus, Grafana, ELK/Loki, tracing, incident response |
| 🛡️ | [devsecops-security](devsecops-security) | Shift-left, secrets, container security, SAST/DAST, supply chain |
| 🗺️ | [devops-roadmap-and-interviews](devops-roadmap-and-interviews) | Roadmap, portfolio projects, interview Q&A, certifications |

---

By [@Akhilgoud01](https://github.com/Akhilgoud01) — ⭐ star if it helped
