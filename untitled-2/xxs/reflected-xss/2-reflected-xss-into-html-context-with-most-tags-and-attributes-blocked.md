# 2 - Reflected XSS into HTML context with most tags and attributes blocked

> This lab contains a reflected cross-site scripting vulnerability in the search functionality but uses a **web application firewall \(WAF\)** to protect against common XSS vectors.
>
>  To solve the lab, perform a cross-site scripting attack that bypasses the WAF and alerts `document.cookie`.

Probamos hacer el  `alert(document.cookie)` y nos rechaza todas las tags. Usamos burp intruder para hacer la prueba de atributos bloqueados.

1. Hacemos "Clear §" y cambiamos el termino a &lt;&gt;.
2. Luego dentro de las llaves hacemos el  "Add §" dos veces para marcar el payload. El valor debe ser `<§§>`
3.  Vamos a la [**XSS CHEATSHEET** ](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)y copiamos las tags, tenemos entonces las etiquetas de las mismas.

![](../../../.gitbook/assets/imagen%20%28619%29.png)

En el **intruder** de burp tenemos la opcion de payloads, ahi pegamos nuestra lista. Lo que ocurre es que ira probando una por una hasta lograr dar con una que funcione.

La unica que pasa sin recibir un HTTP400 es **body**.

Cambiamos el search term dentro de positions a `<body%20=1>` 

Luego hacemos que quede `<body%20§§=1>` y vamos nuevamente al cheatsheet, colocamos como nuevo payload "copy events to clipboard".

Lo que pasa es que estan blacklisted algunos eventos, realizamos lo mismo para los eventos y llegamos a que el onresize es el unico que causa un 200.

![](../../../.gitbook/assets/imagen%20%28624%29.png)

Vamos al exploit server y ponemos el exploit brindado por el lab: 

`<iframe src="https://acab1fc11f6a4bb3818e083000280033.web-security-academy.net/?search=%22%3E%3Cbody%20onresize=alert(document.cookie)%3E" onload=this.style.width='100px'>`

Deliver to victim y gg.

![](../../../.gitbook/assets/imagen%20%28618%29.png)

