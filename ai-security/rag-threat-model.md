# RAG Threat Model

## Scenario

An internal assistant uses Retrieval-Augmented Generation to answer employee questions from HR, finance, policy, and engineering documents. The assistant can retrieve internal documents, summarise policy, draft responses, and create support tickets. It does not directly update employee records without human approval.

## Assets

| Asset | Security Concern |
| --- | --- |
| HR documents | privacy, employment data, regional access rules |
| Finance documents | sensitive business data, invoice and budget exposure |
| Engineering documents | architecture details, secrets references, vulnerability context |
| User identity and role data | authorization accuracy |
| Retrieved context | data leakage through prompts or logs |
| Model output | inaccurate, unsafe, or over-authoritative responses |
| Tool calls | unintended business actions |

## Trust Boundaries

```text
User
-> Application UI
-> Authorization service
-> Retrieval service
-> Vector database / document index
-> Model gateway
-> Tool execution layer
-> Human approval workflow
```

Key trust boundaries:

- user input enters the system as untrusted content
- retrieved documents may contain untrusted or outdated instructions
- the model output is not automatically trusted
- tool calls require scoped permissions and approval rules
- logs must not become a secondary sensitive data store

## Threat Scenarios

| Scenario | Risk | Control |
| --- | --- | --- |
| user asks the assistant to reveal another department's HR data | unauthorized data exposure | enforce authorization before retrieval |
| malicious document contains instructions to ignore policy | prompt injection through retrieved content | separate system instructions from retrieved content and constrain tool use |
| assistant retrieves documents outside the user's region | privacy and compliance breach | apply region, role, and tenant filters before retrieval |
| model summarises sensitive content into logs | secondary data leakage | redact logs and limit prompt retention |
| assistant creates a ticket with sensitive data in the wrong queue | data mishandling | classify output and require approval for sensitive workflows |
| model recommends an action based on outdated policy | operational error | include source dates, confidence handling, and review paths |

## Control Design

### Retrieval Controls

- enforce authorization before document retrieval
- filter by user role, business unit, region, tenant, and document sensitivity
- prevent retrieval from unapproved repositories
- keep document ownership and classification metadata current

### Prompt and Model Controls

- keep system instructions separate from retrieved data
- treat retrieved content as data, not authority
- limit model access to approved tools
- validate output before high-impact use
- require source references for policy or procedural answers

### Tool Use Controls

- allowlist tools by role and use case
- scope tool permissions to the user's authorization context
- require human approval for high-impact actions
- log tool requests, approvals, denials, and outcomes

### Logging and Monitoring

- log retrieval decisions without storing unnecessary sensitive text
- monitor denied retrieval attempts and unusual access patterns
- record prompt, retrieval, and tool-call metadata for investigation
- define retention rules for AI interaction logs

## Human Approval Model

| Action | Approval Requirement |
| --- | --- |
| answer general policy question | no approval required |
| summarise documents the user is authorized to view | no approval required |
| draft external communication | user review required |
| create support ticket containing sensitive data | user confirmation required |
| update employee, financial, or customer record | human approval required |
| trigger system or workflow action | approval based on impact and reversibility |

## Evidence Required

- documented AI feature scope and approved data sources
- retrieval authorization tests
- role and region access test cases
- prompt injection abuse cases
- logging and retention configuration
- tool approval workflow evidence
- incident response path for AI misuse or data leakage

## Practical Summary

RAG security is primarily an authorization, data governance, and workflow control problem. Prompt injection matters, but enterprise risk often comes from retrieving the wrong data, trusting model output too much, or allowing model-driven actions without sufficient approval and logging.
