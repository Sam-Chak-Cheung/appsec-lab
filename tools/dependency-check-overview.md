# OWASP Dependency-Check Overview

## Where Dependency-Check Fits

OWASP Dependency-Check is a Software Composition Analysis tool that identifies publicly known vulnerabilities in project dependencies. It is commonly used in CI/CD pipelines and security review workflows.

It supports dependency visibility, especially for teams that need an open source option for identifying vulnerable components.

## Practical Use Cases

- identify vulnerable open source dependencies
- support OWASP A06 review
- run dependency checks in CI/CD
- produce evidence for dependency risk review
- complement other SCA tools and SBOM workflows

## Engineering Considerations

Dependency findings should be prioritised based on affected version, exploitability, reachability, application exposure, data sensitivity, and available fixes. Not every CVE has the same business impact.

## Practical Summary

OWASP Dependency-Check helps teams identify known vulnerable dependencies. It is useful for SCA and supply chain visibility, but remediation decisions still require context about exposure, exploitability, and application criticality.
