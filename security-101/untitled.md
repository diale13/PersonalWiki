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

## Risk Management Concepts

**Risk vector**

Identificamos los puntos clave donde el riesgo afectaria mas a nuestra organizacion

* Mission-critical IT systems
  * Sistemas de pago
  * RH
  * Emergencia
* Datos sensibles
* Acceso de terceros
* Accesos fisicos
* Server room access
* Limitar USB 

Para controlar estos vectores de riesgo se introducen los **Risk Management Frameworks \(RMFs\)**

* Center for Internet Security \(CIS\): publica mejores practicas
* NIST Risk Management Framework
* ISO \(internation Organizzation For Standarization\); 27001/27002/27701/3100
  * IT system and information security

**Data Privacy Regulations and Standards**

* General Data Protection Regulation \(GDPR\)
* Health Insurance Portability and Accountability Act \(HIPAA\)
* Payment Card Industry Data Security Standard \(PCI DSS\)

## Security Controls

* Solucion que mitiga ameenaza/riesgos
  * Ejemplo: antivirus que mitiga infecciones de malware

### **Security Control Categories • Managerial/administrative**

* Que debe hacerce?
* Check de background
* Cada cuanto?
* Revision de politicas de seguridad y tecnicas

### **Security Control Types • Physical**

* Ingreso aal vestibulo o recepcion
* Logs
* Correccion de vulnerabilidades

### **Risk Example • Risk**

* Robo de identidades
* Correos maliciosos
* Conocimiento de seguridad de empleados
* Filtros de spam
* Antivirus

## Risk Assessments and Treatments

* Un risk assestment busca determinar la probabilidad de que ocurra una amenaza
* Los riesgos pueden ser ambientales \(terremotos\), causados por personas, internas o externas
* Los tratamientos sobre estos riesgos \(management\) incluyen aceptacion, mitigacion, transferencia y el evitarlos.

## Quantitative Risk Assessments

* Aqui entra el concepto de Single Loss Expectancy \(SLE\): cuanta perdida podemos esperar con un incidente negativo? 
  * Se toma el valor de un asset y se multiplica por el valor de exposicion

![](../.gitbook/assets/imagen%20%28931%29.png)

Calculado esto se hace la multiplicacion de arriba: 24000x0,125

Se puede expandir esto a una version anual, multiiplicando este valor anterior obtenido X la frecuencia de ocurrencias 

## Qualitative Risk Assessments

Es basado en elementos subjetivos como son:

* Probabilidad
* Impacto de la amenaza \(threat\)

Se asigna luego un score basado en esto. Es subjetivo por lo que dos personas pueden llegar a distintos resultados.

![Risk register example](../.gitbook/assets/imagen%20%28945%29.png)

Podemos generar un Risk Heat Map donde tomamos riesgo e impacto

![Risk Heat Map ](../.gitbook/assets/imagen%20%28946%29.png)

Una matriz es similar pero es sin los colores y llevado a los riesgos.

## Business Impact Analysis \(BIA\)

Hacemos una priorizacion de los procesos critiocs para el negocio, por ejemplo los sistemas de pago  en retail o los registros de pacientes en un hospital.

* Financiero
* Reputacional
* Perdida de datos

**Field component**: son elementos de campo como el mismo software O puede ser elementos de hardware como servidores

* **Mean time between failures \(MTBF\)**
  *  Average time between repairable component failures
  * Software patching
* **Mean time to failure \(MTTF\)**
  * Average time between NON-repairable component failures
  * Hard disks, switches, routers
* **Mean time to repair \(MTTR\)**
  * Time required to repair a failed component

Ubicar recursos criticos:

* Donde estan los datos
* Realizar Privacy Threashold Assesment \(PTA\)
* Privacy impact assesment

**Recovery time objetivce \(RTO\):** define maximo tolerable de downtime

**Recovery point objective \(RPO\):** maximo tolerable de perdida de datos



\*\*\*\*









