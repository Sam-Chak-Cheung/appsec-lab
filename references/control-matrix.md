# Application Security Control Matrix

This matrix connects common application security risks to practical controls, tooling, evidence, and ownership. It is designed to support assessment planning, remediation tracking, and security governance.

| Risk Area | Practical Controls | Tooling Support | Evidence | Primary Owner |
| --- | --- | --- | --- | --- |
| Broken access control | server-side authorization, tenant checks, least privilege, negative tests | code review, SAST, DAST, API tests | authorization tests, policy logic, access logs | application team |
| Injection | parameterized queries, input validation, safe APIs, least-privileged service accounts | SAST, DAST, code review | fixed code paths, test cases, scanner results | application team |
| Security misconfiguration | secure baselines, hardened defaults, environment separation, IaC review | IaC scanning, CSPM, DAST | configuration review, pipeline results, exception records | platform and cloud teams |
| Vulnerable components | SCA, dependency ownership, SBOM, patch workflow, exception process | Snyk, Dependency-Check, Dependabot, Trivy | dependency report, upgrade PR, SBOM, risk acceptance | application and AppSec teams |
| SSRF | destination allowlists, egress filtering, metadata protection, outbound logging | code review, SAST, DAST, cloud network review | egress rules, tests, logs, architecture review | application and cloud teams |
| Secrets exposure | managed secrets, no secrets in code, rotation process, repository scanning | GitHub secret scanning, Gitleaks, TruffleHog | scan results, rotation records, vault configuration | platform and application teams |
| Container risk | minimal base images, image scanning, patching, non-root runtime | Trivy, Snyk Container | image scan results, Dockerfile review, deployment evidence | platform team |
| Cloud data exposure | private storage, encryption, IAM review, logging | IaC scanning, cloud posture review | storage policy, access logs, encryption evidence | cloud platform team |
| CI/CD compromise | least-privileged tokens, protected branches, artifact integrity, approval gates | GitHub Actions controls, CodeQL, dependency review | workflow config, approval records, build provenance | platform and engineering leads |
| AI/RAG data leakage | retrieval authorization, data classification, prompt logging controls, human approval | access tests, logging review, AI risk assessment | role-based retrieval tests, approval logs, data source inventory | application and AI governance teams |

## How to Use This Matrix

Use the matrix to avoid treating a scanner finding as the whole security story. A practical control decision should identify:

- which risk is being reduced
- which control is expected to reduce it
- which tool or review method provides signal
- what evidence proves the control is working
- who owns remediation or risk acceptance
