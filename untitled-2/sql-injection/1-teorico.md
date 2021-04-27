# 1 - Teorico

Permite introducir codigo sql donde normalmente no estaria permitido y obtener informacion directamente de la base de datos. O modificarla. Es incluso posible escalar esta amenaza a conseguir informacion del servidor.

![](../../.gitbook/assets/imagen%20%28593%29.png)

## Ejemplo aplicacion de compras

![](../../.gitbook/assets/imagen%20%28594%29.png)

Releleased es un atributo interno dentro de la aplicacion.

Ahora si un atacante modificase el codigo de la uri para agregar un comentario y este input no es sanitizado ocurre lo siguiente

![](../../.gitbook/assets/imagen%20%28591%29.png)

Comenta el codigo y revela informacion de objetos sin release.

### Agregando una condicion para obtener todo

![](../../.gitbook/assets/imagen%20%28592%29.png)

