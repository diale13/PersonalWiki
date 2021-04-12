---
description: 'https://www.youtube.com/watch?v=1S0aBV-Waeo'
---

# Buffer Overflow Attack

### Entendiendo la memoria \(linux\)

![](../../.gitbook/assets/imagen%20%28376%29.png)

* **Kernel:** variables de ambiente u elementos de parametros para la terminal
* **Text:** codigo de un programa, lo que compilamos
* **Data**: variables sin inicializar y las inicializadas
* **Heap**: area muy grande donde se agregan lo que va necesitando el programa. Lo mas grande de esto.
* **Stack:** variables locales y funciones

Del stack sale el stackoverflow, y tambien los ataques a buffer suelen ir para ahi.

![](../../.gitbook/assets/imagen%20%28366%29.png)

Vemos que el stack crece hacia esa direccion



