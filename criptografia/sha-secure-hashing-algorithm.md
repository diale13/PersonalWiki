---
description: Muy gracioso saber que fue vencido y se llama secure hashing algorithm
---

# SHA: Secure Hashing Algorithm

Algo importante de SHA es que no es encriptacion, no es necesario que se pueda volver al estado inicial, es usado para verificar integridad o alguna verificacion adicional.

Es comparable con una lavarropa, se ajustan las perillas \(en realidad son numeros a base que se manejan acorde a estados de inicio y fin dependiendo del mensaje\), y luego se pone en "la lavadora a dar vueltas". Esto es simbolico a una rotacion de 80 vueltas en un algoritmo de compresion propio de SHA. La gracia es se comprime y queda siempre igual retornando 128 bits.

![](../.gitbook/assets/imagen%20%2824%29.png)

Si el mensaje original es mas chico que 128 se hace un padding:

![](../.gitbook/assets/imagen%20%2810%29.png)

Sino se separa en varios y se junta \(creo\).

Los distintos SHA \(1,2,3\) van aumentando su seguridaad; el SHA1 es facilmente vencible por fuerza por alguien que tenga buen poder de computo.

