# Research algorithm

## Find ports
```bash
nmap app
```

## Find os
```bash
sudo nmap -O -Pn app
```

## Research site directory
```bash
gobuster dir -u http://app -w /usr/share/wordlists/dirb/common.txt
```

```bash
wfuzz -w /usr/share/seclists/Discovery/Web-Content/combined_directories.txt --hc 404 http://app/FUZZ.php
```

## Alternatives
- Directory Traversal [[2023051318534545 Directory Traversal or Path Traversal]]
- Check IDOR [[202304131820011 Insecure Direct Object Referencing]]
- Check SQL Injection [[2023050422584646 SQL Injection]]
- Check XML [[2023051417011010 XML]]
- Check templates  [[2023051512325757  SSTI]]
- Check XSS [[2023042015372828 XSS]]
- Check CMD Injection [[2023051521093838 Command Injection]]
- Check SSRF [[202305201524033 SSRF Server-side Request Forgery]]
- 