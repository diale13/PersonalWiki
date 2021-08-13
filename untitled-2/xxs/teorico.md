# Teorico

## Introduccion

El cross site es una vulnerabilidad web que permite al atacante comprometer las interaciones de los usuarios con las aplicaciones vulnerables.

Puede pasar por encima de las politicas de same origin, designadas para separar las distintas paginas entre ellas. XSS permite hacerse pasar por otra persona, aceder datos. La victima gana un acceso privilegiado a la aplicacion y el atacante puede ganar control completo sobre las funcionalidades.

XSS funciona manipulando una web para que haga ejecutar codigo JS malicioso al usuario. 

![](../../.gitbook/assets/imagen%20%28623%29.png)

## Tipos de XSS

*  [**Reflected XSS**](https://portswigger.net/web-security/cross-site-scripting#reflected-cross-site-scripting), where the malicious script comes from the current HTTP request.
*  [**Stored XSS**](https://portswigger.net/web-security/cross-site-scripting#stored-cross-site-scripting), where the malicious script comes from the website's database.
*  [**DOM-based XSS**](https://portswigger.net/web-security/cross-site-scripting#dom-based-cross-site-scripting), where the vulnerability exists in client-side code rather than server-side code.

### Reflected

Reflected es la version mas simple, una vez que recibe data en la request interactua con esa data de una forma insegura. Por ejemplo:

 `https://insecure-website.com/status?message=All+is+well.`

 `<p>Status: All is well.</p>`

 Como la pagina no hace procesado de datos el atacante puede modificar la linea:

 `https://insecure-website.com/status?message=<script>/*+Bad+stuff+here...+*/</script>`

 `<p>Status: <script>/* Bad stuff here... */</script></p>`

 El url puede ser construido desde el atacante y atacar al usuario.

### Stored

Tambien conocido como persistente o de segundo orden. Ocurre cuando una aplicacion recibe una inyeccion que se aplica a todas las respuestas http posteriores.

Ocurren en comentarios de blogs, usuarios o etc. Otras formas ocurren desde correos o al responder con mensajes automaticos.

Por ejemplo al dejar un comentario queda algo asi en el html renderizado:

 `<p>Hello, this is my message!</p>`

Que pasa si se incrusta un script no sanitizado

 `<p><script>/* Bad stuff here... */</script></p>`

### DOM-Based

Ocurre cuando la aplicacion contiene js del lado del cliente procesando datos de forma insegura y los retorna al DOM. Recordar que Document Object Model \(DOM\) es la representacion jerarquía de los elementos de una pagina; esta misma usa JavaScript para manipularse. 

 Por ejemplo aqui lee el valor del input y lo manda al html

`var search = document.getElementById('search').value;  
var results = document.getElementById('results');  
results.innerHTML = 'You searched for: ' + search;`

Un atacante puede tomar el valor del input y construir codigo malicioso:

`You searched for: <img src=1 onerror='/* Bad stuff here... */'>`

 **Fuentes comunes**

 `document.URL  
 document.documentURI  
 document.URLUnencoded  
 document.baseURI  
 location  
 document.cookie  
 document.referrer  
 window.name  
 history.pushState  
 history.replaceState  
 localStorage  
 sessionStorage  
 IndexedDB (mozIndexedDB, webkitIndexedDB, msIndexedDB)  
 Database`

##  Impactos y existencias

Un ataque real puede llevar a un usuario malicioso a:

* Hacerse pasar por un usuario distinto
* Llevar a un usuario a hacer una accion que no pretende
* Leer data del usuario
* Inyectar codigo

Esto hace que el ataque exitoso pueda tener un alto impacto en la aplicacion sobretodo al tratar con informacion sensible.

## Encontrando vulnerabilidades

* Muchas de las vulnerabilidades pueden ser detectadas utilizando el **web vulnerability scanner** de burpsuit.
* Adicionalmente se han de testear todos los lugares donde se ingresen elementos por el usuario a fin de buscar estos puntos debiles.

Cuando buscamos **reflected** o **stored** xss se ha de identificar el contexto:

* Lugar donde se puede manipular datos
* Input validations o porcesos que se realizan en la aplicacion.

 Luego para DOM-Based muchas salen de los url con sus parametros. Hay otras que emergen de imput como document.cookie o de set timeouts.

## Mitigaciones

Content security policy \(CSP\) es un mecanismo del navegador apuntado a mitigar el impacto de xss. Si una app usa CSP esta puede prevenir alguna explotacion del mismo. Por ejemplo puede forzar a la pagina a ejecutar scripts unicamente provenientes del mismo sitio.

## Previniendo XSS

* Filtrar inputs al arrivar
* Encode data on output: a fin de eliminar el control del usuario
* Uso de headers de respuesta: Content-Type o X-Content-Type-Options para asegurar que el navegador haga lo requerido
* CSP

