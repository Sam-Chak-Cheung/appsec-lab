# A10 Server-Side Request Forgery

## Description

Server-Side Request Forgery occurs when an application can be influenced to make server-side requests to unintended destinations.

## Why It Matters

SSRF can expose internal services, metadata endpoints, or network paths that are not directly reachable by external users. In cloud environments, metadata service access can create serious credential and infrastructure risk.

## Example Scenario

An application accepts a user-supplied URL to fetch a document preview. Without strict validation and egress controls, the application may request internal cloud metadata or private network services.

## Detection Methods

- Code review
- SAST
- DAST
- Security testing
- Logging and monitoring
- Cloud network review

## Prevention

- Use allowlists for approved destination domains and schemes.
- Validate URLs and resolve final destinations safely.
- Block access to cloud metadata services unless explicitly required.
- Apply network egress control and segmentation.
- Avoid using user-controlled URLs for server-side requests where possible.
- Log outbound request destinations from sensitive services.

## Related Tools

- Snyk
- Checkmarx
- Veracode
- SonarQube
- OWASP ZAP
- Dependency-Check

## Interview Talking Points

- SSRF is especially important in cloud environments because of metadata service risk.
- URL validation alone is usually not enough; egress control and allowlisting are important.
- Segmentation limits what an application server can reach.
- Logging outbound requests helps detect unusual behaviour.
- Secure design should question whether server-side URL fetching is required at all.

## Disclaimer

This project is for educational and defensive security purposes only.
