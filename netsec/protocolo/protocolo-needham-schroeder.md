# Protocolo Needham-Schroeder

Needham-Schroeder es un protocolo de autenticación de clave compartida que ha sido muy importante históricamente.

• Muchos protocolos existentes se derivan de uno propuesto por Needham y Scroeder \(1978\), incluida la suite del protocolo de autenticación Kerberos ampliamente utilizado.

• N-S es un protocolo de autenticación de clave compartida diseñado para generar y propagar una clave de sesión, es decir, una clave compartida para posteriores comunicaciones encriptadas simétricas. 

• Tenga en cuenta que no existe una infraestructura de clave pública en uso.

## El protocolo

Hay tres actores: A y B, dos actores que desean una comunicación mutua, y S, un servidor de clave de confianza.

![](../../.gitbook/assets/imagen%20%2822%29.png)

Se supone que A y B ya tienen una comunicación simétrica segura con S usando las claves Kas y Kbs, respectivamente.



• N-S usa “nonces” \(abreviatura de “numbers used once”\), valores generados aleatoriamente incluidos en los mensajes.

• Si un “nonce” es generado y enviado por A en un solo paso y devuelto por B en un paso posterior, A sabe que el mensaje de B es reciente y no una respuesta desde un intercambio anterior.

• Un “nonce” no es una marca de tiempo. La única suposición es que no se han usado en ningún intercambio anterior, con alta probabilidad.

![](../../.gitbook/assets/imagen%20%2823%29.png)

![](../../.gitbook/assets/imagen%20%288%29.png)

## Vulnerabilidades

Denning y Sacco señalaron que el compromiso de la clave de una sesión tiene malas consecuencias. Un intruso puede reutilizar la clave de una sesión anterior y pasarla como una clave nueva.

![](../../.gitbook/assets/imagen%20%2841%29.png)

Supongamos que C ha descifrado Kab de la ejecución del protocolo de la semana pasada, y ha escondido el mensaje 3 de esa sesión:

![](../../.gitbook/assets/imagen%20%2845%29.png)

• B creerá que está hablando con A.

• Problema: El mensaje 3 no está protegido por “nonces”. No hay forma para que B sepa si el Kab que recibe es actual. Un intruso tiene tiempo ilimitado para descifrar una clave de sesión antigua y reutilizarla como si fuera nueva. 

• Ejemplo de Ataque: Un empleado ejecuta los primeros pasos del protocolo varias veces, reuniendo tickets {Kab , A}Kbs para cada servidor B diferente en el sistema. Si lo despiden, todavía puede inicial sesión en todos los servidores de la compañía.

• Bauer, y otros, señaló que si la clave Kas se vio comprometida, cualquiera podría hacerse pasar por A y establecer comunicación con cualquier otra parte.

![](../../.gitbook/assets/imagen%20%2833%29.png)

• **Estos defectos persistieron durante casi 10 años antes de que fueran descubiertos**

_• Los “ataques” descubiertos por Denning y Sacco, y por Bauer, y otros, cuestionan que pasa si una clave se rompe. • ¿Es justo hacer esa pregunta? ¿No es una presunción de cualquier protocolo criptográfico que la encriptación es fuerte?_

\_\_







