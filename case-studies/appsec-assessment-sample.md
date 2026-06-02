# Application Security Assessment Sample

## Scenario

A customer-facing account management application allows users to view profile details, invoices, support cases, and payment history. The application is deployed to a cloud environment, uses a REST API backend, stores customer records in a managed database, and integrates with a third-party payment provider.

This sample assessment focuses on defensive review, business impact, and practical remediation planning.

## Executive Summary

The application has a moderate-to-high security risk profile because it handles sensitive customer and billing data. The most material risk is inconsistent authorization enforcement across object-level API requests. Dependency and secrets controls are partially implemented, but release evidence is not yet mature enough to support reliable governance.

The recommended priority is to strengthen server-side authorization, improve dependency visibility, formalise CI/CD security gates, and define ownership for remediation and exceptions.

## Scope

| Area | Included |
| --- | --- |
| Application | customer account portal and API |
| Data | profile data, invoice metadata, support case references, payment tokens |
| SDLC | pull request review, CI/CD scanning, release approval |
| Cloud controls | identity, logging, secrets handling, network exposure |
| Third parties | payment provider integration and dependency inventory |

## Key Findings

| Finding | Risk | Business Impact | Priority |
| --- | --- | --- | --- |
| Inconsistent object-level authorization | user may access records outside their account scope | customer data exposure, privacy impact, trust loss | High |
| Dependency visibility is incomplete | vulnerable transitive packages may remain unknown | delayed response to urgent CVEs | Medium |
| Secrets scanning is not enforced before merge | credentials may enter source control | account compromise, emergency key rotation | Medium |
| CI/CD security results are not tied to release evidence | risk decisions are difficult to audit | weak governance and unclear accountability | Medium |
| Cloud service permissions are broader than required | application compromise could reach unnecessary resources | larger blast radius during incident | Medium |

## Finding Detail: Object-Level Authorization

### Risk

The API validates that a user is authenticated, but authorization checks are not consistently applied to every requested object. This can lead to horizontal access control failure where one authenticated customer can access another customer's data.

### Business Impact

This risk affects confidentiality, privacy obligations, customer trust, and incident response cost. If invoice or support case data is exposed, the organisation may need to notify affected customers, investigate access logs, and review regulatory reporting obligations.

### Likely Detection Methods

- code review of controller and service-layer authorization logic
- negative API tests using users from different accounts
- DAST with authenticated test roles
- log review for unusual cross-account object access
- SAST findings that highlight authorization-sensitive code paths

### Recommended Controls

- enforce server-side authorization for every sensitive object request
- centralise account, tenant, role, and ownership checks in reusable policy logic
- deny access by default when ownership cannot be proven
- add automated tests for same-account and cross-account access attempts
- log denied authorization decisions with user, object type, and account context

### Evidence Required

- updated authorization policy or service-layer control
- test cases covering positive and negative access scenarios
- pull request review record for authorization-sensitive changes
- logs showing denied cross-account access attempts in test
- release record linking remediation to deployment

## Remediation Plan

| Priority | Action | Owner | Evidence |
| --- | --- | --- | --- |
| High | implement central object authorization checks | application team | merged PR, test results |
| High | add negative authorization tests for customer data APIs | application team | CI test output |
| Medium | enforce SCA and secrets scanning in pull requests | platform team | pipeline configuration |
| Medium | document dependency ownership and exception process | AppSec and engineering leads | dependency register |
| Medium | review cloud IAM permissions for the application identity | cloud platform team | access review record |

## Risk Acceptance Criteria

Risk acceptance should be limited to cases where:

- the affected system and data are clearly identified
- compensating controls are documented
- a business owner accepts residual risk
- remediation has an assigned owner and due date
- monitoring is in place for suspicious activity

## Practical Summary

This assessment demonstrates the core AppSec workflow: identify the risk, explain the business impact, recommend controls, assign ownership, and define evidence. The most important security decision is not only whether a finding exists, but how quickly the team can reduce material risk and prove the control is working.
