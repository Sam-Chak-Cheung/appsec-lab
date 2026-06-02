# Security Discussion Notes

These notes provide concise explanations for common Application Security and DevSecOps topics. They are intended to support security engineering discussions, design reviews, risk workshops, and technical decision making.

The emphasis is on explaining risk clearly enough for engineering and business stakeholders to make practical control decisions.

## What is OWASP Top 10?

The OWASP Top 10 is a widely used awareness document that summarises major categories of web application security risk. It is not a full testing methodology, but it gives security and engineering teams a shared language for discussing common issues such as broken access control, injection, security misconfiguration, vulnerable components, and SSRF.

## What is SAST?

Static Application Security Testing reviews source code or code-like artefacts for insecure patterns before the application is running. SAST is useful early in development because it can run in pull requests and CI/CD pipelines. It still needs triage because findings require business and technical context.

## What is SCA?

Software Composition Analysis reviews open source dependencies and third-party components for known vulnerabilities, licensing concerns, and affected versions. SCA is important because modern applications rely heavily on external libraries, including transitive dependencies that developers may not directly see.

## What is DAST?

Dynamic Application Security Testing reviews a running application from the outside. DAST can help identify runtime behaviour such as exposed endpoints, missing headers, authentication issues, and injection behaviour. It complements SAST but does not replace code review or secure design.

## What is DevSecOps?

DevSecOps integrates security into development and operations workflows. The goal is to give teams useful security feedback early through pull request checks, CI/CD scanning, automated evidence, and clear remediation ownership. It is not only tooling; it also includes process, accountability, and engineering culture.

## Snyk vs Checkmarx

Snyk is often strong in developer-first workflows, SCA, container scanning, IaC scanning, and actionable remediation guidance. Checkmarx is often used for enterprise SAST depth, governance, and centralised AppSec programs. They can complement each other depending on organisational needs.

## SonarQube vs Snyk

SonarQube focuses strongly on code quality, maintainability, reliability, code smells, and security hotspots. Snyk focuses more directly on security workflows such as SCA, SAST, container, and IaC scanning. SonarQube helps improve code health; Snyk helps drive security remediation.

## Why A06 Matters After Log4Shell

Log4Shell showed that dependency visibility is critical. Many organisations had difficulty identifying where affected versions of Log4j existed, whether the dependency was direct or transitive, which systems were exposed, and who owned remediation. A06 is important because security teams need to know what software they run and how quickly they can respond.

## How AppSec Fits Into Cloud Security

Application security and cloud security are tightly connected. An application flaw can expose cloud data, misuse identity permissions, reach metadata services, leak secrets, or create risky network paths. Cloud-native AppSec should consider IAM, storage exposure, container security, logging, egress control, secrets management, and CI/CD deployment controls.

## Practical Discussion Framing

- Start with the risk in plain English.
- Explain the business impact.
- Name likely detection methods.
- Describe practical prevention controls.
- Discuss prioritisation, ownership, and evidence.
- Avoid presenting tools as a complete solution.

## Disclaimer

This project is for educational and defensive security purposes only.
