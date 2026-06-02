# DevSecOps

DevSecOps is the practice of integrating security into software delivery so teams receive useful feedback early and leaders retain visibility over production risk. The goal is not to add friction for its own sake. The goal is to make security decisions traceable, repeatable, and proportionate to the risk being shipped.

## Practical Pipeline Model

A secure delivery workflow commonly includes:

- developer secure coding practices before pull request
- pull request review for authentication, authorization, data handling, dependencies, and cloud changes
- SAST for risky source code patterns
- SCA for vulnerable direct and transitive dependencies
- secrets scanning for exposed tokens and credentials
- container scanning for base image and package risk
- IaC scanning for unsafe cloud configuration
- risk-based approval for material findings
- deployment evidence linking code, scans, approvals, and production changes

See the detailed [DevSecOps pipeline overview](../docs/devsecops-pipeline-overview.md).

See the [DevSecOps reference architecture](reference-architecture.md) for a practical control placement model.

## Security Automation Principles

Effective security automation should:

- run close to where engineers already work
- produce clear, actionable findings
- distinguish blocking risk from advisory feedback
- identify ownership and remediation paths
- record evidence for audit and governance
- allow documented exceptions where business context justifies residual risk

Automation is strongest when it supports human judgement rather than replacing it. A critical dependency finding on an internet-facing payment service deserves different treatment from the same finding in an isolated internal prototype.

## Example Tool Placement

| SDLC Stage | Security Activity | Example Tools |
| --- | --- | --- |
| Commit | local hygiene and secrets prevention | pre-commit checks, Gitleaks |
| Pull request | code and dependency review | CodeQL, Snyk, Checkmarx |
| Build | dependency, container, and IaC scanning | Snyk, Trivy, OWASP Dependency-Check |
| Release | risk approval and evidence capture | GitHub Actions, ticketing, AppSec review |
| Runtime | monitoring and response | cloud logs, SIEM, vulnerability monitoring |

## Practical Summary

DevSecOps means building security into delivery pipelines so teams can identify and manage risk before production. Mature programs combine automation with ownership, triage, exception handling, and business context. The most useful pipelines help engineers fix problems earlier while giving security teams visibility over what risk is accepted, remediated, or still open.
