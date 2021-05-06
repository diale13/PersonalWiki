# 1 - Handling Rejected Promises

Por ejemplo si se cae mongo lo que ocurre es retornar una rejected promise. Esto no es igual que una excepcion comun por lo que se cae.

![](../../../.gitbook/assets/imagen%20%28684%29.png)

**Ahora es mejor tener eso en un middleware.**

![](../../../.gitbook/assets/imagen%20%28685%29.png)

Ahora para usar eso simplemente lo usamos asi

![](../../../.gitbook/assets/imagen%20%28688%29.png)

Si vemos el orden dde regiistro de app.use el next entra en ese filter.

Luego la mueve a middleware nomas.

Ahora el tema es que sigue repitiendo el codigo de catch en TODAS las rutas. Un bajonete.

## Creando un handler

Estaria genial hacer lo siguiente

![](../../../.gitbook/assets/imagen%20%28687%29.png)

Ver como todas las rutas tendrian ese catch si las pusieramos en el lugar del handler. Ahora el problema es que no  tiene las req, res apropiadas.

![](../../../.gitbook/assets/imagen%20%28683%29.png)

No se porque funciona esto asi, magia de express y async pero asi se hace un catch middleware asi que vos lo copias y listori. Claramente se mueve a otra carpeta para reusar.





