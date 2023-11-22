## Server-Side Template Injection (SSTI) Attack

Server-Side Template Injection (SSTI) is a type of attack on modern applications that becomes possible when untrusted data is inserted into a document template, which is then processed by a template engine. This attack often allows for the execution of arbitrary code on the server side.

### Protective Measures

* Prevent user data from being included in the template description.
* Avoid sequential processing by template engines, where a document processed by one template engine is passed to another.
* Use the template engine in an isolated environment, if available.

### Task

This code contains SSTI vulnerabilities. Find and fix the vulnerability without changing the program's behavior.

### Additional Information

* https://nvisium.com/blog/2015/12/07/injecting-flask.html
