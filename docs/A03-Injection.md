# A03 Injection

## Description

Injection occurs when untrusted input is interpreted as part of a command, query, expression, or instruction. Common examples include SQL injection, command injection, LDAP injection, and template injection.

## Why It Matters

Injection can lead to unauthorised data access, data modification, account compromise, service disruption, or remote code execution depending on the application and execution context.

## Example Scenario

An application builds a database query by directly concatenating user input. If the input is treated as part of the query structure, the application may return records the user should not see.

## Safe Vulnerable-Code Example

```python
def find_user(cursor, username):
    query = "SELECT id, username FROM users WHERE username = '" + username + "'"
    return cursor.execute(query)
```

This example is unsafe because user input is inserted directly into the SQL statement.

## Fixed-Code Example

```python
def find_user(cursor, username):
    query = "SELECT id, username FROM users WHERE username = ?"
    return cursor.execute(query, (username,))
```

This version uses a parameterized query so the database treats the username as data, not query structure.

## Detection Methods

- Code review
- SAST
- DAST
- Security testing
- Logging and monitoring

## Prevention

- Use parameterized queries for database access.
- Avoid building shell commands from user input.
- Apply input validation based on expected data type and format.
- Apply output encoding in the correct context.
- Use least privilege for database, service, and operating system accounts.
- Monitor unusual query, error, and command execution patterns.

## Related Tools

- Snyk
- Checkmarx
- Veracode
- SonarQube
- OWASP ZAP
- Dependency-Check

## Interview Talking Points

- Parameterized queries are a primary control for SQL injection.
- Input validation is helpful but should not replace safe query construction.
- Least privilege reduces blast radius if an injection defect exists.
- Command injection risk increases when applications call operating system commands.
- Injection detection should combine code scanning, testing, and runtime monitoring.

## Disclaimer

This project is for educational and defensive security purposes only.
