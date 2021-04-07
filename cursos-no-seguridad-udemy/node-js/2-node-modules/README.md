# 2- Node modules

En js existe el concepto de global donde todas las var entran ahi y podes hacer global.variable y obtenerlo. Entonces el siguiente codigo funciona ahi pero no en node.

![](../../../.gitbook/assets/imagen%20%28121%29.png)

## Para correr un archivo

```text
$ node app.js 
```

## Modulos

Para trabajar apropiadamente con las variables hemos de crear modulos. Estos contienen dentro de si mismo un scope que maneja las variables, encapsulandolas de forma que no afecten a las de otro modulo.

![](../../../.gitbook/assets/imagen%20%28118%29.png)

![](../../../.gitbook/assets/imagen%20%28125%29.png)

## Accediendo a modulos externos

Supongamos que fuera de nuestro modulo principal creamos un modulo de logs.

![](../../../.gitbook/assets/imagen%20%28119%29.png)

Ahora para acceder al mismo desde la app.js debemos modificar la configuracion

![Aqui vemos que elementos son exportados](../../../.gitbook/assets/imagen%20%28120%29.png)

Para exportar elementos

![](../../../.gitbook/assets/imagen%20%28124%29.png)

En app debemos requerirla. 

Nota adicional despues cambia las **var** a **const** para no redefinirla.

![](../../../.gitbook/assets/imagen%20%28130%29.png)

De ser requerida veremos lo siguiente desde la consola

![](../../../.gitbook/assets/imagen%20%28129%29.png)

## Manejo de errores

![](../../../.gitbook/assets/imagen%20%28127%29.png)

Lanzando Jshint te dic e que puede estar mal

## En tiempo de ejecucion

![](../../../.gitbook/assets/imagen%20%28139%29.png)

Node no ejecuta nuestro codigo asi nomas, lo convierte a una funcion como aparece en la foto de arriba.





