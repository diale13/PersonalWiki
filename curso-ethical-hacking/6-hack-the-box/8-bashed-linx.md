# 8 - Bashed \(linx\)

Tenemos un apache abierto en el 80. Buscamos un **remoto** no un local.

![](../../.gitbook/assets/imagen%20%28576%29.png)

![](../../.gitbook/assets/imagen%20%28580%29.png)

En la pagina no hay mucho, parece un blog de informatica sobre una terminal web, usemos **dirbuster.**  

Con eso encontramos la carpeta dev que contiene una terminal

![](../../.gitbook/assets/imagen%20%28575%29.png)

## Reverse shell para php

{% embed url="https://pentestmonkey.net/tools/web-shells/php-reverse-shell" %}

Lo hosteamos en el simple http de python, se lo subimos.

![](../../.gitbook/assets/imagen%20%28585%29.png)

Ponemos un listener con netcat. Y luego como quedo subido al lado del index.html podemos entrar directo a rev.php la uri.

Tenemos una reverse shell muy bella. Ahora el problema es que llora por un tty. Veamos como escapar de ella. Juan pedro google dice: escape tty shell.

![](../../.gitbook/assets/imagen%20%28583%29.png)

Bien eso funciona, ahora somos un usuario normal pero para escalar el privilegio hacemos esto:

![](../../.gitbook/assets/imagen%20%28586%29.png)

Si no anda  cambiar sin contraseña podemos hacer sudo -u user /bin/bash

Vemos dentro de la carpeta scripts lo siguiente

![](../../.gitbook/assets/imagen%20%28571%29.png)

Parece que hay una tarea programada que se manda a ejecutar como administrador y escribe el contenido de test.py 

Ahora podemos editar eso y poner una reverse shell de python para que ejecute como root y nos de eso.

![](../../.gitbook/assets/imagen%20%28582%29.png)

Al conectarse denuevo se envia una peticion para conectarse al puerto de escucha de arriba asi que ponemos un netcat y pum shell.

