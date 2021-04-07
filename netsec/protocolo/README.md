# Protocolo

• Los protocolos criptográficos cumplen funciones relacionadas con la seguridad a través de un intercambio estructurado de mensajes. 

• Son muy importantes para la seguridad en Internet.

• Un protocolo es un **diálogo estructurado entre dos o más partes en un contexto distribuido que controla la sintaxis, la semántica, y sincronización de la comunicación, y diseñado para lograr una función relacionada con la comunicación.** 

• Un protocolo critográfico es un protocolo que usa mecanismos criptográficos para lograr algunas funciones relacionadas con la seguridad

Entre los objetivos de los protocolos criptográficos se encuentran los siguientes: 

• Unicidad: secreto compartido exactamente por dos partes 

• Integridad: el mensaje llegó sin modificaciones 

• Autenticidad: el reclamo de origen del mensaje es verdadero 

• Confidencialidad: los contenidos del mensaje son inaccesibles para un escucha.

 • No repudio de origen: el remitente no puede denegar el envío. 

• No repudio de recibo: el receptor no puede negar la recepción.

## Fundamentos de los protocolos criptográficos 

• Todos los protocolos criptográficos comparten las siguientes características: 

• Varios actores están intercambiando mensajes 

• Están tratando de cumplir con algunas funciones relacionadas con la seguridad 

• Están operando en un ambiente hostil e inseguro.

 • El protocolo debe ser robusto y confiable frente a un atacante determinado.



Un protocolo implica una secuencia de intercambios de mensajes de la forma:

![A le env&#xED;a a B el mensaje M. ](../../.gitbook/assets/imagen%20%2829%29.png)

• Debido a la naturaleza distribuida del sistema y la posibilidad de actores maliciosos, típicamente no hay garantía de que B reciba el mensaje, o incluso que está esperando el mensaje.

• Debido a la naturaleza distribuida del sistema, los protocolos son altamente asincrónicos.

• Un participante de un protocolo no sabrá nada sobra la corrida actual del protocolo excepto los mensajes que ha recibido y enviado.

• Excepto por el iniciador, otros participantes ni siquiera sabrán que ellos están participando hasta que reciban su primer mensaje. 

• Cada mensaje enviado debe ser de una forma tal que el destinatario pueda identificarlo y responderlo.





## Verificación de un protocolo

Hay varios enfoques principales para el problema de verificación:

• \(1\) – **Las lógicas de autenticación** permiten razonar sobre qué actores dentro del protocolo deberían ser capaces de inferir de los mensajes que ven. Permite pruebas abstractas, pero pueden pasar por alto algunos defectos importantes.

• \(2\) – **Métodos de exploración de estado** \(comprobación del modelo\) tratan un protocolo como un sistema de estado finito y realizan una búsqueda exhaustiva verificando que todos los estados alcanzables sean seguros. 

• \(3\) – La demostración del **teorema de propósito general** usa la inducción sobre los potenciales rastros de la ejecución del protocolo.



### Lógica de Autenticación

• Una lógica de autenticación es un sistema formal para razonar acerca de la autenticación. Cualquier lógica consiste en un conjunto de operadores lógicos y reglas de inferencia.

 • Un truco es tomar una secuencia de intercambios de mensajes y generar una colección de declaraciones de autenticación.

 • Tiene que postular algunas suposiciones iniciales razonables sobre el estado de conocimiento / autenticación de los actores.





