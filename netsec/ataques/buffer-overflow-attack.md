---
description: 'https://www.youtube.com/watch?v=1S0aBV-Waeo'
---

# Buffer Overflow Attack

## Entendiendo la memoria \(linux\)

![](../../.gitbook/assets/imagen%20%28376%29.png)

* **Kernel:** variables de ambiente u elementos de parametros para la terminal
* **Text:** codigo de un programa, lo que compilamos \(read only\)
* **Data**: variables sin inicializar y las inicializadas
* **Heap**: area muy grande donde se agregan lo que va necesitando el programa. Lo mas grande de esto.
* **Stack:** variables locales y funciones

Del stack sale el stackoverflow, y tambien los ataques a buffer suelen ir para ahi.

![](../../.gitbook/assets/imagen%20%28366%29.png)

![](../../.gitbook/assets/imagen%20%28386%29.png)

Vemos que el stack crece hacia esa direccion, los parametros que agregamos se ponen en esa direccion.

## Buffer overflow

Es un tipo de ataque donde mediante un código por ejemplo en c, escribimos algo que supera el largo del bloque de memoria intencionado. Por lo que nos vamos a otro bloque.

Los ejecutables son mantenidos en memoria.

Ahora vamos a atacar:

![](../../.gitbook/assets/imagen%20%28389%29.png)

Lo que hace es crear un buffer de 500 caracteres y colocar el parametro\(s\) de char en el mismo

Asi queda nuestra memoria:

![](../../.gitbook/assets/imagen%20%28385%29.png)

El base pointer no importa mucho pero el return es el valor de la variable que retornaremos y/o ejecutaremos. Lo que queremos lograr es pasarnos por completo del buffer y ejecutar en el return lo que nosotros querramos.

Usaremos el compilador **gdb**

**C**orriendo eso con ayuda de un script de python no solo asigna los valores sino que se pasa

![](../../.gitbook/assets/imagen%20%28387%29.png)

Obtenemos entonces un segmentation fault. Eso es bueno implica que linux se dio cuenta que tocamos algo que no deberiamos al retornar. Ver como le metimos 506 chars que manejan lo suficiente para pasarse de ese buffer pero no tanto para romper todo.

Tenemos este payload que queremos ejecutar para atacar la shell:

![](../../.gitbook/assets/imagen%20%28384%29.png)

Los x90 son espacios de memoria que dicen movete a la derecha basicamente

![](../../.gitbook/assets/imagen%20%28383%29.png)

![](../../.gitbook/assets/imagen%20%28392%29.png)

Ademas el calcula cuanto se tiene que mover con estos agregados le da 425 

![](../../.gitbook/assets/imagen%20%28391%29.png)

Viendo la memoria con el compilador tenemos lo siguiente:

![](../../.gitbook/assets/imagen%20%28390%29.png)

Como es intel la lees al revez, pero lo clave es ver todos esos 0x90 que se repiten, elegimos uno que no es nuestro.

![](../../.gitbook/assets/imagen%20%28388%29.png)



