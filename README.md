# F5_waf_custom_blocking_page
iRule to intercept and customize F5 WAF (aka ASM) blocking page,  Use this irule for testing and as an example only.

iRule returns the violation information in HTML format when the WAF detects an attack.  It is a good example of how to customize the blocking page.  Also useful when testing your WAF policy.  It is not good for use in production.

Test it like this:
https://myhost/?a=<script>

If the uri is "/test/headers", the irule will reflect back the HTTP request as well as the Source IP address of the client.  The iRule will also skip further processig by the F5 Big-IP.  e.g no WAF inspection when this occurs.

Test it like this:
https://myhost/test/headers
