# Golang receiver type

- If the structure is small and its methods do not modify it, then avoid using a pointer to avoid putting pressure on the garbage collector.
- If the structure is massive, it's better to use a pointer even if its methods do not modify it, in order to avoid copying large amounts of data.
- If at least one method uses a pointer, it's better to use pointers in all methods

## References
1. https://github.com/golang/go/wiki/CodeReviewComments#receiver-type
