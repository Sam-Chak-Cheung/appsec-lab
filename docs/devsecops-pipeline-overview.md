# DevSecOps Pipeline Overview

This document describes a practical secure CI/CD pipeline for application teams. The aim is to provide useful security feedback early while keeping risk, ownership, and exception handling visible.

## Pipeline Flow

Developer commit
-> Pull request
-> SAST
-> SCA
-> Secrets scanning
-> Container scan
-> IaC scan
-> Security approval
-> Deploy

## 1. Developer Commit

Security starts before the pull request. Developers should use secure coding patterns, dependency hygiene, local linting, and approved secrets handling.

Useful controls:

- Secure coding standards
- Pre-commit checks where appropriate
- Dependency lock files
- Local secret scanning

## 2. Pull Request

Pull requests are the first structured review point. Security should be part of normal engineering review, not a separate last-minute activity.

Review focus:

- Authentication and authorization changes
- Input handling
- Sensitive data flows
- New dependencies
- Cloud or infrastructure changes
- Logging and error handling

## 3. SAST

Static Application Security Testing reviews source code for risky patterns.

Example tools:

- GitHub CodeQL
- Snyk Code
- Checkmarx
- Veracode

Best used for:

- Injection patterns
- Unsafe deserialization
- Hardcoded secrets indicators
- Risky API usage
- Access control review prompts

## 4. SCA

Software Composition Analysis checks open source dependencies for known vulnerabilities and licensing concerns.

Example tools:

- Snyk Open Source
- OWASP Dependency-Check
- GitHub Dependabot

Best used for:

- CVE visibility
- Direct and transitive dependency risk
- Upgrade guidance
- Dependency inventory and SBOM support

## 5. Secrets Scanning

Secrets scanning helps detect exposed credentials before they reach production or public repositories.

Example tools:

- GitHub secret scanning
- TruffleHog
- Gitleaks

Best used for:

- API keys
- Tokens
- Private keys
- Cloud credentials
- Accidental credential commits

## 6. Container Scan

Container scanning reviews base images, operating system packages, application dependencies, and image configuration.

Example tools:

- Trivy
- Snyk Container
- GitHub container scanning integrations

Best used for:

- Vulnerable base images
- Outdated packages
- Image hardening gaps
- Runtime risk prioritisation

## 7. IaC Scan

Infrastructure as Code scanning reviews deployment templates before cloud resources are created or changed.

Example tools:

- Snyk IaC
- Trivy
- Checkov

Best used for:

- Public cloud storage exposure
- Overly permissive IAM
- Missing encryption
- Unsafe network exposure
- Logging and monitoring gaps

## 8. Security Approval

Not every finding should block every release. Security approval should focus on material risk, compensating controls, business context, and clear ownership.

Approval should capture:

- Risk rating
- Business impact
- Remediation owner
- Due date
- Exception reason, if accepted
- Evidence of review

## 9. Deploy

Deployment should preserve traceability between code, pipeline results, approvals, and production changes.

Deployment evidence:

- Build identifier
- Commit SHA
- Scan results
- Approval record
- Deployment environment
- Rollback plan

## Practical Tool Mix

| Pipeline Area | Example Tools |
| --- | --- |
| CI/CD orchestration | GitHub Actions |
| SAST | CodeQL, Snyk Code, Checkmarx, Veracode |
| SCA | Snyk Open Source, OWASP Dependency-Check, Dependabot |
| Secrets scanning | GitHub secret scanning, Gitleaks, TruffleHog |
| Container scanning | Trivy, Snyk Container |
| IaC scanning | Snyk IaC, Trivy, Checkov |
| Code quality | SonarQube |

## Disclaimer

This project is for educational and defensive security purposes only.
