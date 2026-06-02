# Secure Coding Examples

## Input Validation

Validate input against expected type, length, format, and business rules. Prefer allowlists for fields with known valid values.

```python
def is_valid_account_id(account_id):
    return account_id.isdigit() and 1 <= len(account_id) <= 12
```

## Parameterized Query

Use parameterized queries so user input is treated as data.

```python
def get_account(cursor, account_id):
    query = "SELECT id, name FROM accounts WHERE id = ?"
    return cursor.execute(query, (account_id,))
```

## Server-Side Authorization

Check that the authenticated user is allowed to access the requested object.

```python
def can_view_account(user, account):
    return user.role == "admin" or account.owner_id == user.id
```

## Safe Error Handling

Return simple user-facing errors while logging useful diagnostic detail securely.

```python
def public_error_response():
    return {"message": "Request could not be processed"}
```

## Dependency Management

Use SCA tools, dependency lock files, and regular update cycles to manage vulnerable components.

## Disclaimer

This project is for educational and defensive security purposes only.
