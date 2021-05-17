# 1 - Lab 1

> This lab's email change functionality is vulnerable to CSRF.
>
>  To solve the lab, craft some HTML that uses a [CSRF attack](https://portswigger.net/web-security/csrf) to change the viewer's email address and upload it to your exploit server.
>
>  You can log in to your own account using the following credentials: `wiener:peter`

1. Haciendo uso del proxy sacamos la peticion para hacer update del correo.
2. Luego desde Burp pro en el historial obtenemos la peticion y usamos:  **Engagement tools / Generate CSRF PoC** con esto debemos complementarlo con un auto submit que sacamos de opciones. 

![](../../../.gitbook/assets/imagen%20%28730%29.png)



![](../../../.gitbook/assets/imagen%20%28729%29.png)

Vamos al exploit server que actua de pagina generada por atacante y lo explotamos.

