# Analyses pattern Hierarchy
💡 Avoid using explicit hierarchy because it can be flatter in the future. 
Instead of:
![[Pasted image 20231006161822.png]]

- ⛔ If the organization changes, for example, regions are taken out to provide a flatter structure, then we must change the model.

Use hierarchy:
![[Pasted image 20231006161531.png]]

But: 
- ⛔ Limitation: it only supports a single organizational hierarchy
- ⚠️ As more hierarchies appear the structure will become unwieldy.

## References
1. Analysis Patterns: Reusable Object Models - Fowler, Martin, p. 20