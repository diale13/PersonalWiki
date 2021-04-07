# Hashing

## Funciones de Hash 

• Una función de Hash es una función que convierte texto de tamaño variable en un pequeño “dato”, generalmente un cadena de tamaño fijo. 

• Una función criptográfica de Hash tiene las siguientes cualidades adicionales: 

• Es difícil construir un texto que tenga un determinado Hash. 

• Es difícil modificar un texto dado, sin cambiar su Hash. 

• Es poco probable encontrar dos mensajes diferentes tenga en mismo Hash. 

• El valor del Hash se denomina “digest” del texto asociado.

 • Las funciones criptográficas de Hash se usan para proteger la integridad.

Existen varias formas de usar los hash, algunas vistas en Algoritmos 2 como apoyos en estructuras de datos que los hacen super eficientes. En seguridad y criptografia los podemos usar primero como un verificador de integridad. Es decir tomamos el resultado de aplicar una funcion de hash a un texto y vemos que de igual el texto que nos llega.

Una funcion sumamente sencilla es sumar todos los numeros del texto o archivo convertido. Esta funcion no es buena. Lo deseable para una funcion de hash es:

1. Velocidad media: para archivos grandes debe ser veloz pero no demasaido como para romperse \(ahora explico porque\)
2. Que si cambio algo del texto SE CAMBIE TODO EL HASH, una pequeña variacion puede ser corregida accidentalmente por la trasmision de otro bit incorrecto. Por ejemplo se me pierde un 1 y aparece otro 1 por error eso no deberia dar correcto pero con una suma lo hace.
3. Evitar colisiones de hash. Dos documentos no deben de tener el mismo resultado tras pasarlo por la funcion hash. Ahora es imposible garantizar esto por palomar \(en algun momento chocaran\) pero es deseable evitar la dispersion a toda costa.

MD5 es un ejemplo de un hash que fue vencido, es decir es posible crear documentos maliciosos facilmente. Aqui entra lo de la velocidad no muy rapida deseable. Si puedo generar un monton de documentos maliciosos para engañar y vencer al hash es mas facil de romper.

No usar md5 para guardar contraseñas

Antes era comun poner el hash del archivo a bajar en paginas de descarga, aunque no es la mejor idea del mundo ya que si modifican el archivo original tambien lo haran con el hash.

## Vocabulario 

• Una función f es preimagen resistente si, dada h, es difícil encontrar algún m tal que h = f \(m\). 

• Una función f es la segunda preimagen resistente si, dada una entrada m1, es difícil encontrar un m2, con m2 diferente de m1, tal que f \(m1\) = f \(m2\). 

• A esto se le llama resistencia de colisión débil. 

• Una función f es resistente a colisiones \(fuerte\), si es difícil encontrar dos mensajes m1 y m2, tal que f \(m1\) = f \(m2\)



## Ataque de cumpleaños

Sale de la llamada paradoja de cumpleaños _\(lo voy a poner en ingles porque me aburre traducir\)_

Que dice: "The high probability that two people in a room of 50 people will have the same birthday. 365 / 50, 1 in 6 or 17%? 

Actually it’s closer to 97% chance that two people will have the same birthday! "



If we compare every birthday to every other birthday, the amount of combinations in much greater.

![](../.gitbook/assets/imagen%20%281%29.png)

Using this principal of probability we can find the chance of a collision occurring in a hash algorithm. 

MD5 always outputs a hash of 128 bits long. \(3.4  _10^38 possible hashes\)_ 

_94 characters are accepted by MD5 and lets say passwords of length 20. \(2.9_  10^39 possible passwords\)

Time to compute all the password hashes would be around 1.4 \* 10^25 years, and to store them, trillions of petabyte drives. Luckily we can use the birthday paradox!

![](../.gitbook/assets/imagen%20%2827%29.png)

5.98 \* 10^19 for a 99% chance of collision. Less than one trillionth of a percent of the original keyspace. About 8 months on a high end PC.

This is the chance of finding a collision. **NOT** finding a specific collision with a specific hash. However once collisions have been found in a hashing algorithm, you can start to uncover how the algorithm generates that hash collisions. MD5 can have hash collisions generated in less than 17 seconds, thanks to Vlastimil Kilma. MD5 is still one of the most common hashing functions.

## Usos del Hash

Las funciones de Hash usualmente se usan para la **integridad**, no para la **confidencialidad**. 

• En un sistema de recuperación de documentos que contiene registros legales, puede ser importante saber que la copia recuperada es idéntica a lo que está almacenado.

 • En un sistema de comunicaciones seguro, la transmisión correcta de mensajes puede anular las preocupaciones de confidencialidad.













