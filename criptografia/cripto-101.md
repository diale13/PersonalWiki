# Cripto 101

## Cifrado / Descifrado <a id="docs-internal-guid-2ee12945-7fff-2232-5d57-d0a033a9aebb"></a>

El propósito del cifrado es hacer que el mensaje sea menos útil / significativo para

cualquier espía. Conceptualmente, el proceso de el cifrado es bastante simple:  


![](https://lh5.googleusercontent.com/Sc5N8UI4bA7S3u0xZ3ybcwMrlHHVsM1JLfCPgbyaf_qyvhlF04OjsujRjun6xkeqjc3qbEm_yO0IfulbNbTg427xVRUER5u1MrTYZbw2kBubcYlLoLLxTfoIkl5siZpl7jJbN6Xz)

Al igual que en el proceso de descifrado  


![](https://lh6.googleusercontent.com/qMp-otS-52UNsvoag-tuD93QEd9aUEM6fvYpyDQ2RleWx92oFyXuSb2Hk2vPvA-2u2aM6nxWYX6IoJ5qkgb41lP3uUTt67GufAVluWh7b_wQTV8ARNS44VGtkglcEx3x3X_L6gKg)

## Teoría de la Información y Criptografía

La teoría de la información describe la criptografía de varias maneras:

• ¿Qué efectos tiene el cifrado de un mensaje en el contenido de la información del archivo?

• Un intento de descifrar un mensaje es realmente un intento de recuperar un mensaje de un canal \(sistemáticamente\) ruidoso.

• ¿Cómo puede la redundancia en la fuente dar pistas sobre el proceso de la decodificación?

• Es posible un cifrado perfecto \(es decir, uno que es teóricamente irrompible\)?  


**Reusmin:**  
• El cifrado está diseñado para ocultar el significado del texto.

• La redundancia es enemiga del cifrado seguro porque proporciona influencia al atacante.  


El cifrado y el descifrado son funciones que transforman un texto en otro.

En notación funcional:  
**C = E \(P\)  y  P = D \(C\)**  


Donde C denota texto cifrado, E es la regla de cifrado, D es la regla de ****descifrado, P es el texto plano. En este caso, también tenemos:    **P = D \(E \(P\) \)**  


_Obviamente, es importante poder recuperar el mensaje original del texto cifrado._  
  
A menudo, los algoritmos de cifrado y descifrado usan una clave K. La clave ****selecciona un algoritmo específico de la familia de algoritmos definidos por E. Escribimos esta dependencia como:   
C = E \(P, KE\) y P = D \(C, KD\)  


Si KE = KD, entonces el algoritmo es llamado simétrico. Si no, entonces es

llamado asimétrico. En general:  


P = D \(E \(P, KE\), KD\)  


Un algoritmo que no utiliza una clave se denomina cifrado sin clave.  


## Notación

• A menudo, la notación E \(P, K\) y D \(C, K\) se vuelve engorrosa. Por eso se usa una notación alternativa, particularmente en protocolos de criptografía.

• A menudo usaremos {P}K para denotar E \(P, K\), y algunas veces para

denotar D \(P, K\).

Por ejemplo: P = D \(E \(P, KE\), KD\) = {{P}KE} KD  


• Esto suele ser apropiado ya que, en muchos sistemas criptográficos

comerciales importantes, el mismo algoritmo se usa tanto para cifrado

como para descifrado \(es decir, el algoritmo es su propio inverso\)  


Un criptoanalista puede intentar hacer una o todas las siguientes cosas:  


• Romper un solo mensaje.

• Reconocer patrones en mensajes encriptados.

• Inferir algún significado sin romper el algoritmo.

• Denunciar la clave.

• Encontrar las debilidades en la implementación o en entorno o el uso de la

encriptación.

• Encontrar debilidades en el algoritmo, sin necesariamente habiendo

interceptado cualquier mensaje.

## Cifrado fuerte y Cifrado rompible

• Un algoritmo de cifrado se denomina “rompible” si, dado el tiempo

suficiente y los datos, un analista puede recuperar el texto plano.

• La mayoría de los algoritmos de cifrado son rompibles, ya que el analista

puede probar todas las claves sistemáticamente.

• Ser rompible no significa que sea factible de romperse.

• El analista debe ser capaz de reconocer el éxito. Por esta razón, tener pares

de texto plano / texto cifrado disponibles a menudo es necesario.  
  


• Un sistema criptográfico es fuerte si no hay un enfoque analítico que sea

sustancialmente más rápido que la fuerza bruta, es decir, probando todas

las claves una por una. La mayoría de los algoritmos fuertes son aún

rompibles.

• Cuanto mayor sea el espacio de claves, más tiempo se requiere para

encontrar la clave por búsqueda. ¿Cómo se calcula el tamaño del espacio

de claves?

• Muchos sistemas de cifrado usan una cadena de n bits como clave. Dado

un pequeño número de pares de texto claro / texto cifrado con la clave K,

dicho valor K puede ser recuperado mediante una búsqueda exhaustiva en

un tiempo esperado del orden 2n-1 de operaciones.  


## Construyendo bloque de cifrado

Los bloques de construcción de cifrado más simples son:  


• Sustitución: en la que cada símbolo se intercambia por otro \(no

necesariamente de manera uniforme\).

• Transposición: en la que se reorganiza el orden de los símbolos.  


Casi todos los cifrados simétricos comerciales modernos utilizan

alguna combinación de sustitución y transposición para el cifrado.  


Dos cosas que un paso de cifrado puede proporcionar son:  


• Confusión: transformar la información en texto plano para que un

interceptor no pueda extraerlo fácilmente.

• Difusión: difundir la información desde una región de texto plano

ampliamente sobre el texto cifrado.  


La sustitución tiende a ser buena en la confusión; la transposición tiende a ser bueno en la difusión  
  
  


### Resumen 

• Un algoritmo de cifrado es rompible si un proceso sistemático permite extraer el mensaje.

• Es fuerte si no hay un mejor ataque que la fuerza bruta.

• La mayoría de los algoritmos de encriptación simétrica usan una combinación de sustitución y transposición para lograr la confusión y difusión.  


## Cifrados de sustitución

• Un cifrado de sustitución es aquel en el que cada símbolo del texto plano se intercambia por otro símbolo.  


• Si esto se hace uniformemente, esto se denomina cifrado monoalfabético o cifrado de sustitución simple.  


• Si se realizan diferentes sustituciones dependiendo de dónde aparece el símbolo en el texto plano, esto se llama sustitución polialfabética.  


Sustitución Simple  


• Un cifrado de sustitución simple es una función inyectiva \(mapeo 1 a 1\) del

alfabeto en sí mismo o en otro alfabeto. ¿Cuál es la clave? ¿El alfabeto mismo?

• Un cifrado de sustitución simple es rompible; podría probar todos los

mapeos posibles \(k!\) del texto plano a los alfabetos de cifrado. Usualmente

esto no es necesario.

• Las redundancias en el texto plano \(frecuencia de las letras, di-gramas, etc.\)

se reflejan en el texto cifrado.

• No todos los cifrados de sustitución son cifrados de sustitución simple.  
  
• El **Cifrado de César** es un cifrado monoalfabético en el que cada letra

se reemplaza en el cifrado por otra letra que está ubicada a una “distancia” fija en el alfabeto.  


• Por ejemplo, A es reemplazado por C, B por D, … , Y por A, Z por B,

etc.

