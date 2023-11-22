## ClickJacking Attack

Clickjacking is a mechanism for deceiving internet users, where an attacker can gain access to a user's confidential information by luring them to an outwardly harmless page. The principle is based on the fact that an invisible layer is placed over the visible page, into which the attacker's desired page is loaded in an iframe. The control element (for example, a button or link) necessary for the desired action coincides with a visible link or button, which the user is expected to click. Various applications of this technology are possible - from subscribing to a resource in a social network to stealing sensitive information and making purchases in online stores at someone else's expense.

### Protective Measures

**_The current approach_** involves adding the ``X-Frame-Options: DENY`` or ``X-Frame-Options: SAMEORIGIN`` headers to all HTTP responses with layout.

In the Content Security Policy specification, a more convenient directive frame-ancestors has [appeared](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives#frame-ancestors), allowing to set a list of domains that are allowed to open the resource in frames. We **_recommend_** using CSP on your resources not only for protection against Clickjacking ;-)

If framing from various domains is necessary in the service, we recommend making protection based on postMessage. The document loaded in the iframe initially "pings" the main document, checks the host, and if it falls into the list of allowed, loads the main content.

An alternative is to set the `X-Frame-Options` header based on the value of the referrer. But it should be checked precisely by the algorithm: if there is a referrer and it equals one of the list, then we do not show `X-Frame-Options`. That is, by default, we block framing:
```nginx
if ($http_referer !~ "^https?://([^/]+\.)?website\.com/"){
    add_header X-Frame-Options SAMEORIGIN always;
}
```

### Task

This code is vulnerable to a Clickjacking attack. Add the X-Frame-Options header to protect against Clickjacking.

### Additional References

* https://owasp.org/www-community/attacks/Clickjacking
* https://learn.javascript.ru/clickjacking
