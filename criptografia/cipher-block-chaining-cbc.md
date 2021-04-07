# Cipher Block Chaining \(CBC\)

Basicamente lo que se hace es una mejora de ECB, se linkean los resultados y se vuelve mas dificil de obtener resultados iguales significativos.

![](https://lh6.googleusercontent.com/JOy4xYzP7se-qBcBuxZto88F9BUW_sxXjBq1Bs466wMBsvu1ftI1gzCjHJgbC3jwYjC1e7gjBdBndH37LIMQKi9ameePhnDCNz_4BjWx-oQeR_DYy2sOG5HIGggp6olYT3VG9x7I)



![](https://lh6.googleusercontent.com/QqaPBbbi4f013qvstrKo_8Sh-beh59tIADFPK4wZ0H1SNRkJvLqs-Nwj8-Lv_gt1XQSPUTDPD5PIqAHUcwiQWkkwEZPXakooupgYIxQ0a9Y32tUL0KqlHfMCTEluzyo-T1DglKUY)

Lo que es el IV o vector de inicializacion es un vector \(dha\) que evita el que dos mensajes 0 sean iguales, maximizando la encriptacion.



El desifrado es el proceso inverso, se puede ver como el Ci de la foto de arriba.



## Problemas: 

Es bastante lento, no podes descifrar hasta haber obtenido todos los anteriores, algo que en el streaming es mortal si queres adelantar.

Es vulnerable a un ataque, si yo cambio algo del mensaje 2 por ejmplo tiene impacto sobre el mensaje 3. 



