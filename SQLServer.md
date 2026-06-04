SQL Server / Transact SQL
======

### Get version:

```sql
SELECT @@version;
-- Microsoft SQL Server 2016 (SP3-GDR) (KB5029186) - 13.0.6435.1 (X64) 
--	Jul 30 2023 19:53:42 
--	Copyright (c) Microsoft Corporation
--	Developer Edition (64-bit) on Windows Server 2016 Standard 10.0 <X64> (Build 14393: ) (Hypervisor)
```

### Get current database name

```sql
SELECT DB_NAME()
-- EBX5
```

### Get details about database physical files on disk
```sql
SELECT * FROM sys.database_files
```

### Get active sessions and processed
```sql
sp_who2 'active'

-- To kill one session 
kill {SPID value}
```

### List running queries
```sql
SELECT  *
FROM    sys.dm_exec_requests  
        CROSS APPLY sys.dm_exec_sql_text(sql_handle)  ;
```
