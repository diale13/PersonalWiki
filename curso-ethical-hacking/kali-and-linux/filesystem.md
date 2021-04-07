# 1 - Filesystem

## Overview

![](../../.gitbook/assets/imagen%20%28101%29.png)

Cambiamos directorio con cd, poner cd / nos lleva a home.

Luego tenemos los directorios en si.

### /Bin

Contiene binarios, estos son los que ejecutamos desde la consola, el mismo ls que lista los conenidos es uno. Usar vim por ejemplo llama a lo contenido en esta carpeta

### /Sbin

Contiene binarios del sistema, solo usables por root. 

### /Lib

Son liberias comunes usadas por los binarios

### /Usr and /Usr/bin

Son binarios no clave del sistema, pensados para el usuario final.

### echo $PATH

La variable del sistema path mapea todos los binarios ejecutables

### /ETC

ETC = Editable Text Configuration: son aquellos archivos que podemos modificar para customizar nuestro sistema.

### /Home

Contiene dentro de el mismo los archivos de cada usuario, separados entre sus carpetas

### /Boot

Archivos necesarios para bootear el sistema, incluido el kernell de linux

### /Dev

Son los device files, como elementos externos

### /Opt

Optional software, muy raro interactuar

### /Var

Elementos variables como log files

### /Temp

Temporary files que no se persisten al reiniciar

## Curso

Print working directory -&gt; imprime directorio actual

```text
pwd
```

ls muestra el  contenido de la carpeta, tambien podes lanzarlo sin entrar a la misma

```text
ls  /Desktop
```

```text
ls -la
```

![](../../.gitbook/assets/imagen%20%28103%29.png)

Muestra directoiros ocultos, se muestran con color especial







