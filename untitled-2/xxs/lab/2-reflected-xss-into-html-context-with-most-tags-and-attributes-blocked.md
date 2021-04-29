# 2 - Reflected XSS into HTML context with most tags and attributes blocked

> This lab contains a [reflected cross-site scripting](https://portswigger.net/web-security/cross-site-scripting/reflected) vulnerability in the search functionality but uses a web application firewall \(WAF\) to protect against common [XSS](https://portswigger.net/web-security/cross-site-scripting) vectors.
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





1.  Place the cursor before the `=` character and click "Add §" twice, to create a payload position. The value of the search term should now look like: 
2.  Visit the [XSS cheat sheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet) and click "copy events to clipboard".
3.  In Burp Intruder, in the Payloads tab, click "Clear" to remove the previous payloads. Then click "Paste" to paste the list of attributes into the payloads list. Click "Start attack".
4.  When the attack is finished, review the results. Note that all payloads caused an HTTP 400 response, except for the `onresize` payload, which caused a 200 response.
5.  Go to the exploit server and paste the following code, replacing `your-lab-id` with your lab ID:  `<iframe src="https://your-lab-id.web-security-academy.net/?search=%22%3E%3Cbody%20onresize=alert(document.cookie)%3E" onload=this.style.width='100px'>`
6.  Click "Store" and "Deliver exploit to victim".

![](../../../.gitbook/assets/imagen%20%28624%29.png)

![](../../../.gitbook/assets/imagen%20%28618%29.png)

