# 1 - Linux

## Variables de entorno

### Visualizar variables de entorno

Las variables de entorno son valores dinámicos que afectan los programas o procesos que se ejecutan en un servidor. Existen en todos los sistemas operativos y su tipo puede variar. Las variables de entorno se pueden crear, editar, guardar y eliminar.

En Linux, las variables de entorno son marcadores de posición para la información almacenada dentro del sistema que pasa datos a los programas iniciados en shells \(intérpretes de comando\) o sub-shells.

```text
printenv | less
env //tambien funciona
```

![](../../.gitbook/assets/imagen%20%28265%29.png)

Para crear una, verla y luego borrarla

```text
VARNAME=value123
echo $VARNAME
unset VARNAME
```

![](../../.gitbook/assets/imagen%20%28270%29.png)

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

![](../../.gitbook/assets/imagen%20%28267%29.png)

![](../../.gitbook/assets/imagen%20%28278%29.png)

Haremos un backup de la original

```text
#PS_ORG="$PS1"
#PS1="WORLD BEST HACKER "
```

![](../../.gitbook/assets/imagen%20%28273%29.png)

```text
WORLD BEST HACKER PS1 = $PS1_ORG
```

## Bash Script





### 



