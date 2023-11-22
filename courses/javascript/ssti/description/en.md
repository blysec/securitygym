## Server-Side Template Injection (SSTI) Attack

Server-Side Template Injection (SSTI) is a type of attack on modern applications that becomes possible when untrusted data is inserted into a document template, which is subsequently processed by a template engine. This attack often allows the execution of arbitrary code on the server side.

### Protective Controls

* Load templates from files and never modify them during application execution;
* It is recommended to use the simplest template engines that do not use dynamic code execution, but implement full parsing of the template and substitution of variables. One such template engine is [Mustache](https://mustache.github.io/).

### Task

This code contains SSTI vulnerabilities. Find and fix the vulnerability without changing the program's behavior.

### Additional References

* https://portswigger.net/research/server-side-template-injection
