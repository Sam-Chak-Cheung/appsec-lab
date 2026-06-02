# SolarWinds

## Overview

The SolarWinds incident is a major example of supply chain security risk involving trust in software build and update processes.

## OWASP Mapping

- A08 Software and Data Integrity Failures

## Why It Matters

Modern organisations depend on vendors, managed services, software updates, and build pipelines. A trusted update path can become a high-impact risk if integrity controls, monitoring, and vendor assurance are weak.

The incident is useful for security engineering because it shows that supply chain security is not limited to vulnerable open source packages. Build systems, update channels, signed software, vendor access, and monitoring all become part of the trust model.

## Business Impact

- compromise risk through trusted software update mechanisms
- downstream exposure across customers and partners
- increased scrutiny of vendor assurance and third-party risk
- need for detection even when software appears legitimate
- incident response complexity across many environments

## Security Themes

- Supply chain security
- Build pipeline trust
- Code signing
- Vendor risk
- Monitoring
- Detection engineering
- Incident response

## Defensive Lessons

- Understand critical vendors and software dependencies.
- Review software update trust models.
- Protect build systems and deployment pipelines.
- Monitor unusual behaviour from trusted software.
- Include supply chain scenarios in incident response planning.

## Recommended Control Model

| Control | Purpose |
| --- | --- |
| build system hardening | reduce risk of tampering with source, build, or release processes |
| separation of duties | prevent a single identity or process from controlling all release steps |
| artifact signing and verification | improve integrity checks for released software |
| vendor criticality register | identify high-impact suppliers and software dependencies |
| runtime monitoring | detect unusual behaviour from trusted software |
| incident response playbooks | prepare for supplier compromise and update-channel abuse |

## Evidence a Security Team Should Collect

- list of critical vendor software and business owners
- update and patch management records
- build and release pipeline controls
- software integrity verification process
- monitoring coverage for privileged vendor tools
- third-party risk review outcomes

## Practical Talking Points

- Supply chain security is broader than dependency CVEs.
- Code signing supports integrity but is not a complete control by itself.
- Vendor risk management should connect to technical monitoring and incident response.
- Build pipeline compromise can affect downstream customers.

## Disclaimer

This project is for educational and defensive security purposes only.
