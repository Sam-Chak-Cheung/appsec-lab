# A05 Security Misconfiguration

## Description

Security misconfiguration occurs when systems, applications, cloud services, or frameworks are deployed with unsafe defaults, excessive permissions, missing hardening, or incomplete security settings.

## Why It Matters

Misconfiguration can expose sensitive data, administration interfaces, debug information, or internet-facing services. It is common in fast-moving environments where infrastructure, application, and cloud settings change frequently.

## Example Scenario

A web application is deployed with debug mode enabled and verbose error messages. When an error occurs, the response exposes internal paths, framework details, and configuration hints.

## Common Examples

- Default passwords
- Overly permissive cloud storage
- Debug mode enabled
- Missing security headers
- Excessive error messages
- Unrestricted administration interfaces
- Unnecessary services enabled

## Detection Methods

- Code review
- SAST
- DAST
- Security testing
- Logging and monitoring
- Configuration baseline review

## Prevention

- Define secure configuration baselines.
- Disable debug mode and verbose error messages in production.
- Change or disable default credentials.
- Apply security headers where appropriate.
- Restrict cloud storage and administration interfaces.
- Automate configuration checks in CI/CD and cloud posture management.

## Related Tools

- Snyk
- Checkmarx
- Veracode
- SonarQube
- OWASP ZAP
- Dependency-Check

## Interview Talking Points

- Misconfiguration is often a process and ownership issue as much as a technical issue.
- Cloud storage exposure should be reviewed through both configuration and data sensitivity.
- Security headers reduce common browser-side risks but do not replace secure design.
- Infrastructure as Code scanning helps catch issues before deployment.
- Baselines should be reviewed after major platform, framework, or architecture changes.

## Disclaimer

This project is for educational and defensive security purposes only.
