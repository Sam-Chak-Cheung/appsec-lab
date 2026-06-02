# Application Security Lab

Author: Samuel Cheung

## Purpose

This repository is a practical Application Security portfolio project covering secure coding, OWASP Top 10 risks, DevSecOps tooling, software supply chain security, and cloud-native application security.

It is written for security engineering discussions, recruiter review, AppSec interviews, and hands-on learning. The focus is not on offensive techniques. The focus is on how security engineers identify risk, explain impact, select controls, and integrate security checks into delivery workflows.

## Why This Repo Exists

Application security is no longer only a late-stage penetration test or code review activity. Modern AppSec work connects secure design, developer education, CI/CD controls, dependency visibility, cloud configuration, and evidence-based risk management.

This repo shows how I approach AppSec as a security engineering discipline:

- explain risk in business and technical language
- map issues to OWASP Top 10 categories
- use SAST, SCA, DAST, secrets, container, and IaC scanning appropriately
- prioritise remediation based on impact and exposure
- connect application security to DevSecOps and cloud security operations

## Who It Is For

- Security Engineer / AppSec Engineer roles
- DevSecOps and Cloud Security discussions
- Recruiters and hiring managers reviewing practical security capability
- Developers looking for concise defensive security explanations
- Consultants preparing application security assessment material

## Topics Covered

- A01 Broken Access Control
- A03 Injection
- A05 Security Misconfiguration
- A06 Vulnerable and Outdated Components
- A10 Server-Side Request Forgery
- Log4Shell
- SolarWinds
- MOVEit
- Snyk, Checkmarx, SonarQube, Veracode, Trivy, CodeQL, and OWASP Dependency-Check

## AppSec, DevSecOps, and Cloud Security Connection

Good application security depends on engineering integration. SAST can help identify risky code patterns. SCA helps track vulnerable open source dependencies. Container and IaC scans help reduce deployment risk. Secrets scanning reduces credential exposure. Cloud security controls help protect identity, data, network paths, logging, and runtime environments.

The practical goal is to give teams useful feedback early, keep production risk visible, and avoid treating security as a final approval gate with no engineering context.

## How To Use This Lab

Use these notes as interview-ready explanations, secure design prompts, and examples for AppSec / DevSecOps conversations. The material is intentionally defensive and concise, with practical examples that can be adapted for awareness sessions, assessment planning, or portfolio review.

## Disclaimer

This repository is for educational and defensive security purposes only. It is not production-ready tooling, legal advice, or a substitute for environment-specific security review.
