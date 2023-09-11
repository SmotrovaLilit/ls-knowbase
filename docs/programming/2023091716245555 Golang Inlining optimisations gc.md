# Inlining optimisations
Inlining - it is optimization during the compilation process when small functions are combined into their respective callers. 

It allows:
- to remove the overhead of the function call
- to permit the compiler to apply other optimization strategies

Using //go:noinline we can turn of inlining for the function. 
```go
//go:noinline 
func max(a, b int) int { 
	if a > b { 
	    return a 
	} 
	return b 
}
```

## Inline budget

It is a cost of inlining the function, that is defined by the compiler. 

## Inline compiling flags
```bash
 -gcflags=-m=2
```
Allows to see the cost the compiler assigns to each function. [2](#references)

The inlining budget can be controlled to some degree with the `-gcflag=-l` flag. Currently the values that apply are:

- `-gcflags=-l=0` is the default level of inlining.
- `-gcflags=-l` (or `-gcflags=-l=1`) disables inlining.
- `-gcflags=-l=2` and `-gcflags=-l=3` are currently unused and have no effect over `-gcflags=-l=0`
- `-gcflags=-l=4` reduces the cost for inlining non-leaf functions and calls through interfaces.
## Functions which is ineligible for inlining
- Some functions may be ineligible because of their complexity. For example: recovery, break, select, go
- Functions with //go:noinline 
## Mid stack inlining
Mid stack inlining allows functions in the middle of a call stack to be inlined without requiring everything below them to be eligible.

Splitting functions into an easily inlineable function allows to reduce the cost. 
## References
1. https://dave.cheney.net/2020/04/25/inlining-optimisations-in-go
2. https://dave.cheney.net/2020/05/02/mid-stack-inlining-in-go


