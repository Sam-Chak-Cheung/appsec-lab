# A06 Vulnerable and Outdated Components

## Description

Vulnerable and outdated components occur when applications rely on libraries, frameworks, containers, or platforms with known security weaknesses or unsupported versions.

## Why It Matters

Modern applications depend on many third-party components. A single vulnerable dependency can affect many systems, especially when asset inventory, software composition analysis, and patch management are immature.

## Example Scenario

An application uses an affected version of Apache Log4j. Without an accurate dependency inventory and SCA process, the organisation may not quickly know which applications require urgent attention during a major vulnerability event such as Log4Shell.

## Detection Methods

- SCA
- Dependency inventory
- SBOM review
- Container scanning
- Vulnerability management
- Security testing
- Logging and monitoring

## Prevention

- Use Snyk Open Source or another SCA tool to identify vulnerable dependencies.
- Maintain an SBOM for important applications.
- Define patch management and exception processes.
- Remove unused dependencies.
- Monitor CVEs affecting direct and transitive dependencies.
- Test updates before deployment and track remediation ownership.

## Related Tools

- Snyk Open Source
- Checkmarx
- Veracode
- SonarQube
- OWASP ZAP
- Dependency-Check

## Interview Talking Points

- SCA focuses on open source dependency risk, including direct and transitive dependencies.
- SBOMs improve visibility but still need monitoring and response processes.
- Log4Shell is a strong example of why dependency inventory matters.
- Patch management should balance urgency, testing, business risk, and compensating controls.
- DevSecOps moves dependency visibility earlier into development and CI/CD.

## Disclaimer

This project is for educational and defensive security purposes only.
