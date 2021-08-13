# Risk Management

## Definiendo riesgo

Comenzamos hablando de la gestión de riesgos. Tomamos **riesgo** como la probabilidad de que un atacante pueda tomar ventaja de una vulnerabilidad amenazando a algún activo.

Este activo varia en el contexto, para un dragón puede ser su tesoro a defender de hobbits, para una organización pueden ser sus datos, su infraestructura, etc.

**Actores:** 

* Hackers
* Hacktivists
* Script kiddies \(uso de ataques conocidos, herramientas sencillas, nosotros ahora ja\)
* Insiders,
* Competencia
* Shadow it \(infraestructura de tu empresa no controlada, no asegurada\)
* Organizaciones criminales y estados

**Vulnerabilidades**: puntos débiles que pueden ser explotados a beneficio del atacante

**Amenaza:** ataque que explota la vulnerabilidad.

**Remediación:** que hacemos para bajar el impacto de estas amenazas. **** 

## Amenazas y vulnerabilidades

La seguridad se basa en la protección de los pilares CIA sobre la información.

**Confidencialidad:** impide la divulgación de información a todos los individuos, entidades o procesos no autorizados. Asegura acceso a información solo a quienes estén realmente autorizados para verlos.

**Integridad:** propiedad de mantener los datos libres de modificaciones no autorizadas. Busca mantener con exactitud la información tal cual fue generada, sin ser manipulada ni alterada por personas o procesos no autorizados.

**Disponibilidad \(Availability\) :** la información está disponible a quienes \(personas, procesos o aplicaciones\) deban acceder a ella.

Un **Pathway Vector** es un camino que puede recorrer un atacante para lograr afectar alguno de estos pilares al ganar acceso. Por ejemplo:

* Configuraciones débiles o inexistentes.
* Puertos de firewalls abiertos.
* Falta de seguridad por parte de los usuarios.
* Falta de 2FA.
* Falta de parches:
  * Equifax hack
* Usbs hackeados
  * Stuxnet worm

Los Supply-chain attack son otro vector popular, se colocan entre la distribución de un producto o servicio.

* Mano facturadores
* Contratistas
* Implementadores
* Software tercerizado
  * Clausula Right-to-audit 

## Threat Intelligence

Es el acto de aplicar metodologías a estas amenazas a fin de:

* Facilitar la gestión de riesgos
* Realizar el Hardening correspondiente
* Reducir el tiempo de respuesta
* Proveer un insight de seguridad.

Brinda además tácticas y técnicas junto a procedimientos para cumplir estos objetivos. Esto en ingles es: adversary tactics, techniques and procedures \(**TTP**\).

Las fuentes para el estudio de esto pueden ser open source o no, abarcando desde bases de datos como exploit-db o common vulnerability and expousures \(**CVE**\).

Existen muchas fuentes de información, algunas incluso en la red Tor, esto hace la necesidad de compartir esta información entre todos, entra Automated Indicator Sharing \(AIS\), permite el intercambio de información de seguridad entre entidades, maneja una expresión de amenazas llamada STIX

**Trusted Automated eXchange of Intelligence Information \(TAXII\)**

* Es como un RSS pero para amenazas
* Consiste en TAXII servers y clientes
* Constituye amenazas en tiempo real y feeds.





