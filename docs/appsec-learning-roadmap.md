# AppSec Learning Roadmap

This roadmap is designed for a security engineer moving from application security fundamentals into DevSecOps, cloud-native security, and AI application security.

## Phase 1: OWASP Top 10 Foundation

Build a practical understanding of common application risks and how to explain them clearly.

Focus areas:

- Broken access control
- Injection
- Security misconfiguration
- Vulnerable and outdated components
- SSRF
- Secure coding basics
- Authentication vs authorization
- Error handling and logging

Practical outputs:

- Explain each OWASP risk in plain English.
- Map findings to business impact.
- Review simple code examples and identify the safer pattern.
- Describe prevention and detection controls without relying on tool names alone.

## Phase 2: SAST, SCA, and DAST Tools

Understand where different scanning methods fit and what each one can and cannot prove.

Focus areas:

- SAST for source code patterns
- SCA for dependency and CVE exposure
- DAST for running application behaviour
- Secrets scanning for exposed credentials
- Triage, false positives, and remediation ownership

Practical outputs:

- Compare Snyk, Checkmarx, SonarQube, Veracode, CodeQL, and OWASP Dependency-Check.
- Explain the difference between a tool finding and confirmed risk.
- Prioritise findings by exploitability, exposure, data sensitivity, and fix effort.

## Phase 3: CI/CD Security Integration

Move application security checks earlier into development and release workflows.

Focus areas:

- Pull request checks
- CodeQL or SAST scanning
- SCA dependency checks
- Secrets scanning
- Container scanning
- IaC scanning
- Security gates and exception handling

Practical outputs:

- Design a secure CI/CD workflow.
- Decide which checks should warn, block, or require security approval.
- Define evidence needed for audit, risk, and remediation tracking.

## Phase 4: Cloud-Native Application Security

Connect application risk to cloud identity, data, network, and runtime controls.

Focus areas:

- Managed identity and least privilege
- API security
- Cloud storage exposure
- Container and Kubernetes security
- Logging and monitoring
- Key management and secrets handling
- Network egress and SSRF protection

Practical outputs:

- Explain how application flaws can become cloud security incidents.
- Review cloud-native deployment risks in CI/CD.
- Map AppSec controls to cloud security architecture decisions.

## Phase 5: AI Application Security

Extend AppSec thinking to LLM and AI-enabled applications.

Focus areas:

- Prompt injection
- Data leakage
- RAG source governance
- Insecure tool use
- Human approval controls
- Model output handling
- AI governance and monitoring

Practical outputs:

- Threat model an AI application.
- Define approval gates for high-impact model actions.
- Review how AI systems use tools, retrieval data, logs, and user input.

## Disclaimer

This project is for educational and defensive security purposes only.
