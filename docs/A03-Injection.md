# A03 Injection

## Description

Injection occurs when untrusted input is interpreted as part of a command, query, expression, or instruction. Common examples include SQL injection, command injection, LDAP injection, and template injection.

## Why It Matters

Injection can lead to unauthorised data access, data modification, account compromise, service disruption, or remote code execution depending on the application and execution context.

From a security engineering perspective, injection risk is important because it often sits at the boundary between user input, business logic, databases, operating system commands, and downstream services.

## SQL Injection Example

An application builds a database query by directly concatenating user input. If the input is treated as part of the SQL statement, the database may process logic the developer did not intend.

## Safe Vulnerable-Code Example

```python
def find_user(cursor, username):
    query = "SELECT id, username FROM users WHERE username = '" + username + "'"
    return cursor.execute(query)
```

This example is unsafe because the application combines SQL structure and user-controlled data in the same string.

## Fixed Parameterized Query Example

```python
def find_user(cursor, username):
    query = "SELECT id, username FROM users WHERE username = ?"
    return cursor.execute(query, (username,))
```

This version uses a parameterized query so the database treats the username as data, not query structure.

## Why Prepared Statements Matter

Prepared statements separate query structure from user input. The database receives the SQL template and the input values as separate items, which reduces the chance that user input will change the intended query logic.

Prepared statements are important because:

- they are a primary control for SQL injection
- they are more reliable than manual string escaping
- they support consistent secure coding patterns across teams
- they are easier to review during code review and SAST triage

## Other Injection Types

- Command injection: untrusted input influences operating system commands.
- LDAP injection: untrusted input influences LDAP queries.
- Template injection: untrusted input is interpreted by a template engine.
- Query injection: untrusted input changes NoSQL, GraphQL, or search query logic.

## Detection Methods

- Code review
- SAST
- DAST
- Security testing
- Logging and monitoring

## Detection Tools

- Snyk Code
- Checkmarx
- Veracode
- GitHub CodeQL
- OWASP ZAP
- SonarQube

## Prevention

- Use parameterized queries for database access.
- Avoid building shell commands from user input.
- Apply input validation based on expected data type and format.
- Apply output encoding in the correct context.
- Use least privilege for database, service, and operating system accounts.
- Monitor unusual query, error, and command execution patterns.
- Treat user input, API input, file content, and third-party data as untrusted.

## Related Tools

- Snyk Code
- Checkmarx
- Veracode
- GitHub CodeQL
- SonarQube
- OWASP ZAP

## Interview Talking Points

- Injection happens when data crosses into an interpreter as executable logic.
- Prepared statements are one of the most important controls for SQL injection.
- Input validation is useful, but it should not replace safe query construction.
- Least privilege reduces blast radius if an injection defect exists.
- SAST can identify risky code patterns, while DAST can validate behaviour in a running application.
- Command injection risk increases when applications call operating system commands or scripts.

## Disclaimer

This project is for educational and defensive security purposes only.
