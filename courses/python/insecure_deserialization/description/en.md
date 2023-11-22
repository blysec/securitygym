## Insecure Deserialization

Deserialization of untrusted data can lead to very serious consequences, such as remote code execution or denial of service. This statement is true for both object deserialization and data formats like JSON, AMF, YAML, XML.

### Protective Controls

* Do not deserialize data from untrusted sources.
* Use deserialization from trusted sources only where it is not possible to avoid it.
* Use JSON or Protobuf as a structure for data transfer.
* Ensure that you use a library/component/service that does not deserialize untrusted data. For this, you can use CVE search engines (https://cve.mitre.org/ or https://vulners.com).
* A good practice is to use a whitelisting mechanism, if such a mechanism is present in the library you are using.
* When deserializing Yaml files with the PyYAML library, use ```yaml.safe_load()```.

### Task

This code unsafely deserializes YAML files received from the user. Find and fix the vulnerability without changing the program's behavior.

### Additional References

* https://owasp.org/www-project-top-ten/2017/A8_2017-Insecure_Deserialization
* https://portswigger.net/web-security/deserialization
* https://www.kevinlondon.com/2015/08/15/dangerous-python-functions-pt2.html
* https://blog.nelhage.com/2011/03/exploiting-pickle/
* https://xerosecurity.com/wordpress/exploiting-python-deserialization-vulnerabilities/
