## Missing Function Level Access Control

Missing Function Level Access Control (MFLAC) occurs when there is insufficient verification of access rights in request handlers.

An attacker only needs to access a direct URL to gain access to privileged functionality.

### Protective Measures

Verify for each request that the user is authorized to access the requested application functionality.

### Task

This code does not check whether the user has admin privileges (`is_admin = True`) when accessing `/users_list`. Find and fix the vulnerability without changing the program's behavior.
_Hint: Information about the current user is stored in the application context. You can check if the user is an administrator like this: `if flask.g.user["is_admin"] == True`_

### Additional Information

* https://blog.detectify.com/2016/07/13/owasp-top-10-missing-function-level-access-control-7/
