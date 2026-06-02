# Application Security Tools

Security tools are most valuable when they are mapped to a clear purpose in the SDLC. A tool should help a team find risk, understand ownership, prioritise remediation, or produce evidence for governance.

This section positions tools by decision value: what they detect, where they run, and how their results should be triaged.

## Tool Categories

| Category | Purpose | Example Tools |
| --- | --- | --- |
| SAST | Review source code for risky patterns before deployment | CodeQL, Checkmarx, Veracode, Snyk Code |
| SCA | Identify vulnerable open source dependencies and licensing concerns | Snyk Open Source, OWASP Dependency-Check, Veracode SCA |
| DAST | Test a running application for observable web security issues | OWASP ZAP, Veracode DAST |
| Secrets scanning | Detect exposed credentials in code and repositories | GitHub secret scanning, Gitleaks, TruffleHog |
| Container scanning | Review image packages, base images, and dependency risk | Snyk Container, Trivy |
| IaC scanning | Detect unsafe cloud and platform configuration before deployment | Snyk IaC, Trivy, Checkov |

## Tool Briefs

- [Snyk](snyk-overview.md)
- [Checkmarx](checkmarx-overview.md)
- [SonarQube](sonarqube-overview.md)
- [Veracode](veracode-overview.md)
- [GitHub CodeQL](codeql-overview.md)
- [OWASP ZAP](owasp-zap-overview.md)
- [OWASP Dependency-Check](dependency-check-overview.md)

## Practical Positioning

No single tool is an Application Security program. Mature use of tooling requires severity thresholds, triage, ownership, exception handling, remediation evidence, and feedback loops with engineering teams.
