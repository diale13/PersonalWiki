# 1 - Teorico

Vulnerabilidad que permite inducir al usuario a hacer acciones que no quiere realizar realmente. Permite a un atacante bypasear la same origin policy tambien.

![](../../.gitbook/assets/imagen%20%28727%29.png)

### What is the impact of a CSRF attack? <a id="what-is-the-impact-of-a-csrf-attack"></a>

Si el ataque es exitoso la victima puede realizar acciones involuntarias como enviar una contraseña o cambiar su correo, ademas de enviar alguna transferencias de fondos. Se puede llegar a comprometer toda la cuenta.

### How does CSRF work? <a id="how-does-csrf-work"></a>

Se cumplen las siguientes claves:

*  **A relevant action.** Hay una accion dentro de la aplicacion que es inducida por el atacante. Esta puede ser privilegiada \(como modificar permisios o llevar a alguien a cambiar su contraseña\).
*  **Cookie-based session handling.** performa una accion usando una o mas requests http, la aplicacion utiliza solamente session cookies para identificar quien lo hace. No hay mecanismo para validar sesiones ni de tracking.
*  **No unpredictable request parameters.** Los parametros de la request no contienen parametros vulnerables a ataques donde se han de adivinar o detemrminar. 

Por ejemplo si una aplicacion contiene un cambio de correo para su cuenta donde se realiza el cambio de correo de la siguiente forma:

```http
 POST /email/change HTTP/1.1
 Host: vulnerable-website.com
 Content-Type: application/x-www-form-urlencoded
 Content-Length: 30
 Cookie: session=yvthwsztyeQkAPzeQ5gHgTvlyxHfsAfE

 email=wiener@normal-user.com
```

`Esto cumple las condiciones de CSRF`

* La accion de cambiar el correo es algo deseable para el atacante ya que puede llegar a tomar control completo de la cuenta de usuario.
* La aplicacion usa unicamente una session cookie para identificar la request, no hay otros mecanismos en juego para identificar la sesion.
*  El atacante puede determinar rapidamente los parametros requeridos para realizar la accion.

Con esto el atacante podria construir una pagina de la siguiente forma:

 `<html>  
   <body>  
     <form action="https://vulnerable-website.com/email/change" method="POST">  
       <input type="hidden" name="email" value="pwned@evil-user.net" />  
     </form>  
     <script>  
       document.forms[0].submit();  
     </script>  
   </body>  
 </html>`

 Suponiendo que la pagina sea suceptible a CSRF:

* El atacante provoca una HTTP request al sitio objetivo desde el creado
* Si el usuario esta logeado incluye su **session cookie** en la peticion. \(De no existir el sistema _SameSites cookies_\)
* El sitio vulnerable procesa la request como una normal.

## SameSite cookies

Existe un atributo llamado **SameSite** para controlar aspectos de las cookies relacionados a las peticiones cross-site. Con este atributo la aplicacion previene al browser de agregar de forma automatica cookies sin importar su origen.

Es un atributo agregado al **Set-Cookie** que puede incluir valores como **Strict o Lax**.

  `Set-Cookie: SessionId=sYMnfCUrAlmqVVZn9dqevxyFpKZt30NN; SameSite=Strict;`

 `Set-Cookie: SessionId=sYMnfCUrAlmqVVZn9dqevxyFpKZt30NN; SameSite=Lax;`

 Si SS esta colocado en **strict** el navegador no incluye cookies en peticiones originadas desde otro sitio, Esta es la opcion mas defenisva pero puede colocarse en medio de la comididad del usuario ya que si esta siguiendo un link de terceros no se podra logear. 

Si esta en Lax el browser si incluye la cookie cuando se cumplen las siguientes condiciones:

*  _The request uses the GET method. Requests with other methods, such as POST, will not include the cookie._
*  _The request resulted from a top-level navigation by the user, such as clicking a link. Other requests, such as those initiated by scripts, will not include the cookie._

 Usar las cookies con Lax provee  defensa parcial ante CSRF ya que  la mayoria de las que causan problemas son relacionados al POST. Los problemaas posibles son:

*  _Some applications do implement sensitive actions using GET requests._
*  _Many applications and frameworks are tolerant of different HTTP methods. In this situation, even if the application itself employs the POST method by design, it will in fact accept requests that are switched to use the GET method._

SS cookies provee defensa adicional pero no es suficiente por si sola para protejer a un sitio sobre CSRF. Se han de combinar con tokens.

## Profundizando

La politica que evita que los iframes dentro de la misma pagina se comuniquen entre ellos es la siguiente por ejemplo:

![](../../.gitbook/assets/imagen%20%28734%29.png)

Usando TOKENS

![](../../.gitbook/assets/imagen%20%28728%29.png)

![](../../.gitbook/assets/imagen%20%28732%29.png)

### De HTML a JSON

![](../../.gitbook/assets/imagen%20%28733%29.png)

![](../../.gitbook/assets/imagen%20%28735%29.png)

![](../../.gitbook/assets/imagen%20%28731%29.png)

## Como iniciar un ataque 

 Manually creating the HTML needed for a CSRF exploit can be cumbersome, particularly where the desired request contains a large number of parameters, or there are other quirks in the request. The easiest way to construct a CSRF exploit is using the [CSRF PoC generator](https://portswigger.net/burp/documentation/desktop/functions/generate-csrf-poc) that is built in to [Burp Suite Professional](https://portswigger.net/burp/pro):

*  Select a request anywhere in Burp Suite Professional that you want to test or exploit.
*  From the right-click context menu, select Engagement tools / Generate CSRF PoC.
*  Burp Suite will generate some HTML that will trigger the selected request \(minus cookies, which will be added automatically by the victim's browser\).
*  You can tweak various options in the CSRF PoC generator to fine-tune aspects of the attack. You might need to do this in some unusual situations to deal with quirky features of requests.
*  Copy the generated HTML into a web page, view it in a browser that is logged in to the vulnerable web site, and test whether the intended request is issued successfully and the desired action occurs.



