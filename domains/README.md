# Application Security Domains

This section organises the repository around five domains that reflect modern Application Security work. The domains are intentionally practical: each one connects technical risk to business impact, detection, prevention, and security engineering decisions.

Use this page as the main map for how the knowledge base separates application risk, tooling, delivery, supply chain, and AI security.

## Domain 1: OWASP Top 10

Purpose: understand common application security risks and how they affect real systems.

Key topics:

- [A01 Broken Access Control](../docs/A01-Broken-Access-Control.md)
- [A03 Injection](../docs/A03-Injection.md)
- [A05 Security Misconfiguration](../docs/A05-Security-Misconfiguration.md)
- [A06 Vulnerable and Outdated Components](../docs/A06-Vulnerable-Components.md)
- [A10 Server-Side Request Forgery](../docs/A10-SSRF.md)

Professional focus:

- risk and business impact
- detection through code review, SAST, DAST, and monitoring
- prevention through design, secure coding, configuration, and least privilege
- clear security explanations that avoid exploit-led framing

## Domain 2: Application Security Tooling

Purpose: understand how security risks are identified and prioritised across the SDLC.

Key topics:

- SAST
- SCA
- DAST
- secrets scanning
- container scanning
- IaC scanning

Representative tools:

- [Snyk](../tools/snyk-overview.md)
- [Checkmarx](../tools/checkmarx-overview.md)
- [SonarQube](../tools/sonarqube-overview.md)
- [Veracode](../tools/veracode-overview.md)
- [GitHub CodeQL](../tools/codeql-overview.md)
- [OWASP ZAP](../tools/owasp-zap-overview.md)
- [OWASP Dependency-Check](../tools/dependency-check-overview.md)

Professional focus:

- where each tool fits in development and delivery
- what each tool is strong at detecting
- when human triage is required
- how findings become engineering work, not only reports

## Domain 3: DevSecOps

Purpose: understand how security integrates into software delivery.

Key topics:

- Secure SDLC
- GitHub Actions
- CI/CD security
- CodeQL
- container scanning
- dependency scanning
- secrets scanning

Professional focus:

- security automation
- pull request feedback
- risk-based release decisions
- exception handling and evidence capture

## Domain 4: Software Supply Chain Security

Purpose: understand dependency, vendor, and third-party software risk.

Key topics:

- Log4Shell
- SolarWinds
- MOVEit
- SBOMs
- dependency risk
- third-party components

Professional focus:

- software inventory
- component visibility
- patching and remediation ownership
- continuous monitoring
- supplier and integration risk

## Domain 5: AI Application Security

Purpose: understand emerging AI security risks in enterprise applications.

Key topics:

- OWASP LLM Top 10
- prompt injection
- RAG security
- data leakage
- AI governance
- human approval controls

Professional focus:

- trust boundaries between users, prompts, models, tools, and data
- safe retrieval and data access
- output validation and human review
- governance for business-critical AI workflows
