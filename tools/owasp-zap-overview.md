# OWASP ZAP Overview

## Where OWASP ZAP Fits

OWASP ZAP is a Dynamic Application Security Testing tool used to assess running web applications. It can support baseline scans, authenticated testing, proxy-based review, and automated checks in CI/CD.

ZAP is useful because it observes application behaviour from the outside, which complements source code and dependency analysis.

## Practical Use Cases

- baseline scan of a deployed test environment
- detection of missing security headers and common web issues
- authenticated browsing and manual security review support
- CI/CD smoke checks for web applications
- validation that fixes changed runtime behaviour

## Engineering Considerations

DAST only sees reachable behaviour in the running application. It may miss issues hidden behind untested roles, workflows, feature flags, or API paths. It should be paired with code review, SAST, SCA, and threat modelling.

## Practical Summary

OWASP ZAP is a practical DAST tool for testing running web applications. It helps validate observable behaviour, but it is strongest when combined with secure design review and source-level analysis.
