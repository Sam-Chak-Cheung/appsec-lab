# SolarWinds

## Overview

The SolarWinds incident is a major example of supply chain security risk involving trust in software build and update processes.

## OWASP Mapping

- A08 Software and Data Integrity Failures

## Why It Matters

Modern organisations depend on vendors, managed services, software updates, and build pipelines. A trusted update path can become a high-impact risk if integrity controls, monitoring, and vendor assurance are weak.

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

## Interview Talking Points

- Supply chain security is broader than dependency CVEs.
- Code signing supports integrity but is not a complete control by itself.
- Vendor risk management should connect to technical monitoring and incident response.
- Build pipeline compromise can affect downstream customers.

## Disclaimer

This project is for educational and defensive security purposes only.
