# Kill process by port
## Mac
### Find
```bash
netstat -vanp tcp | grep 8000

```

``` bash
lsof -i tcp:8000
```
### Kill
```bash
kill -9 $(lsof -ti:8000)
```