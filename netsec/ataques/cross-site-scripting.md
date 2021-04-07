# Cross-site scripting XSS

Same origin policy: evita que una pagina lea o envie información de una pagina a la otra

![](../../.gitbook/assets/imagen%20%2888%29.png)

Se verifica antes de enviar información de un sitio al otro que:

* Puerto
* Host
* Protocolo

Sean iguales para distintos origenes.

Por ejemplo:

![](../../.gitbook/assets/imagen%20%2889%29.png)

De aqui no permite que se leean ni escriban entre ellos pues no cumple la politica para el punto dos, host \(si para protocolo y puerto que es el 80\)

Ahora pensemos algo aparte; si yo controlase el js de cada pagina que vistio. Tendria control total de la informacion,esquivaria el SOP, basicamente podria robar informacion que se usa en las paginas todo controlando el js

![](../../.gitbook/assets/imagen%20%2896%29.png)

El problema: **Insertar JS en una pagina**

El caso mas sencillo es un imput para texto

![](../../.gitbook/assets/imagen%20%2880%29.png)

Luego de procesado el nombre se realiza lo siguiente:

![](../../.gitbook/assets/imagen%20%2878%29.png)

Ahora, que pasa si no insertamos un texto, que pasa si inserto un poco de js

![](../../.gitbook/assets/imagen%20%2886%29.png)

Esto se ejecuta y realiza la alerta

## Tipos: 

### Reflected

Es el del ejemplo de arriba, donde vimos que se realiza la alerta al insertarse en codigo de respuesta del servidor.

### Stored

Peor aun pues este se incrusta dentro de la base de datos.

![](../../.gitbook/assets/imagen%20%2884%29.png)

**Que pasaria si lo incrusto en los comentarios de youtube**

![](../../.gitbook/assets/imagen%20%2879%29.png)

## **DOM XSS**

Este xss implica que el imput del usuario cae directamente en codigo malicioso del atacante, donde ejecuta su script de xss

![](../../.gitbook/assets/imagen%20%2894%29.png)

## Mutation

si yo insertase codigo malicioso en el mismo browser podria llevar a darse xss

![](../../.gitbook/assets/imagen%20%2892%29.png)

## Un problema dificil

No es tan simple como eliminar &lt;script&gt; tambien se han de tomar en consideracion los handlers, los sistemas que ocurren detras como gmail que utilizan mucho etiquetas.

![](../../.gitbook/assets/imagen%20%2876%29.png)

Algunas soluciones como limpiar el dom al leer

![](../../.gitbook/assets/imagen%20%2877%29.png)





\*\*\*\*









