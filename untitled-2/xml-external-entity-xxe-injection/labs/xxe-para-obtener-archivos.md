# XXE para obtener archivos

En esta pagina de productos se puede checkear manualmente el stock de cada producto

![](../../../.gitbook/assets/imagen%20%28613%29.png)

Entonces al ver dentro de burp vemos como es enviada la peticion en formato xml

![](../../../.gitbook/assets/imagen%20%28612%29.png)

Luego de un rato de hacer debug con el xml llego a esto

![](../../../.gitbook/assets/imagen%20%28616%29.png)

Se coloca el &xxe como una forma de hacer referencia a la variable de arriba.



