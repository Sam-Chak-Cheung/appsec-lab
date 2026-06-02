# Snyk Overview

## Where Snyk Fits in AppSec

Snyk is a developer-first security platform used to identify and remediate security issues earlier in the software delivery lifecycle. It is commonly used by AppSec, DevSecOps, platform, and development teams to bring security feedback into source control, pull requests, CI/CD, and release workflows.

Snyk is most useful when the goal is to help engineers understand what is affected, why it matters, and how to fix it without waiting for a late-stage security review.

## Snyk Open Source

Snyk Open Source provides Software Composition Analysis for open source dependencies.

It helps identify:

- vulnerable direct dependencies
- vulnerable transitive dependencies
- CVEs and security advisories
- recommended upgrade paths
- dependency risk across the application estate

This is especially relevant to OWASP A06 Vulnerable and Outdated Components.

## Snyk Code

Snyk Code provides Static Application Security Testing for source code.

It helps identify risky coding patterns such as:

- injection risks
- insecure data handling
- weak validation patterns
- unsafe API usage
- security-sensitive logic requiring review

SAST findings still require triage and context. A tool result is a starting point for engineering review, not automatic proof of exploitable risk.

## Snyk Container

Snyk Container reviews container images for vulnerable packages and base image risk.

It is useful for:

- identifying vulnerable operating system packages
- reviewing base image exposure
- recommending safer image versions
- supporting container hardening discussions before deployment

## Snyk IaC

Snyk IaC reviews Infrastructure as Code for insecure cloud and platform configuration.

It can help identify:

- overly permissive IAM
- public cloud storage exposure
- missing encryption
- network exposure
- logging and monitoring gaps

## CI/CD Integration

Snyk can be integrated into GitHub Actions and other CI/CD systems to scan pull requests, builds, containers, and infrastructure templates.

Practical pipeline use:

- scan pull requests before merge
- alert developers to vulnerable dependencies
- block or warn based on risk policy
- record evidence for remediation and governance
- monitor projects continuously after release

## Developer Workflow

The strongest use of Snyk is not only producing security reports. It is giving developers timely, understandable, and actionable feedback.

Good workflow design includes:

- clear severity thresholds
- ownership for remediation
- exception process for accepted risk
- links to upgrade guidance
- integration with tickets or pull requests
- AppSec review for material or uncertain findings

## Typical Enterprise Use Case

An enterprise AppSec team may use Snyk to monitor application dependencies, scan pull requests, identify vulnerable container images, and review IaC templates. Security teams can then prioritise remediation based on exposure, business criticality, exploitability, and available fixes.

Snyk often complements tools such as Checkmarx, Veracode, SonarQube, CodeQL, Trivy, and OWASP Dependency-Check.

## Disclaimer

This project is for educational and defensive security purposes only.
