<h1 align="center">🚀 CI/CD Pipelines</h1>

<p align="center"><b>Build, test, and ship code automatically — every single time.</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/topic-CI%2FCD-blue?style=for-the-badge" alt="topic">
  <img src="https://img.shields.io/badge/level-beginner%20to%20intermediate-green?style=for-the-badge" alt="level">
  <img src="https://img.shields.io/badge/status-maintained-brightgreen?style=for-the-badge" alt="status">
  <img src="https://img.shields.io/badge/tools-GitHub%20Actions%20%7C%20Jenkins%20%7C%20GitLab-orange?style=for-the-badge" alt="tools">
</p>

---

## 🎯 Why this repo

Shipping software by hand is slow and risky. A CI/CD pipeline is a robot that checks your code, tests it, packages it, and deploys it. This repo explains the ideas first, then shows real pipelines in the three most popular tools: GitHub Actions, Jenkins, and GitLab CI.

## 🗺️ Learning path

```mermaid
flowchart LR
    A["01 CI/CD explained"] --> B["02 GitHub Actions"]
    B --> C["03 Jenkins"]
    C --> D["04 GitLab CI"]
    D --> E["05 Best practices and quality gates"]
```

## 📚 Table of contents

| # | Topic | What you will learn |
|---|-------|---------------------|
| 01 | [CI/CD explained](docs/01-ci-cd-explained.md) | CI vs Continuous Delivery vs Continuous Deployment |
| 02 | [GitHub Actions](docs/02-github-actions.md) | Workflows, jobs, secrets, matrix, caching |
| 03 | [Jenkins](docs/03-jenkins.md) | Declarative Jenkinsfile, agents, stages |
| 04 | [GitLab CI](docs/04-gitlab-ci.md) | `.gitlab-ci.yml`, runners, environments |
| 05 | [Best practices](docs/05-pipeline-best-practices-artifacts-and-quality-gates.md) | Artifacts, caching, quality gates, rollbacks |

## ⚡ Quick cheat sheet

```mermaid
flowchart LR
    C["Commit"] --> B["Build"] --> T["Test"] --> S["Scan"] --> A["Package artifact"] --> D["Deploy"]
```

```yaml
# Smallest useful GitHub Actions workflow: .github/workflows/ci.yml
name: ci
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: echo "run your tests here"
```

| Term | Meaning |
|------|---------|
| Pipeline | The full automated path from commit to deploy |
| Job | A group of steps that run on one machine |
| Stage | A phase, like build or test |
| Artifact | A file produced by the pipeline (jar, image, zip) |
| Runner / Agent | The machine that runs your jobs |

---

<p align="center">Part of the DevOps Hub by <a href="https://github.com/Akhilgoud01">@Akhilgoud01</a> — ⭐ star if it helped</p>
