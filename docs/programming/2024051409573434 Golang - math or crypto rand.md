# Math or crypto rand

For generating cryptographically strong random you should use crypto/rand. 

[ref](#references:1): 
```
For example, using `math/rand` to generate a 128-bit or 256-bit AES key would be a serious mistake, since the key would be easier to brute force. For that kind of use, you need a cryptographically strong random number generator, as provided by [`crypto/rand`](https://go.dev/pkg/crypto/rand/).
``` 

## References

1. [https://go.dev/blog/randv2](https://go.dev/blog/randv2)