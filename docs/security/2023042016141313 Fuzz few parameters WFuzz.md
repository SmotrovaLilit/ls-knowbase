---
tags:
- wfuzz
- fuzzFewParameters
---

# Fuzz few parameters WFuzz

Use FUZ2Z, FUZ3Z...
``` bash
wfuzz -c -z file,/usr/share/list.txt --hc 404 http://offsecwp:80/FUZZ?fpv=FUZ2Z
```