# 9 - Netmon

![](../../.gitbook/assets/imagen%20%28590%29.png)

Estudiando un poco esto vemos que el fpt **con login anonimo** nos coloca directamente en el **disco c** lo cual no deberia suceder.

Luego tiene el puerto 80 abierto.

Se llama netmon por lo que tiene levantado en el puerto 80.

* Ftp abierto y un servidor ejecutando no es un buen combo ya que potencialmente lo que puede suceder es ejecutarlo desde el servidor.

### Buscando default credentials

![](../../.gitbook/assets/imagen%20%28701%29.png)

\*no hubo suerte

Remote code execution

![](../../.gitbook/assets/imagen%20%28695%29.png)

El problema es que necesitamos estar logeados para ejecutarlo. Viendo un poco las carpetas disponibles desde fpt encontramos aplication data que es donde la documentacion indica que puede haber credenciales.

![](../../.gitbook/assets/imagen%20%28707%29.png)

Parecia como que no pero:

![](../../.gitbook/assets/imagen%20%28702%29.png)

En PRTG podriamos ver configuraciones, por eso hacemos un get y luego lo estudiamos

![](../../.gitbook/assets/imagen%20%28709%29.png)

![](../../.gitbook/assets/imagen%20%28697%29.png)

Esa pass que esta ahi esta encriptada, probemos el bak que conseguimos

![Ahi esta la contrase&#xF1;a](../../.gitbook/assets/imagen%20%28705%29.png)

Ahora si probamos esa no funciona...pero cambiandole el ultimo digito a 9 por el año 2019 si. Tema de password reuse

### Recordar el script:

![](../../.gitbook/assets/imagen%20%28696%29.png)

Necesitaba una cookie

Lo copiamos en nuestra maquina, le ponemos la cookie por parametro

![](../../.gitbook/assets/imagen%20%28698%29.png)



{% embed url="https://github.com/SecureAuthCorp/impacket" %}

![](../../.gitbook/assets/imagen%20%28694%29.png)

Con eso ya llega a ser admin. Las credenciales esas son las subidas con el sh anterior.

