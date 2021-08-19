# Burp Collaborator

## ¿Que es Burp Collaborator?

Burp Collaborator es un servicio que ayuda a descubrir algunas vulnerabilidades. Por ejemplo:

* Algunas inyecciones que se detectan al usar payloads que detonan una interaccion con un sistema externo cuando ocurren de forma exitosa. Por ejemplo alguna SQL blind inyection puede solo ser relevante al interactuar con sitios web y sus tiempos de respuesta,
* Algunas vulnerabilidades de servicios pueden ser detectadas usando payloads que hacen a los servicios interactuar con aplicaciones y analizar los resultados. Por ejemplo **mail header injection**
* Algunas vulnerabilidades son iintroducidas al retirar contenido de sistemas externos. Por ejemplo una url en su respuesta.

Cuando se usa el collaborator Burp envia payloads a la aplicacion auditada que causen interacciones con el collaborator. Estas intereacciones son detectadas y se determiina si ocurren interacciones especificas.

![](../../.gitbook/assets/imagen%20%28934%29.png)

## ¿Como funciona?

* Tiene su propio nombre de dominio, el server esta registrado como authoritative dns server para ese dominio
* Provee su propio DNS service para responder cualquier lookup 
* Provee HTTP/HTTPS con su propio certificado
* Tiene SMTP/SMTPS

### **Detecting external service interaction**

Un ejemplo de uso:

* Burp envia un payload a la aplicacion conteniendo un URL que usa un random subdomain del burp collaborator. Por ejemplo `param=http://yaduishasdh9asd.burpcollaborator.net`
* Dado el comportamiento esperado de la aplicacion \(asi sea planeado o no\), se hace un lookup de la peticion.
* El DNS del lookup y del http llegan al collaborator conteniendo informacion que es analizada en el subdominio especificiado.
* Burp le pregunta al collaborator: "Recibiste informacion de mi payload?" y el collaborator se la responde
* Burp reporta la informacion al servidor incluyendo la interaccion de mensajes capturados por el collaborator.

![](../../.gitbook/assets/imagen%20%28936%29.png)

### **Detecting out-of-band resource load**

Out of band resource load es cuando una app puede ser inducida a cargar contenido de una fuente externa arbitraria para luego incluirla en su respuesta. Burp Suite detecta esto induciendo al collaborator server a retornar data especifica en sus respuestas para la interaccion externa y ver como se comporta

![ponele...](../../.gitbook/assets/imagen%20%28941%29.png)

### **Detecting blind SQL injection**

Si llevas a interactuar a la app inyectando codigo el collaborator te avisa

![](../../.gitbook/assets/imagen%20%28943%29.png)

**Detecting blind cross-site scripting**

![](../../.gitbook/assets/imagen%20%28937%29.png)

