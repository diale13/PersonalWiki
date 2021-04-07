# 1 - Sync y Async

Haremos un proyecto nuevo para explicar codigo de js asincronico.

```javascript
console.log("before");
console.log("after");
```

Recordar esto ocurre simpre before y after.

Simulemos entonces una llamada en el medio, supongamos una llamada a la base de datos que dura 2 segundos.

```javascript
console.log("before");
setTimeout(() => {
    console.log("reading from db")
    }, 2000);
console.log("after");
```

![](../../../.gitbook/assets/imagen%20%28277%29.png)

Aqui suceden muchas cosas interesantes. Lo primero es que before y after actuan primero SIN ESPERAR y luego recien de la ejecucion SE EJECUTA EL TIMEOUT. Es decir ni siquiera se pone a esperarlo



