## Open Redirection Attack

This attack is possible when a web application has a script that, without any restrictions, redirects to a user-specified URL: ```https://site.com/redirect?url=http://evil.com/```. From the attacker's perspective, this feature can be used to stealthily "lead" the victim to a phishing site. Try to avoid such implementations.

### Protective Controls

There should be no possibility to specify which URL to redirect to. It is necessary to validate the parameter against a list of allowed paths.

### Task

This code is vulnerable to an "Open Redirection" attack. Find and fix the vulnerability so that the application does not redirect to external resources, but only redirects within the service.

### Additional References

* https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html
