---
description: Se trata de modos de cifrado
---

# Modos de uso: Electronic Code Book \(ECB\)

![](../.gitbook/assets/imagen%20%2817%29.png)

Agarramos el texto a cifrar, lo convertimos en bloques de misma longitud y lo exponemos a cifrados puntuales. Es super eficiente porque podes implementar versiones con varios hilos de esto, donde se enivan bloques a descifrar para cada nucleo de procesador.



Ahora parece super bueno pero la verdad es que no es nada seguro, el problema es que si dos mensajes son iguales, por ejemplo yo te envio dos veces la misma cantidad de plata, es muy simple analizar el output y ver que son efectivamente el mismo, o varias request http al mismo sitio.



![](../.gitbook/assets/imagen%20%2842%29.png)

![Aca se ve claro el problema de usar ECB, se ve claro en el trafico](../.gitbook/assets/imagen%20%2818%29.png)

Ahora necesitamos una mejora, pero el problema de ECB es que usa la misma clave para cada funcion, como mejoramos esto?



Usamos CBS, eso lo puse en la siguiente seccion.

