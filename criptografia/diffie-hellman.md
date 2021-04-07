# Diffie Hellman

En todo lo que mencione dentro del capitulo de critpografia cuando se hace alusion al intercambio de claves publicas no se hace mencion a como se intercambian las mismas de forma segura. Para esto surge el algoritmo Diffie-Hellman desarrollado por estos dos ingeneros.

La siguiente foto es basicamente la guia de como hacerlo, siendo cada color la clave de cada uno, de todos modos elaborare mejor debajo, la foto es para acordarme rapidamente de como era.



![](https://lh3.googleusercontent.com/OjKVxBCT0_gfIef5dBns8o7R4OH3DmwMT76h5uOTaAepm7C9Oje3wkEM_RDTY49dmaPXlSC-0NxPwlWOBiqKBoM5ttriVPop1tmizjgvpgUtafSBGNoal1rfbxBYv1bKt7X-dH45)



## Mas en detalle

Empieza asi:

![](../.gitbook/assets/imagen%20%289%29.png)

La idea no es realmente intercaambiar claves secretas sino mezclar las claves secretas reales con algunas variables publicas para poder generar asi una nueva y segura que sea conocida y manipulable unicamente por alice y bob.

Si un atacante quiere entrometerse solo puede ver la zona publica, de otro modo tiene cosas que ya le permitirian hacer un daño considerable y no tendria sentido el esfuerzo.

a y b son claves privdas que no pueden ser mostradas a nadie. Luego en el area publica ambos acuerdan dos cosas, un gran numero primo n y un generador g, el cual tambien es un numero grande.

![](../.gitbook/assets/imagen%20%2831%29.png)



Luego mezclas el color  a con g y el b con g obteniendo ag y bg. Esos se intercambian, se mezclan con los opuestos \(ahora se ve en la foto\) y listo, se tiene una clave comun a los dos sumamente dificil de separar en base a los secretos que manejan ambos.

![](../.gitbook/assets/imagen%20%2837%29.png)

Ahora con nuestro secreto conjunto podemos manipularlo acrode y usarlo de clave k para cualquier otro algoritmo de clave publica o similar. Lo importante es que abg es sumamente dificil de reproducir para un atacante  quien solo conoce ag y bg.



Ahora el "n" es usado para la parte matematica la cual linkeo aca:

{% embed url="https://www.youtube.com/watch?v=Yjrfm\_oRO0w" %}





