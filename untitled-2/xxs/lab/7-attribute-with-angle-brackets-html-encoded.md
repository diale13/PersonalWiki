# 7 - Attribute with angle brackets HTML-encoded

> This lab contains a [reflected cross-site scripting](https://portswigger.net/web-security/cross-site-scripting/reflected) vulnerability in the search blog functionality where angle brackets are HTML-encoded. To solve this lab, perform a cross-site scripting attack that injects an attribute and calls the `alert` function.

Al enviar algo por la barra de busqueda vemos que nos encodea el envio desde el burp. Entonces cambiamos el parametro de busqueda desde el burp

GET /?search="onmouseover="alert\(1\) HTTP/1.1

Pasando la mano por arriba de la barra ya lo ejecuta.



