# 6 - Editando archivos

Para crear un archivo ya vimos el comando **echo "hola" &gt; texto.txt**

Esto no nos permite editar uno existente. Si repetimos el comando con **echo "hola 2" &gt; texto.txt** y lo leemos con cat texto.txt dice solo "hola2"

Ahora lo ideal es poner **echo "hola3" &gt; &gt; texto.txt**

Eso hace que al usar cat texto.txt veamos en dos lineas separadas nuestro "hola2" y "hola3"

Luego cuenta los distintos editores **nano** por ejemplo.

