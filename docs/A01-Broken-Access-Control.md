# A01 Broken Access Control

## Description

Broken access control occurs when an application does not correctly enforce what a user, role, service, or tenant is allowed to access.

## Why It Matters

Access control failures can expose customer records, financial data, administration functions, or cross-tenant information. The impact is often both technical and business-critical because it affects confidentiality, integrity, trust, and regulatory obligations.

## Example Scenario

An authenticated user changes an account ID in a URL and can view another user's record because the server checks that the user is logged in but does not check whether the user owns the requested record. This is commonly described as IDOR.

## Detection Methods

- Code review
- SAST
- DAST
- Security testing
- Logging and monitoring

## Prevention

- Enforce server-side authorization for every sensitive request.
- Use RBAC or ABAC consistently.
- Validate tenant, user, object, and role relationships on the server.
- Apply least privilege to users, services, and administrators.
- Deny access by default and log important authorization decisions.

## Related Tools

- Snyk
- Checkmarx
- Veracode
- SonarQube
- OWASP ZAP
- Dependency-Check

## Practical Talking Points

- Authentication proves identity; authorization decides what that identity can access.
- IDOR is usually a server-side authorization design problem, not only an input validation issue.
- Horizontal privilege escalation means accessing another user's data at the same privilege level.
- Vertical privilege escalation means a lower-privileged user accesses administrator-level functionality.
- Good access control is enforced centrally and tested through both positive and negative cases.

## Disclaimer

This project is for educational and defensive security purposes only.
