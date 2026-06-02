# Cloud Application Security

Cloud Application Security focuses on how application risk changes when software runs on cloud platforms, managed services, containers, serverless functions, identity systems, APIs, and internet-exposed infrastructure.

This section connects application weaknesses to cloud blast radius, identity design, data exposure, network paths, and runtime visibility.

The important shift is that application security and cloud security are tightly connected. A secure codebase can still create serious risk if it is deployed with public storage, excessive IAM permissions, missing logging, weak network controls, or exposed management interfaces.

## Key Risk Areas

| Area | Security Concern | Practical Controls |
| --- | --- | --- |
| Identity and access | overly broad IAM, weak service account design | least privilege, scoped roles, workload identities, regular access review |
| Data protection | public storage, weak encryption, poor key handling | encryption, private access, secrets management, data classification |
| Network exposure | unintended internet-facing services | segmentation, private endpoints, ingress review, egress control |
| Configuration | unsafe defaults and drift | IaC scanning, policy-as-code, cloud posture review |
| Logging and monitoring | poor visibility during incidents | centralised logs, alerting, audit trails, retention standards |
| Runtime security | vulnerable images and workloads | container scanning, patching, runtime monitoring |

## AppSec and Cloud Connection

Cloud controls often reduce the blast radius of application defects. For example:

- strong egress control can limit SSRF impact
- least privilege can reduce damage from credential exposure
- private storage can prevent data exposure after an access control mistake
- centralised logging can support investigation after suspicious application behaviour
- IaC scanning can catch misconfiguration before deployment

## Practical Review Questions

- What identities can the application use, and what can they access?
- Which data stores are reachable from the application?
- Which services are internet-facing?
- Are secrets stored in a managed secrets platform rather than source code or environment sprawl?
- Are logs sufficient to investigate authorization failures, unusual data access, and deployment changes?
- Does CI/CD scan application code, dependencies, containers, and infrastructure templates?

## Sample Cloud Application Review

Scenario: a customer API runs in containers, stores data in managed cloud storage and a database, and deploys through GitHub Actions.

| Review Area | Security Question | Practical Control | Evidence |
| --- | --- | --- | --- |
| Identity | Does the workload identity have only the permissions it needs? | scoped role for database and storage access | IAM policy review |
| Storage | Can sensitive data be accessed publicly or cross-tenant? | private storage, encryption, object-level access review | storage policy and access logs |
| Secrets | Are credentials stored outside code and pipeline logs? | managed secrets service and rotation process | secret inventory and rotation record |
| Network | Can the application reach internal services unnecessarily? | egress filtering and private endpoints | network rules and architecture review |
| Logging | Can security events be investigated after deployment? | central logs for auth, data access, deployments, and denied actions | log retention and alert configuration |
| CI/CD | Are code, dependencies, containers, and IaC reviewed before release? | SAST, SCA, secrets, container, and IaC checks | pipeline run and approval record |

## Practical Summary

Cloud Application Security is about securing the full environment where software operates. It connects secure coding with identity, data protection, network design, deployment automation, logging, and runtime visibility. In practice, this means AppSec engineers need to understand both application behaviour and the cloud controls that shape exposure and blast radius.
