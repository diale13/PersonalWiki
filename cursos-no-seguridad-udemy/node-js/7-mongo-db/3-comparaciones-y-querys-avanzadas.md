# 3 - Comparaciones y querys avanzadas

## Operadores de comparacion

Moongose trae los siguientes comparadores armados sobre mongodb

![](../../../.gitbook/assets/imagen%20%28494%29.png)

Ejemplo de uso:

![](../../../.gitbook/assets/imagen%20%28490%29.png)

## Operaciones logicos

Si quiero los cursos publicados O los cursos publicados por mosh hacemos lo siguiente:

Primero traemos todo, luego usamos el **or,**  para el mismo pasamos un array como filtro donde le ponemos lo que deseamos

![](../../../.gitbook/assets/imagen%20%28491%29.png)

Poner .count al final cuenta el total tambien.

## Expresiones regulares

![Van ahi](../../../.gitbook/assets/imagen%20%28492%29.png)

## Paginacion

Lo ideal para una api es tenerlo en la url algo asi: /api/courses?pageNumber=2&pageSize=10

Pero de momento vamos a dejarlo harcodeado arriba.

![](../../../.gitbook/assets/imagen%20%28493%29.png)







