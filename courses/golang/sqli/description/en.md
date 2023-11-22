## SQL Injection Attack

An "Injection" type attack allows an attacker to insert arbitrary code through an application into another system (for example, when executing external programs through a shell or accessing databases through SQL).

SQL injections occur when a program dynamically forms database queries, including data obtained from untrusted sources.

### Protective Measures

No user input should enter SQL queries in raw form, preferably use ORM, if custom queries are necessary for optimization — only strictly cast to the required type, using prepared statements:
```go
customerName := r.URL.Query().Get("name")
db.Exec("UPDATE creditcards SET name=? WHERE customerId=?", customerName, 233, 90)
```

### Task

This code contains a SQL injection vulnerability. Find and fix the vulnerability without changing the program's behavior.

### Additional References

* https://owasp.org/www-community/attacks/SQL_Injection
* https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html
* https://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet.html
* https://portswigger.net/web-security/sql-injection