# 4 - Events module y Clases en Js

![](../../../.gitbook/assets/imagen%20%28144%29.png)

Queremos responder apropiadamente a cada evento. Usaremos este modulo.

![](../../../.gitbook/assets/imagen%20%28163%29.png)

La diferencia de este es que es una clase. El estandar es con mayuscula.

emitter.emmit\(\) -&gt; lanza una señal de que se largo una señal

![](../../../.gitbook/assets/imagen%20%28154%29.png)

## Emit con parametros

![](../../../.gitbook/assets/imagen%20%28166%29.png)

Podes emitir un evento con varios parametros pero es ideal encapsularlo en un objeto para no confundirte

![](../../../.gitbook/assets/imagen%20%28147%29.png)

## Emprolijando eso

Tenemos que mover todo lo de ahi al modulo logger que teniamos antes

![](../../../.gitbook/assets/imagen%20%28155%29.png)

![](../../../.gitbook/assets/imagen%20%28152%29.png)

Esto no anda, esto sucede porque el emmiter que escucha NO ES EL MISMO que el del logger

Para mejorar esto debemos convertir a clase el logger

## Creando una clase

![](../../../.gitbook/assets/imagen%20%28133%29.png)

![](../../../.gitbook/assets/imagen%20%28148%29.png)

![](../../../.gitbook/assets/imagen%20%28137%29.png)

