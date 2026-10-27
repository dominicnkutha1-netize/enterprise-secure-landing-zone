# Enterprise Automated Cloud Landing Zone with Security Guardrails & Event-Driven Remediation

[![DevSecOps Pipeline](https://github.com/dominicnkutha1-netize/enterprise-secure-landing-zone/actions/workflows/devsecops-pipeline.yml/badge.svg)](https://github.com/dominicnkutha1-netize/enterprise-secure-landing-zone/actions)
![Terraform](https://img.shields.io/badge/Terraform-1.5+-purple?style=for-the-badge&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-Enterprise-orange?style=for-the-badge&logo=amazonaws&logoColor=white)
![Security](https://img.shields.io/badge/Checkov-Passing-green?style=for-the-badge)

## 🎯 Executive Summary
An enterprise-grade, multi-account AWS landing zone designed with strict Zero Trust architecture, automated compliance guardrails, shift-left DevSecOps pipelines, and self-healing cloud security operations.

## 🏗️ Architectural Overview

\	ext
┌─────────────────────────────────────────────────────────────────────────┐
│                          AWS ORGANIZATION / ROOT                        │
└────────────────────────────┬────────────────────────────────────────────┘
                             │
       ┌─────────────────────┴──────────────────────┐
       ▼                                            ▼
┌──────────────────────────────┐        ┌──────────────────────────────┐
│       SECURITY OU            │        │        WORKLOADS OU          │
├──────────────────────────────┤        ├──────────────────────────────┤
│  Log Archive S3 Bucket       │        │  Production / Staging VPCs   │
│  (Object Lock, KMS Encrypted)│        │  Private Subnets Only        │
│                              │        │                              │
│  SecurityHub / GuardDuty     │        │  CloudTrail Logs Sent to Log │
│                              │        │  Archive                     │
│  Lambda Auto-Remediation     │◄───────┼─ EventBridge Rules (S3 Public│
│  (Fixes bad S3/SecGroups)    │        │  Block / Port 22 Closure)   │
└──────────────────────────────┘        └──────────────────────────────┘
\\n
## 🚀 Core Components

1. **Multi-Account Landing Zone & Guardrails**
   - **Service Control Policies (SCPs):** Enforces hard governance boundaries.
   - **Remote State Locking:** S3 backend integrated with DynamoDB.

2. **Automated DevSecOps Pipeline**
   - **GitHub Actions:** Runs Checkov static analysis and Infracost on PRs.

3. **Event-Driven Auto-Remediation**
   - **Self-Healing Infrastructure:** EventBridge + Lambda for instant remediation.

## 👨‍💻 Author
Built with 🛡️ by [Dr Dominic Nkutha](https://github.com/dominicnkutha1-netize)
