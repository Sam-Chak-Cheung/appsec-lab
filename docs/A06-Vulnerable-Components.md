# A06 Vulnerable and Outdated Components

## Description

Vulnerable and outdated components occur when applications rely on libraries, frameworks, containers, plugins, runtime platforms, or infrastructure components with known security weaknesses or unsupported versions.

## Why It Matters

Modern applications depend on many third-party and open source components. A single vulnerable dependency can affect many systems, especially when asset inventory, dependency visibility, software composition analysis, and patch management are immature.

This risk is not only technical. It affects incident response speed, business continuity, customer trust, audit evidence, and regulatory reporting.

## SCA Explanation

Software Composition Analysis helps identify open source dependencies, known CVEs, affected versions, licensing concerns, and available fixes.

SCA is useful because it can detect:

- direct dependencies listed by the application
- transitive dependencies pulled in by other packages
- vulnerable package versions
- known CVEs and advisories
- recommended upgrades or remediation paths

## SBOM Explanation

A Software Bill of Materials is an inventory of software components used by an application or system. SBOMs improve visibility into what software exists, where it is used, and which systems may be affected when a new vulnerability is disclosed.

An SBOM is most useful when it is connected to:

- asset ownership
- application criticality
- deployment environment
- vulnerability monitoring
- patch and exception workflows

## Log4Shell Example

Log4Shell, CVE-2021-44228, affected Apache Log4j and showed why dependency inventory matters. Many organisations had to quickly determine which applications used affected versions, whether Log4j was direct or transitive, which systems were internet-facing, and who owned remediation.

This maps strongly to A06 because the risk came from a vulnerable component used across many applications and vendors.

## Why Inventory Matters

Without a reliable inventory, teams lose time answering basic questions during urgent vulnerability events:

- Which applications use the affected component?
- Is the dependency direct or transitive?
- Which systems are internet-facing?
- Who owns each application?
- Is there a patch, workaround, or compensating control?
- What evidence proves remediation is complete?

## Patch Management Workflow

1. Identify affected component and versions.
2. Map affected applications, owners, and environments.
3. Prioritise by exposure, exploitability, data sensitivity, and business criticality.
4. Test recommended upgrades or mitigations.
5. Deploy fixes through approved change processes.
6. Record evidence, exceptions, and residual risk.
7. Continue monitoring for new advisories or regression.

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
- Use approved package sources and dependency governance.

## Related Tools

- Snyk Open Source
- OWASP Dependency-Check
- GitHub Dependabot
- Mend
- Veracode SCA
- Trivy

## Interview Talking Points

- SCA focuses on dependency risk, including direct and transitive dependencies.
- SBOMs improve visibility, but they still need monitoring and ownership.
- Log4Shell is a strong example of why dependency inventory matters.
- Patch management should balance urgency, testing, business risk, and compensating controls.
- DevSecOps moves dependency visibility earlier into development and CI/CD.
- A06 is about knowing what software you run, where it runs, and how quickly you can respond.

## Disclaimer

This project is for educational and defensive security purposes only.
