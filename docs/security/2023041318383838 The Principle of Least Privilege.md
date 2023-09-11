---
tags:
  - securityPrinciples
---

# The Principle of Least Privilege

User accounts, program codes, and other parts of systems should only be granted the minimum required privileges.

## Another ways

principle of minimal privilege. 
for users: least user access or least-privileged account,  LUA

## Why we need to follow this principle

- Better system stability. If a system component is restricted in its permissions, it is easier to test its interactions with other components and investigate the causes of failures when the number of possible operations by the component is limited. Additionally, such restricted components will not have access to perform operations that could potentially lead to system failures.
- Better system security.
	- Vulnerabilities in one application cannot be used to exploit another application.
	- If this principle is adhered to, it will be more difficult for an intruder who gains access to an account or other part of the system to obtain more extensive privileges.
	- Adhering to this principle significantly reduces the attack surface.
	- This principle limits the damage from an accident, error, or attack.
- Ease of deployment. Sometimes, components that require higher privileges may require additional actions during deployment, for example, assigning necessary roles or policies.

## References

1. (Wheeler, 2021), [https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/follow-good-principles.html](https://dwheeler.com/secure-programs/Secure-Programs-HOWTO/follow-good-principles.html)
2. (Wikipedia, 2021), [https://en.wikipedia.org/wiki/Principle_of_least_privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege)
3.