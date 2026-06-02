# AI Application Security

AI Application Security focuses on the risks introduced when applications use large language models, prompts, retrieval systems, autonomous actions, enterprise data, and AI-assisted decision making.

This section treats AI features as application systems with data access, authorization, logging, validation, and governance requirements.

The core security question is not only whether the model behaves correctly. It is whether the full application protects data, enforces permissions, validates outputs, limits unsafe actions, and keeps humans accountable for high-impact decisions.

## Key Risk Areas

| Area | Security Concern | Practical Controls |
| --- | --- | --- |
| Prompt injection | untrusted content changes model behaviour | isolate instructions from data, constrain tool use, validate outputs |
| RAG security | retrieval exposes data the user should not see | enforce authorization before retrieval, filter by tenant and role, log access |
| Data leakage | prompts or outputs expose sensitive information | data classification, redaction, retention controls, approved model usage |
| Tool use | model actions affect systems or records | allowlisted tools, scoped permissions, human approval for high-impact actions |
| Output trust | generated content is inaccurate or unsafe | verification, confidence handling, review workflows, clear ownership |
| Governance | unclear accountability for AI decisions | risk assessments, approval controls, monitoring, policy alignment |

## Enterprise AI Security Model

A secure AI-enabled application should define:

- who can use the feature
- what data the model can access
- which actions the model can request
- which actions require human approval
- how outputs are validated before business use
- how prompts, retrieval, tool calls, and decisions are logged
- how incidents, abuse, and model failures are reviewed

## Practical Scenario

An internal support assistant uses retrieval to answer employee questions from HR and finance documents. The main risk is not only prompt injection. The higher business risk is cross-department data exposure if retrieval is not filtered by user role, region, employment status, and document sensitivity.

Practical controls include role-aware retrieval, document classification, prompt and response logging, restricted tool use, and human approval before the assistant updates employee records or sends external messages.

See the [RAG threat model](rag-threat-model.md) for a practical control model.

## Practical Summary

AI security is an extension of Application Security. It introduces new trust boundaries between users, prompts, models, retrieval sources, tools, and business workflows. A strong security design treats the model as one component in a controlled system, with authorization, logging, validation, and human approval around it.
