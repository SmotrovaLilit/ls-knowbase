---
tags:
- sqlInjection
---

# SQL Injection number of table column

If application has vulnerable parameter in sort parameter we can enumerate numbers. When error occurred it means that number of columns exceeded. 

```sql
SELECT * FROM users ORDER BY 2
```
ORDER BY 2 - means sorting by the second column in the table.
