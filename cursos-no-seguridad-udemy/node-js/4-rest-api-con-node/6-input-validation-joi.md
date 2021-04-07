# 6 - Input validation - JOI

Para evitar validaciones largas antes de cada objeto usaremos una biblioteca llamada joi

```text
npm i joi
```

En el codigo arriba:

```text
const Joi = require(´joi´)
```

![](../../../.gitbook/assets/imagen%20%28250%29.png)

Queda super sencilla la validacion. De mandar algo mal hecho te dice que esta mal todo validado bien fluent desde **joi**

**Ahora**, para no repetir codigo vamos a extraerlo para futuras funciones

![](../../../.gitbook/assets/imagen%20%28238%29.png)

## Mejorando validacion + Put

![](../../../.gitbook/assets/imagen%20%28253%29.png)

Al usar las llaves extraemos una parte del resultado, es lo mismo que decir resultado.error

