# 4 - XML External Entities \(XXE\)

{% embed url="https://owasp.org/www-project-top-ten/2017/A4\_2017-XML\_External\_Entities\_\(XXE\)" %}

¿Que es? Existen malas configuraciones de XML para procesadores que evaluan elementos externos en documentos XML

¿Impacto? Extraccion de datos, ejecucion de codigo y puede llevar a un denial of service

¿Como prevenir?

* Usar JSON, evitar sensitive data 
* Patchear o mejorar todos los procesadores de XML
* Desabilitar XXE 
* Detectar, resolver y verificar la implementacion para el XXE con aplicaciones estaticas y testing

![](../../../.gitbook/assets/imagen%20%28444%29.png)

![](../../../.gitbook/assets/imagen%20%28432%29.png)

