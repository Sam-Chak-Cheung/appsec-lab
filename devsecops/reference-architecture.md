# DevSecOps Reference Architecture

## Objective

This reference architecture shows how security controls can be integrated into a software delivery pipeline without turning security into a disconnected final approval step.

The design goal is to provide early feedback to engineers, preserve release velocity for low-risk changes, and create clear evidence for material risk decisions.

## Pipeline Flow

```text
Developer workstation
-> Pull request
-> CI security checks
-> Build and package
-> Container and IaC review
-> Risk-based release decision
-> Deployment
-> Runtime monitoring
```

## Control Placement

| Stage | Control | Purpose | Typical Outcome |
| --- | --- | --- | --- |
| Developer workstation | local linting and optional secrets checks | reduce preventable issues before commit | warn |
| Pull request | SAST and CodeQL | identify risky code paths early | warn or block |
| Pull request | SCA | identify vulnerable direct and transitive dependencies | warn or block based on severity and exposure |
| Pull request | secrets scanning | prevent credential exposure | block |
| Build | dependency lock and artifact integrity | ensure repeatable build inputs | block on integrity failure |
| Package | container scanning | identify vulnerable image packages and unsafe base images | warn or block |
| Infrastructure | IaC scanning | detect public exposure, weak encryption, and broad IAM | warn or block |
| Release | AppSec review for material findings | decide whether to remediate, compensate, or accept risk | approve, reject, or exception |
| Runtime | logs and vulnerability monitoring | detect suspicious behaviour and new exposure | alert and investigate |

## Suggested Blocking Rules

| Finding Type | Default Action | Rationale |
| --- | --- | --- |
| confirmed hardcoded secret | block | credential exposure can create immediate compromise risk |
| critical vulnerable dependency with reachable exposure | block | material risk to production systems |
| unauthenticated access control regression | block | direct customer or tenant impact |
| public cloud storage containing sensitive data | block | high likelihood of data exposure |
| medium SAST finding with unclear reachability | warn and triage | context is required before blocking |
| low severity dependency finding | warn | track through normal remediation cycle |

## Exception Handling

Security exceptions should be visible, time-bound, and owned. An exception should record:

- affected application or service
- finding and severity
- business justification
- compensating controls
- remediation owner
- due date
- approval record
- monitoring requirement

An exception is not a permanent bypass. It is a documented risk decision with a defined review point.

## Evidence Model

Release evidence should link:

- commit SHA
- pull request number
- build identifier
- SAST results
- SCA results
- secrets scan result
- container and IaC scan result
- approval or exception record
- deployment environment
- rollback plan

## Operating Model

| Role | Responsibility |
| --- | --- |
| Developers | fix code, dependency, and configuration issues in owned services |
| AppSec | define policy, triage material findings, advise on remediation |
| Platform team | maintain CI/CD controls and pipeline templates |
| Cloud security | review IAM, networking, storage, and logging controls |
| Service owner | accept residual risk and prioritise remediation |

## Practical Summary

A good DevSecOps pipeline does not simply run more tools. It makes risk visible at the point where engineers can act, defines which findings block release, captures evidence, and keeps exception decisions accountable.
