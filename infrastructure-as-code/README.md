<h1 align="center">🏗️ Infrastructure as Code</h1>

<p align="center"><b>Build servers, networks, and clouds from code, not from clicking.</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/topic-Terraform%20%7C%20Ansible%20%7C%20IaC-7B42BC?style=for-the-badge" alt="topic">
  <img src="https://img.shields.io/badge/level-beginner%20to%20intermediate-2ea44f?style=for-the-badge" alt="level">
  <img src="https://img.shields.io/badge/status-complete-blue?style=for-the-badge" alt="status">
</p>

## 💡 Why this repo

Clicking in a cloud console is slow and hard to repeat. Infrastructure as Code (IaC) lets you write what you want in files, keep them in Git, review them, and create the same setup again and again. These docs cover the main ideas, then Terraform, Ansible, and a short look at CloudFormation and Pulumi.

## 🗺️ Learning path

```mermaid
flowchart LR
    A["01 IaC concepts"] --> B["02 Terraform basics"]
    B --> C["03 State, modules, workspaces"]
    C --> D["04 Ansible basics"]
    D --> E["05 Other tools and choosing"]
```

## 📚 Table of contents

| # | Doc | What you will learn |
|---|-----|---------------------|
| 01 | [IaC concepts](docs/01-iac-concepts.md) | Declarative vs imperative, idempotency, drift |
| 02 | [Terraform basics](docs/02-terraform-basics.md) | Providers, resources, variables, outputs, plan and apply |
| 03 | [State, modules, workspaces](docs/03-terraform-state-modules-workspaces.md) | Remote state in S3, locking, reusable modules |
| 04 | [Ansible basics](docs/04-ansible-basics.md) | Inventory, playbooks, roles |
| 05 | [CloudFormation, Pulumi, and choosing tools](docs/05-cloudformation-and-pulumi-overview-and-choosing-tools.md) | Compare tools and pick one |

## ⚡ Quick cheat sheet

```bash
terraform init          # download providers
terraform fmt -recursive
terraform validate
terraform plan -out tf.plan
terraform apply tf.plan
terraform destroy

ansible all -i inventory.ini -m ping
ansible-playbook -i inventory.ini site.yml --check --diff
```

---
Part of the DevOps Hub by [@Akhilgoud01](https://github.com/Akhilgoud01) — ⭐ star if it helped
