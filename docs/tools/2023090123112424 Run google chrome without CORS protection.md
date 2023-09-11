# Run google chrome without CORS protection
## Kali linux
Download package from https://www.google.com/chrome/ and install:
```bash
sudo dpkg -i ~/Downloads/google-chrome-stable_current_amd64.deb
```
Run google chrome
```bash
google-chrome  --user-data-dir="~/google-chrome-data" --disable-web-security
```


## References
1. https://stackoverflow.com/questions/3102819/disable-same-origin-policy-in-chrome