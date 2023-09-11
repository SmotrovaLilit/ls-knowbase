---
tags:
- securityPrinciples
---

# Fail-safe defaults or permissions based approach

By default, access should be denied, and then access conditions can be assigned to the principal.
The opposite of this principle is when proncipals have access to everything by default, and policies are written to deny them certain operations.
## Why we need to follow this principle

When the opposite principle is applied and administrators or programmers grant more permissions to a principal than needed, it can be challenging to identify this mistake. Additionally, testing permissions may become more difficult. 

## References
1. (Wheeler, 2021), [https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/follow-good-principles.html](https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/follow-good-principles.html) 
2. 