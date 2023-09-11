---
tags:
  - securityPrinciples
---

# Least common mechanism

Minimize the amount of using shared mechanisms: /tmp, /var/tmp, etc

The shared mechanism is a mechanism which common to more than one user and depended on all users.
Why we cann't use /tmp read here [[2023041501451616 Don't use tmp directory]]

## Why do we need to follow the principle
1. Shared mechanisms allow sharing state between programs. A single program that corrupts a shared state has the potential to corrupt other programs that are dependent on the state.
## References
1. (Wheeler, 2021), [https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/follow-good-principles.html](https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/follow-good-principles.html) 
2.  https://csf.tools/reference/nist-sp-800-53/r5/sa/sa-8/sa-8-2/