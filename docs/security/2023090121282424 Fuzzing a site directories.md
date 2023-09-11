---
tags:
- findDirectories
---

# Fuzzing a site directories

## If site return 404 if page does not exist
```bash
wfuzz -w /usr/share/seclists/Discovery/Web-Content/combined_directories.txt --hc 404,301  http://app/FUZZ.php
```

```
gobuster dir -u http://app -w /usr/share/wordlists/dirb/common.txt -b 301,404
```
## If site returns not found pages as 200 status

1. We can exclude not existing pages by filtering response body content:
 **--hs**
```bash
wfuzz -w /usr/share/seclists/Discovery/Web-Content/combined_directories.txt --hc 404 --hs "Not found"  http://app/FUZZ.php
```

2. We can exclude not existing pages by filtering response content-length
It works only if not found pages has the same content length
**--exclude-length 104**
```bash
gobuster dir -u http://app -w /usr/share/wordlists/dirb/common.txt -b 301,404 --exclude-length 104
```

**--hh 104**
```bash
wfuzz -w /usr/share/seclists/Discovery/Web-Content/combined_directories.txt --hc 404 --hh 104  http://app/FUZZ.php

```

```
gobuster dir -u http://167.172.61.89:32335 -w /usr/share/wordlists/dirb/common.txt -b 301,404
```