# Reflected XSS into a JavaScript string with single quote and backslash escaped

> This lab contains a [reflected cross-site scripting](https://portswigger.net/web-security/cross-site-scripting/reflected) vulnerability in the search query tracking functionality. The reflection occurs inside a JavaScript string with single quotes and backslashes escaped.
>
> To solve this lab, perform a cross-site scripting attack that breaks out of the JavaScript string and calls the `alert` function.



* Si ponemos algo se realiza un encode a url.
* Probando con `test'payload` vemos que se encodea **test%27payload** evitando romper el string con comillas
* Ahora, de cerrar el script antes se puede ejecutar el nuestro
* &lt;/script&gt;&lt;script&gt;alert\(1\)&lt;/script&gt;





