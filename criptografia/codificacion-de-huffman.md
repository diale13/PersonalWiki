# Codificación de Huffman

Cada letra refiere a un conjunto de 8 bits, desde el comienzo del almacenado de las mismas esta el problema de querer guardar la menor cantidad de los mismos. Perder un par de bits en streaming no es el fin del mundo pero para el texto puede significar algo grave.  


Sin el decir que cada carácter ocupa exactamente 8 bits no es posible que la computadora distinga bien entre los mismos, ademas el tenerlos con una distancia fija es super sencillo buscar entre letras.  


Si se busca una codificación donde el espacio sea un 0, la e un 1 y la t 01 ocurre lo mismo que vimos arriba donde no sabe qué hacer con un 001 donde no sabe si es “espacio t” o si es “espacio espacio e”.  


La gracia de esta codificación es armar un árbol basado en los caracteres más comunes de un texto dado, a partir del mismo árbol generamos un lenguaje propio para nuestro texto y será mucho más eficiente el guardado del mismo. También guardaremos el árbol como forma de tener nuestra clave de desencriptación.

### Pasos:

1:Contamos la cantidad de veces que aparece cada caracter y lo ponemos en una lista ordenada

![](https://lh4.googleusercontent.com/XpuMYzvG_gyytWOT5g7Otn8HFB4avJOfV7BejAhlbrkVwwZRkd8-sZMjgio0iQwJCTa1HCpM6j7lYdAuqXlf1nVo1lzsXYTzL8l08_-SXbBE2sqJ6PwqsjMmleSFSztMRhgQ5I0M)

Tomamos los dos caracteres menos usados \(en el ejemplo de tom scott son justo 1 y 0 pero son caracteres no int\), y los conectamos como la suma de su frecuencia \(2 en este caso\) Y agregamos esta suma a la lista que habíamos armado.

2:

![](https://lh4.googleusercontent.com/aHvPoVbhaTw4cmgrI23GsZRq9bR2Z2PM0jmF4k3s78EEsHf3uuG8UU7tlt-_lvnWXmdG1hCqG9ZfSuO7Z6Avtr26j5_uq4_F-jgmiHSH9pE4nmgIC7nz-9BOWQsy1pzqVPJmkcU4)

Continuamos haciendo sumas hasta que uno de los arbolitos que armamos llegue al final de la lista que estabamos recocrriendo.

![](https://lh5.googleusercontent.com/f8oISQ0_YiNL25k794Ei-2isKU6_XPjVHN0z2MPYq0l0NfoXydbPwpHMPCmXyptHlbo6P_C9cAmNS8MtVl0ea39oSFnX_GLImkYDNWThHh75LS3ewOA6IMFOfuQhWH-LWMKJRHNQ)

Ahora que llega a este punto donde un arbol coincide con una frecuencia de letras los conectamos y lo mandamos para arriba en la lista, contninuando el algoritmo

![](https://lh6.googleusercontent.com/IhqaVUdRtnnUDJo415HI2puAUbW9wMsIOKIf1Q59wZ5fBp4c6PRY1K9O3xK90nB2jhhWp0MkVqS97i5PaR9eNk3COPs3YLYaLXV3KNlU0raFUBSfQTR9zWBOnokFUc5AJmERBmjj)

Llega a armar el arbol de huffman. A partir de esto armaremos nuestra codificacion

![](https://lh5.googleusercontent.com/KzyGB2x8cgoX59YRVK-2KAccEVRTtRH82q4c1cpHS_57vPlCbdnCPR_jNE92vSzT8yFcLBRKPPdW-DiFgjhw89QHtRBED-zP2Lt8mDigqpJxC9PZk23V4bwfX3WwlPwyjLbBKFux)

Para armar una w tomaremos el camino ese, cada que voy a la drecha \(verde\) va un 1 y cada vez a la izquierda es un 0 \(naranja\)

![](https://lh3.googleusercontent.com/1OTWtvetVBTjMz8D2VjdN0c_5soOXe9uumphv7IwNWBx2HnCOVUFQneYTgWL0-ZdDn1KtA-hjmASLmIpE4m0LQjTHekox4GkY4wEKKXzWHBTAPocEbOTrmjvDfHM8MGSIFQPjQ1L)

Esto nos deja con 5 bits y no 8. Algunas ocuparan más de 8 pero son mucho menos probables

El árbol también ha de guardarse, no siempre es eficiente la traducción pero no importa mucho ya que el tema es ahorrar espacio en textos largos.

Para descomprimir es al revez del árbol. 

Huffman demostró que es la mejor forma de codificar, a menos que se trabaje con bloques de más de un carácter pero esta es la base.

