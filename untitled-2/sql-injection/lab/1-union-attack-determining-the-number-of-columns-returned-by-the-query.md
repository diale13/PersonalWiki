# 1 - UNION attack, determining the number of columns returned by the query

 Vemos como el parametro category es el query param que es modificado al realizar el movimiento entre categorias. 

Si ponemos el codigo`'+UNION+SELECT+NULL--` tras la peticion del parametro en nuestro burp nos da error. 

Esto marca que estan faltando parametros en nuestra peticion

![](../../../.gitbook/assets/imagen%20%28591%29.png)

Al editar nos queda asi y capturamos la flag o el lab

![](../../../.gitbook/assets/imagen%20%28601%29.png)

