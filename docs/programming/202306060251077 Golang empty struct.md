# Golang empty struct

Use empty struct for flags because it worths 0 byte. 
```golang
type Set map[int]struct{}
ch := make(chan struct{})
ch <- struct{}{}
```
https://dave.cheney.net/2014/03/25/the-empty-struct