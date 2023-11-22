## Insecure Direct Object Reference

Insecure Direct Object Reference (IDOR) occurs when applications explicitly use the name or key of an object in generating web pages, without verifying the user's rights to request the object.

For exploitation, an attacker only needs to change the value of the parameter referring to the object, to one that refers to an object that the user does not have access to.

### Protective Measures

Verify for each request that the user is authorized to access the object.

### Task

This code contains an IDOR vulnerability in one of the methods. Find and fix the vulnerability without changing the program's behavior.
All payments are stored in the payment table:
```sql
CREATE TABLE payment (
    id INTEGER PRIMARY KEY AUTOINCREMENT, -- payment identifier
    user_id INTEGER NOT NULL, -- identifier of the user who made the payment
    amount DECIMAL(10,2) NOT NULL, -- amount of funds transferred
    description TEXT, -- comment on the payment
    FOREIGN KEY (user_id) REFERENCES user (id)
);
```

### Additional References

* https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet.html
* https://portswigger.net/web-security/access-control/idor