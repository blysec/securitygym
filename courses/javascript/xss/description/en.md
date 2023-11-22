## XSS Attack

XSS (Cross-Site Scripting) is a type of attack on a web application that involves injecting malicious code into the web application's response (which will be executed in the user's browser when they open this page).

### Protective Controls

There are two **main**, complementary approaches to protect against XSS:
* Correct handling of special characters (the most dangerous ones are ```<>&"'```). **It is advisable to enable "escaping by default" in the used templating engine.**
* Implementation of Content Security Policy.

### Task

This code is vulnerable to XSS attacks. Fix the vulnerability without changing the program's behavior.

### Additional References

* https://owasp.org/www-community/attacks/xss/
* https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html
