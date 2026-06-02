# Log4Shell

## Overview

Log4Shell refers to CVE-2021-44228, a critical vulnerability affecting Apache Log4j.

## OWASP Mapping

- A06 Vulnerable and Outdated Components

## Why It Matters

Log4Shell demonstrated how a widely used dependency can create urgent exposure across many applications, vendors, and business services.

## Impact

The vulnerability created remote code execution risk in affected versions of Apache Log4j under certain conditions.

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

## Interview Talking Points

- Log4Shell is a strong example of why SCA and dependency inventory matter.
- The business challenge was visibility, prioritisation, and rapid coordinated remediation.
- SBOMs can help, but they must be paired with monitoring and response processes.

## Disclaimer

This project is for educational and defensive security purposes only.
