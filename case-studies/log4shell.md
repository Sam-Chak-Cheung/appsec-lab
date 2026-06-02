# Log4Shell

## Overview

Log4Shell refers to CVE-2021-44228, a critical vulnerability affecting Apache Log4j.

## OWASP Mapping

- A06 Vulnerable and Outdated Components

## Why It Matters

Log4Shell demonstrated how a widely used dependency can create urgent exposure across many applications, vendors, and business services.

## Impact

The vulnerability created remote code execution risk in affected versions of Apache Log4j under certain conditions.

From a business perspective, the difficult part was not only applying a patch. Organisations first had to determine which applications used Log4j, whether it was present as a direct or transitive dependency, which systems were internet-facing, which vendors were affected, and which services were business-critical.

## Business Impact

- emergency vulnerability response across the application estate
- customer trust and regulatory concern for exposed services
- operational pressure on engineering and platform teams
- increased risk where dependency ownership was unclear
- difficulty proving remediation without reliable inventory and evidence

## Detection

- SCA
- Dependency inventory
- SBOM review
- Asset inventory
- Vendor notifications
- Runtime monitoring

## Remediation

- Upgrade affected versions.
- Identify direct and transitive dependencies.
- Maintain an asset and dependency inventory.
- Use continuous dependency scanning.
- Track exceptions and compensating controls.

## Recommended Control Model

| Control | Purpose |
| --- | --- |
| SCA in pull requests and CI/CD | identify vulnerable dependencies before release |
| continuous dependency monitoring | detect new advisories after deployment |
| SBOM for critical applications | improve component visibility during urgent events |
| application ownership register | route remediation to the right team quickly |
| exposure-based prioritisation | focus first on internet-facing and business-critical services |
| exception workflow | document compensating controls and due dates where patching is delayed |

## Evidence a Security Team Should Collect

- affected applications and owners
- dependency path showing direct or transitive use
- affected and remediated versions
- deployment records for patched builds
- compensating controls for delayed remediation
- monitoring or detection evidence for exposed services

## Practical Talking Points

- Log4Shell is a strong example of why SCA and dependency inventory matter.
- The business challenge was visibility, prioritisation, and rapid coordinated remediation.
- SBOMs can help, but they must be paired with monitoring and response processes.

## Disclaimer

This project is for educational and defensive security purposes only.
