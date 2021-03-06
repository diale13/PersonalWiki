# 1 - Linux

## Variables de entorno

### Visualizar variables de entorno

Las variables de entorno son valores dinámicos que afectan los programas o procesos que se ejecutan en un servidor. Existen en todos los sistemas operativos y su tipo puede variar. Las variables de entorno se pueden crear, editar, guardar y eliminar.

En Linux, las variables de entorno son marcadores de posición para la información almacenada dentro del sistema que pasa datos a los programas iniciados en shells \(intérpretes de comando\) o sub-shells.

```text
printenv | less
env //tambien funciona
```

![](../../../.gitbook/assets/imagen%20%28265%29.png)

Para crear una, verla y luego borrarla

```text
VARNAME=value123
echo $VARNAME
unset VARNAME
```

![](../../../.gitbook/assets/imagen%20%28270%29.png)

Below are some of the most common environment variables:

* `USER` - The current logged in user.
* `HOME` - The home directory of the current user.
* `EDITOR` - The default file editor to be used. This is the editor that will be used when you type `edit` in your terminal.
* `SHELL` - The path of the current user’s shell, such as bash or zsh.
* `LOGNAME` - The name of the current user.
* `PATH` - A list of directories to be searched when executing commands. When you run a command the system will search those directories in this order and use the first found executable.
* `LANG` - The current locales settings.
* `TERM` - The current terminal emulation.
* `MAIL` - Location of where the current user’s mail is stored.

### Visualizar las variables de entorno de forma completa y filtrar por BASH\_ALIAS

Para filtrar un resultado usariamos **grep.** No se a que se refiere con bash\_alias sino. Usar **typeset** muestra las variables de bash.

### Incluye el path al ejecutable masscan como variable de entorno temporal

Para agregar un PATH usaremos el comando **export**. Una ruta path tiene la forma de _/some/new/path_ pero debemos de cuidar la variable path ya existente entonces podemos copiarla asi 

```text
export PATH=/some/new/path:$PATH
```

O poner algo al final

```text
export PATH=$PATH:/some/new/path
```

### Haciendolo persistente

De la forma anterior no se mantiene al reiniciar el equipo

#### LOCALMENTE

Para persistir nuestros cambios para el usuario debemos agregar lo que exportemos al final de _**~/.profile**_ ****en caso de que no exista lo creamos

```text
touch ~/.profile
```

Additionally, we need to open a new shell or source our _~/.profile_ file to reflect the change. We’d either execute:

```text
. ~/.profile
```

#### GLOBALMENTE AL SISTEMA

Para agregarlo al sistema de forma global creamos un .sh en  ****_**/etc/profile.d/**_ y agregamos nuestro comando export a este archivo.

TODOS LOS SCRIPTS EN   ****_**/etc/profile.d/**_  SE EJECUTAN CUANDO INICIALIZA SHELL. 

### Cambiar prompt shell a "World best hacker"

```text
#echo $PS1
```

![](../../../.gitbook/assets/imagen%20%28267%29.png)

![](../../../.gitbook/assets/imagen%20%28278%29.png)

Haremos un backup de la original

```text
#PS_ORG="$PS1"
#PS1="WORLD BEST HACKER "
```

![](../../../.gitbook/assets/imagen%20%28273%29.png)

```text
WORLD BEST HACKER PS1 = $PS1_ORG
```

## Bash Script

Descargamos **metasploitable** y nos aseguramos que este correctamente levantada haciendo ping desde la virutal machine de kali.

### Realiza un script que permita tomar los puertos a escanear

```text
//Suponiendo ports.txt
$ cat ports.txt | sed -e "s/:/ /" | while read ip port
    do
    nmap -T4 -p $port -oN $ip 'nmap'$port  
    done
```

**Recordar**

```text
sed - is a stream editor for filtering and transforming text
sed -e script, --expression=script
add the script to the commands to be executed
```

###  Scan a la direccion ip de Metasploitable y envia a un archivo grepable

```text
$ nmap -sS 10.0.2.16 -p- -oG outScript -T4
```

### Fuera de eso filtrar salida a puerto 80

```text
$ cat outScript | grep 80/open > grepPort.txt
```

### Cuenta puertos abiertos con grep y awk

**NO ES MIO LO SIGUIENTE DEBO CORRELO AUN**

![](../../../.gitbook/assets/imagen%20%2899%29.png)

### Comprimir salida a tar

```text
$ tar -czvf grep.tar.gz ./
```

### Script de eso

```text
//Suponiendo ports.txt
$ cat ports.txt | sed -e "s/:/ /" | while read ip port
    do
    nmap -T4 -p $port -oN $ip 'nmap'$port  
    done

    nmap -sS 10.0.2.16 -p- -oG outScript -T4
    $ cat outScript | grep 80/open > grepPort.txt
    tar -czvf outputed.tar.gz ./ 
```

## Storage device management

### Listar particiones

```text
$ df -h  
```

**Fun fact**: la h es de human, ya que listarlo asi es mas legible por uno.

Conectar usb 

### Crear directorio para usb

```text
$ mkdir /media/usb
```

### Identificar nombre de unidad

```text
$ ls -l /dev/sd*
```

### Montar unidad

```text
$ mount -t vfat /dev/sdb1 /media/usb -o [securityoption]
```

> The security option is mandatory and allows you to give/gain access to the USB by specifying one of the following values for permission;
>
> _uid=1000_
>
> _gid=1000_
>
> _Utf8_
>
> _dmask=027_
>
> _fmask=137_

_Yo use uid=1000_

### Validar espacio disponible 

```text
$ df -h  
```

### Desmontar unidad

```text
$ umount /media/usb 
```

## Logging

### ¿Que es rsyslog?

Es una herramienta de codigo abierto para los sistemas UNIX que se encarga de enviar los logs en una red ip. Implementa un protocolo llamado syslog. Facilmente configurable con propiedades de filtrado que corre sobre TCP.

> "The **r**ocket-fast **sys**tem for **log** processing" - RSYSLOG website

###  Donde se encuentra el archivo de configuración de rsyslog?

```text
$ /etc/rsyslog.conf
```

### Que es logrotate?

Al ser administrador de linux manejas un monton de logs. 

-Os

 -Servidores \(como Nginx\)

-Logs de base de datos 

-App

Un monton de logs de un monton de fuentes. Logrotate ayuda a manejar la cantidad de lgos. Rota los logs. Esto es crear nuevas carpetas y mueve, comprime o remueve los logs viejos.

{% embed url="https://www.youtube.com/watch?v=0U2RMbzKUCY" %}

### Intentar hacer sudo con un usuario que no este en sudoers

No pasa.

### Ingresa mal la contraseña de un user que este en sudoers

Marca error 

### Donde se almacenan los log?

Se almacenan en **/var/log**

### **Ver log de bad login**

```text
$ sudo grep "Failed password" /var/log/auth.log | head -3
```

## Transferencia de archivos

Crea un archivo en kali

```text
$ touch test.txt
```

 Transfiere el archivo mediante scp a Metasploitable

```text
$ scp ./test.txt msfadmin@10.0.2.16:/home/msfadmin
```

Transfiere el archivo mediante FTP a Metasploitable

```text
$ ftp 10.0.2.16
$ msfadmin
$ put test.txt 
```

>

