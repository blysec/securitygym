## Vulnerabilities "Cross-Origin Resource Sharing (CORS)"

Cross-Origin Resource Sharing (CORS) is a mechanism for exchanging data between origins. Incorrect CORS configuration allows an attacker to obtain user data.

### Protective Measures

* Check the request source Origin against a whitelist.

### Task

This code contains a vulnerability in the implementation of CORS interaction. Find and fix the vulnerability without changing the program's behavior, so that interaction with the application is only possible from the hosts service.yandex.ru and yandex.ru.

### Additional Information

* https://www.w3.org/TR/cors/
