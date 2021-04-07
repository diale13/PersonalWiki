# Syn Flooding

## TCP Handshake

Ver _redes_ para mejorar entendimiento de esta seccion, esto es un repaso.

A través de este intercambio de saludos o “handshake” de tres vías, un cliente establece una conexión TCP con un servidor

![](../../../.gitbook/assets/imagen%20%2849%29.png)

El servidor recibe un paquete SYN, asigna espacio en una tabla interna y devuelve un SYN / ACK a la persona que llama. La conexión permanece “medio abierta” hasta que el servidor recibe un ACK o la conexión expira.

## Syn Flooding

• Un ataque de inundación SYN ocurre cuando un atacante manipula la dirección de retorno en una serie de paquetes SYN. El servidor llena su tabla con estas conexiones medio abiertas.

![](../../../.gitbook/assets/imagen%20%2850%29.png)

Todos los accesos legítimos son denegados hasta que se agote el tiempo de espera de las conexiones.

## Soluciones a la inundación de SYN

• \(1\) – Aumente el tamaño de la cola del servidor: típicamente sólo 8 conexiones están permitidas: podría consumir recursos considerables.

• \(2\) – Acorte el periodo de tiempo de espera: podría rechazar conexiones de clientes más lentos.

• \(3\) – Filtrar paquetes sospechosos: si la dirección del remitente no coincide con la dirección original, descartar el paquete. Puede ser difícil de determinar.

• \(4\) – Cambiar el algoritmo: en lugar de almacenar el registro en la cola, envíe la información encriptada junto con el SYN / ACK. Un cliente legítimo lo enviará de vuelta con el ACK.

Agrego las de wikipedia:

1. Filtering
2. Increasing backlog
3. Reducing SYN-RECEIVED timer
4. Recycling the oldest [half-open TCP](https://en.wikipedia.org/wiki/TCP_half-open)
5. SYN cache
6. [SYN cookies](https://en.wikipedia.org/wiki/SYN_cookies)
7. Hybrid approaches
8. Firewalls and proxies





