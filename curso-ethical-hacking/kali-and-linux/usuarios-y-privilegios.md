# 3 - Usuarios y privilegios

## Permisos

![](../../.gitbook/assets/imagen%20%28104%29.png)

Como ves a la izquierda hay varios grupos de letras separados por guiones

* **r-read**
* **w-write**
* **x-execution**

Eso implica que el owner tiene esos privilegios. Luego lo segundo son los que pertenecen al mismo grupo de usuarios que el owner.

La carpeta **temp** suele tener esos permisos de facil acceso

![](../../.gitbook/assets/imagen%20%28105%29.png)

Si queremos poner una vulnerabilidad la solemos tirar ahi.



Por defecto al crear un archivo \(un txt por ejemplo\) solo viene con permisos de r w. Si queremos escalar eso debemos usar **changemode** -&gt; chmod 777 hello.txt

Eso da permisos totales de rwx al archivo.

## Usuarios

Ahora si queremos crear un usuario usamos **adduser** nombre. El usuario lo podemos ver en la carpeta **etc/password**, la carpeta en si no da las contraseñas. Las contraseñas estan en **etc/shaddow**.

En shaddow estan las contraseñas haasehadas, podes intentar usar hashcat para resolverlas.

**su** jhon -&gt; para cambiar el usuario a jhon

Si sos root no pide nada, sino pide contraseña.

No es tan simple como tirar sudo. Se ha de encontrar el usuario dentro de la carpeta sudoers.









\*\*\*\*

\*\*\*\*

