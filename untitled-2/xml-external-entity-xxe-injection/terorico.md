# Terorico

Es un tipo de vulnerabilidad web que permite al atacante vulnerar como se procesar datos XML. Resulta en ver archivos del sistema, interactuar con el backend o sistemasa. Puede escalar a un SSRF.

![](../../.gitbook/assets/imagen%20%28615%29.png)

Muchas aplicaciones usan XML para trasmitir data entre el navegador y el server. La mayoria manejan apis de xml vulnerables desde la especificacion misma de xml.

## Tipos

### Explotando XXE para obtener archivos

Cuando una entidad es definida conteniendo elementos de archivos y es retornada junto a la respuesta de la webapp

Para realizar la inyeccion neceitamos modificar el xml en dos formas:

* Introducir o editar un DOCTYPE element que defina una entidad externa contenienod el path al archivo.
* Editar el valor de unn XML retornado por la aplicacion usado para definir una entidad externa.

Suponer entonces que tenemos una aplicacion que busca el stock de un producto haciendo la siguiente peticion a un server:

 `<?xml version="1.0" encoding="UTF-8"?>  
 <stockCheck><productId>381</productId></stockCheck>`

La aplicacion no tiene ninguna defensa contra XXE entonces podemos explotar esto para obtener /etc/passwd

  `<?xml version="1.0" encoding="UTF-8"?>  
 <!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>  
 <stockCheck><productId>&xxe;</productId></stockCheck>`

Aqui se define una entidad externa \(&xxe\) que tiene de valor el contenido de etc/paswd, Usa el valor del product id para que nos lo retorne.

 `Invalid product ID: root:x:0:0:root:/root:/bin/bash  
 daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin  
 bin:x:2:2:bin:/bin:/usr/sbin/nologin  
 ...`

> With real-world XXE vulnerabilities, there will often be a large number of data values within the submitted XML, any one of which might be used within the application's response. To test systematically for XXE vulnerabilities, you will generally need to test each data node in the XML individually, by making use of your defined entity and seeing whether it appears within the response.





------------



*  [Exploiting XXE to retrieve files](https://portswigger.net/web-security/xxe#exploiting-xxe-to-retrieve-files), where an external entity is defined containing the contents of a file, and returned in the application's response.
*  [Exploiting XXE to perform SSRF attacks](https://portswigger.net/web-security/xxe#exploiting-xxe-to-perform-ssrf-attacks), where an external entity is defined based on a URL to a back-end system.
*  [Exploiting blind XXE exfiltrate data out-of-band](https://portswigger.net/web-security/xxe/blind#exploiting-blind-xxe-to-exfiltrate-data-out-of-band), where sensitive data is transmitted from the application server to a system that the attacker controls.
*  [Exploiting blind XXE to retrieve data via error messages](https://portswigger.net/web-security/xxe/blind#exploiting-blind-xxe-to-retrieve-data-via-error-messages), where the attacker can trigger a parsing error message containing sensitive data.





