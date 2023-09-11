---
tags:
- xss
---

# Reflected Server XSS

Reflected server XSS - is a XSS attack when an attacker sends payload from victim request to the server and server append this payload to the response. 
- XSS in GET request parameters. An attacker create link on original site with XSS payload in url and a victim open it. 
- XSS in POST. An attacker need to create own site like original and when a vicim open it the post request will be sent to the original web site. 
Example of payload in GET parameters:
```
http://example.com?s=<script> alert(0); </script>
```

## How attacker sends payload tho the victim request 
 1. Through an  email, chat message or link to another site
## References
1. web200.Cross-Site Scripting Introduction and Discovery.Cross-Site Scripting - Discovery.Reflected Server XSS
2. 