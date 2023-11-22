## XML External Entity (XXE) Attack

**XML External Entity (XXE)** is a type of attack on applications that process XML. The attack is possible when an XML parser is configured to support external XML entities.
XXE can lead to the disclosure of confidential information, denial of service, SSRF (server-side request forgery), and other security problems.

Before using an XML parser for untrusted data:
- check the possibility of connecting ```DTD schemas``` or ```External Entities```;
- if this feature is enabled, **explicitly disable it**;
- pay attention to similar risks when working with documents in rich formats (DOCX, XLSX, PPTX, and others).

The table below shows attacks to which XML parsers are vulnerable in the default configuration.

| Parser     | DOS      | XXE     | XXE Parameter | URL Invocation | XInclude | XSLT |
|------------|----------|---------|---------------|----------------|----------|------|
| Etree      | **yes*** | no      | no            | no             | no       | no   |
| xml.sax    | **yes*** | **yes** | no            | **yes**        | no       | no   |
| pulldom    | **yes*** | **yes** | no            | **yes**        | no       | no   |
| lxml       | **yes**  | **yes** | no            | no             | no       | no   |
| defusedxml | no       | no      | no            | no             | no       | no   |
| minidom    | **yes*** | no      | no            | no             | no       | no   |
\* no available protection options

## Protective Controls

* It is recommended to use [defusedxml](https://blog.python.org/2013/02/announcing-defusedxml-fixes-for-xml.html)
* For lxml, it is necessary to disable the processing of XML entities into text values (_resolve_entities=False_), prohibit network access (_no_network=True_), and set a custom DTD resolver:
    ```python
    from lxml import etree

    class FakeDTDResolver(etree.Resolver):
        def resolve(self, url, id, context):
            return this.resolve_string('', context)

    parser = etree.XMLParser(remove_blank_text=True, resolve_entities=False, no_network=True)
    parser.resolvers.add( FakeDTDResolver() )
    xml = etree.fromstring(data, parser)
    ```

### Task

The provided code, which processes invoices in XML format, is vulnerable to an XXE attack. Fix the vulnerability without changing the program's behavior.

### Additional References

* https://www.owasp.org/index.php/XML_External_Entity_%28XXE%29_Processing
* https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html
