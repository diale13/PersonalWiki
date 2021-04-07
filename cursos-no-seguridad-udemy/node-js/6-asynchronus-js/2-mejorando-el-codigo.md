# 2 - Mejorando el codigo?



```javascript
console.log("before");
const user = getUSer(1);
console.log(user);
console.log("after");

function getUser(id){
setTimeout(() => {
    console.log("reading from db");
    return {id: id, gitHubUser: "diale13"}
    }, 2000);
}
```

Ahora ESTO NO ANDA. Al hacer el log del user da undefined. Esto se debe aque el codigo SIGUE EJECUTANDO el log antes y luego recien llamando a la funcion.

Para tratar con esto veremos

Callbacks, Promises, Async Await.



