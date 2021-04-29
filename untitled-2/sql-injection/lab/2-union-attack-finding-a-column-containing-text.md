# 2 - UNION attack, finding a column containing text

> This lab contains an SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables. To construct such an attack, you first need to determine the number of columns returned by the query. You can do this using a technique you learned in a [previous lab](https://portswigger.net/web-security/sql-injection/union-attacks/lab-determine-number-of-columns). The next step is to identify a column that is compatible with string data.
>
>  The lab will provide a random value that you need to make appear within the query results. To solve the lab, perform an [SQL injection UNION](https://portswigger.net/web-security/sql-injection/union-attacks) attack that returns an additional row containing the value provided. This technique helps you determine which columns are compatible with string data.

Esta vez se debe usar burp para interceptar y modificar lasa requests porque algunas son sanitizadas. Determinamos las columnas retornadas por la query igual que en el lab anterior. 

Usamos: `'+UNION+SELECT+NULL,NULL,NULL--`

Luego el lab nos pide encontrar un random string, en mi caso wjvI9f. Eso es lo que pondremos en una columna a buscar. Y queda algo asi:

`'+UNION+SELECT+'`wjvI9f`',NULL,NULL--` De no encontrarlo probamos mover el string y volver a poner el null

![](../../../.gitbook/assets/imagen%20%28620%29.png)

