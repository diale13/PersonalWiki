# 5 - Object ID

![](../../../.gitbook/assets/imagen%20%28646%29.png)

### Creando id unica

![](../../../.gitbook/assets/imagen%20%28643%29.png)

Como el tiempo esta ligado a la id podemos ordenar elementos por tiempo usando solamente la id

![](../../../.gitbook/assets/imagen%20%28641%29.png)

![](../../../.gitbook/assets/imagen%20%28647%29.png)

### Validando las id

Toda id puede ser validada para que sea algo real y no solo 1234.

Para esto se hace dentro de la funcion validate que teniamos antes un metodo con joi:

![Luego valida la ide de la movie abajo](../../../.gitbook/assets/imagen%20%28644%29.png)

Pero para que esto sea posible hay que importarlo arriba:

![](../../../.gitbook/assets/imagen%20%28642%29.png)

Ahora probablemente querramos usar eso en otros lugares de validacion. Asi que es aconsejado mover ese require/joi-objectid\) al index:

![](../../../.gitbook/assets/imagen%20%28645%29.png)

