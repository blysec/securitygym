## Insecure Direct Object Reference

Insecure Direct Object Reference (IDOR) occurs when applications explicitly use the name or key of an object when generating web pages, without verifying the user's rights to request the object.

For exploitation, an attacker only needs to change the value of the parameter referring to the object, to one that refers to an object that the user does not have access to.

### Protective Measures

Verify for each request that the user is authorized to access the object.

### Task

It's necessary to check access to the object not only for users. In this example, third-party services use a token in a custom header to access our service for uploading and viewing memes. One of the methods contains an IDOR, which should be fixed without changing the program's behavior.

### Additional References

* https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet.html
* https://portswigger.net/web-security/access-control/idor
