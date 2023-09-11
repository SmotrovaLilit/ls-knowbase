---
tags:
- sqlInjection
---

# SQL Injection Stacked Queries

Stacked Queries  - it is a list queries executed in one request, separated by a semicolon.
Stacked queries are supported only by Postgres and MSSQL
Databases and applications process these queries differently. For example, they can execute only second or only first query. 
1. We can show results from another table
2. We can insert new record in second query or update record
Payload example:
```sql
10; select * from users
```
```sql
insert into users(id, username, password) values (1001,'hax','hax');
```

## References
1. web200.SQL Injection.Exploiting SQL Injection. Stacked Queries