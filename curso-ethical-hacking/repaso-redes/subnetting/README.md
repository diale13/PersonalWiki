# 6 - SubNetting

Aca entra la parte de subredes y asignacion de mascaras para las mismas

![Recordar como una mascara se compone de un octeto binario](../../../.gitbook/assets/imagen%20%2893%29.png)

La cantidaad de hosts se corresponde con los 0 de la ultima parte digamos; prender el bit para el 128 por ejemplo reduce la cantidad de hosts a 2^7

Lasa de las casas suelen ser un /24.

## Trucos para asignacion veloz de subnets

![](../../../.gitbook/assets/imagen%20%2875%29.png)

Vamos sumando los host de forma diagonal acorde a las potencias de dos y nos va dando las subnets

Con esta visualizacion podemos marcar las mascaras

![](../../../.gitbook/assets/imagen%20%2897%29.png)

Lo de arriba corresponde a "8 bits prendidos", lo de la segunda linea 16 etc



### Ejercicio rapido

Si te dicen que tenemos un /27 el sabe que lo ultimo en cruzarse fue el 255.255.255.0; entonces va a la columna del 27 y mira su subnet -&gt; **OBTENEMOS: 255.255.255.224**

**Como complemento brinda la siguiente cheatsheet \(muy facil de hacer ver como se van multiplicando x2\):**

![](../../../.gitbook/assets/imagen%20%2898%29.png)

Ahora supongamos que nos dan a escanear una red:

192.168.1.0/24 -&gt; sabemos por la tabla que tiene \(256**-2**\) hosts \(recordar que se reservan siempre 2\)

192.168.1.0/20 -&gt; sabemos que tiene 4096-2 hosts

Recordando entonces si me dan  192.168.1.0 y mascara 255.255.0.0 los del primer y segundo octeto a la izquierda NO CAMBIAN, los otros si pueden cambiar y seguir en la red

Recordar: viendo la tabla te dice donde poner la subnet \(la x\); luego network es el primer host de la red, brodcast el ultimo /son los reservados



![Ejercicio 2 hecho con la tabla. Dado lo de la izq hacer los de la der](../../../.gitbook/assets/imagen%20%2882%29.png)

Ejemplos un poco mas complejos ya que saltan de octeto:

![](../../../.gitbook/assets/imagen%20%2890%29.png)

## Herramienta

{% embed url="https://ipaddressguide.com/cidr" %}

## Ejercicio Final

![](../../../.gitbook/assets/imagen%20%2895%29.png)





















