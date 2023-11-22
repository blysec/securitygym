## Cross-Site Request Forgery (CSRF) Attack

CSRF (Cross-Site Request Forgery) is a type of attack on website visitors that exploits weaknesses in the HTTP protocol. If a victim visits a site created by an attacker, a request is secretly sent from their behalf to another server (for example, to a payment system server), carrying out a malicious operation (such as transferring money to the attacker's account). For this attack to occur, the victim must be authenticated on the server to which the request is sent, and this request must not require any confirmation from the user that cannot be ignored or faked by the attacking script.

To prevent this attack, all requests for data state changes should be signed with a special token.

It is important to remember that internal services/administration panels (not directly accessible to the attacker) can also be susceptible to this attack, so it's important not to forget about their protection.

![Example of CSRF attack](../img/bank_csrf.png)

### Protective Measures

Signing the request with a special token.

To enable protection against CSRF attacks in Flask applications, connect the CSRFProtect extension.

```python
from flask_wtf.csrf import CSRFProtect

csrf = CSRFProtect(app)
```

To insert the token into the template, you can use the following code:

```html
<form method="post">
    <input type="hidden" name="csrf_token" value="{{ csrf_token() }}"/>
</form>
```

### Task

The fund transfer functionality in the provided code is vulnerable to a CSRF attack. Fix the vulnerability without changing the program's behavior.

### Additional References
* http://www.owasp.org/index.php/Cross-Site_Request_Forgery_%28CSRF%29