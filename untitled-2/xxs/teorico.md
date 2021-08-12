# Teorico

## Introduccion

El cross site es una vulnerabilidad web que permite al atacante comprometer las interaciones de los usuarios con las aplicaciones vulnerables.

Puede pasar por encima de las politicas de same origin, designadas para separar las distintas paginas entre ellas. XXS permite hacerse pasar por otra persona, aceder datos. La victima gana un acceso privilegiado a la aplicacion y el atacante puede ganar control completo sobre las funcionalidades.

XXS funciona manipulando una web para que haga ejecutar codigo JS malicioso al usuario. 

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

Content security policy \(CSP\) es un mecanismo del navegador apuntado a mitigar el impacto de xss. Si una app usa CSP esta puede prevenir alguna explotacion del mismo. Por ejemplo puede forzar a la pagina a ejecutar scripts unicamente provenientes de 







 [Exploiting cross-site scripting vulnerabilities](https://portswigger.net/web-security/cross-site-scripting/exploiting)

###  <a id="how-to-find-and-test-for-xss-vulnerabilities"></a>

**Read more**

 [Cross-site scripting contexts](https://portswigger.net/web-security/cross-site-scripting/contexts)

###  <a id="content-security-policy"></a>

**Read more**

 [Content security policy](https://portswigger.net/web-security/cross-site-scripting/content-security-policy)

### Dangling markup injection <a id="dangling-markup-injection"></a>

 Dangling markup injection is a technique that can be used to capture data cross-domain in situations where a full cross-site scripting exploit is not possible, due to input filters or other defenses. It can often be exploited to capture sensitive information that is visible to other users, including CSRF tokens that can be used to perform unauthorized actions on behalf of the user.

**Read more**

 [Dangling markup injection](https://portswigger.net/web-security/cross-site-scripting/dangling-markup)

### How to prevent XSS attacks <a id="how-to-prevent-xss-attacks"></a>

 Preventing cross-site scripting is trivial in some cases but can be much harder depending on the complexity of the application and the ways it handles user-controllable data.

 In general, effectively preventing XSS vulnerabilities is likely to involve a combination of the following measures:

*  **Filter input on arrival.** At the point where user input is received, filter as strictly as possible based on what is expected or valid input.
*  **Encode data on output.** At the point where user-controllable data is output in HTTP responses, encode the output to prevent it from being interpreted as active content. Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.
*  **Use appropriate response headers.** To prevent XSS in HTTP responses that aren't intended to contain any HTML or JavaScript, you can use the `Content-Type` and `X-Content-Type-Options` headers to ensure that browsers interpret the responses in the way you intend.
*  **Content Security Policy.** As a last line of defense, you can use Content Security Policy \(CSP\) to reduce the severity of any XSS vulnerabilities that still occur.

**Read more**

 [How to prevent XSS](https://portswigger.net/web-security/cross-site-scripting/preventing) [Find XSS vulnerabilities using Burp Suite's web vulnerability scanner](https://portswigger.net/burp/vulnerability-scanner)

### Common questions about cross-site scripting <a id="common-questions-about-cross-site-scripting"></a>

 **How common are XSS vulnerabilities?** XSS vulnerabilities are very common, and XSS is probably the most frequently occurring web security vulnerability.

 **How common are XSS attacks?** It is difficult to get reliable data about real-world XSS attacks, but it is probably less frequently exploited than other vulnerabilities.

 **What is the difference between XSS and CSRF?** XSS involves causing a web site to return malicious JavaScript, while CSRF involves inducing a victim user to perform actions they do not intend to do.

 **What is the difference between XSS and SQL injection?** XSS is a client-side vulnerability that targets other application users, while SQL injection is a server-side vulnerability that targets the application's database.

 **How do I prevent XSS in PHP?** Filter your inputs with a whitelist of allowed characters and use type hints or type casting. Escape your outputs with `htmlentities` and `ENT_QUOTES` for HTML contexts, or JavaScript Unicode escapes for JavaScript contexts.

 **How do I prevent XSS in Java?** Filter your inputs with a whitelist of allowed characters and use a library such as Google Guava to HTML-encode your output for HTML contexts, or use JavaScript Unicode escapes for JavaScript contexts.

