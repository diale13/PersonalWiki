# Lab 7 - SO Memory

![](../../.gitbook/assets/imagen%20%28401%29.png)

## Introduccion

No es solicitado pero para introducir los sistemas paginados comienzan con un marco teorico para los segmentados.

![](../../.gitbook/assets/imagen%20%28406%29.png)

![](../../.gitbook/assets/imagen%20%28404%29.png)

### Que es paginated o paginacion en un sistema operativo?

En la memoria paginada los programas tienen \(para ellos\) toda la memoria disponible para ellos. Esto no es realmente cierto pero el SO les hace creer que si. Lo que ve un programa es la Logical Memory. Cada uno ve una "pagina" de un tamaño fijo.

![](../../.gitbook/assets/imagen%20%28403%29.png)

Como se ve en la figura de arriba el reparto no tiene que ser necesariamente uniforme y se va creando una suerte de memoria fragmentada sumada a la paginada.

![](../../.gitbook/assets/imagen%20%28395%29.png)

_Multiples vistas logicas para las aplicaciones, una page table, y un lugar para hacer el swap a la memoria virtual_

![Paged memory key points](../../.gitbook/assets/imagen%20%28397%29.png)

#### Pagin file en windows

El paging es un overflow para la running memory o para el mismo sistema operativo donde se colocan cosas que no necesariamente tienen que ir a la ram. En windows existe el archivo pagingfile. Es mas lento que la ram pero es mejor que la ram sea saturada.

![](../../.gitbook/assets/imagen%20%28398%29.png)

Porque limitar? Hay usuarios que creen que es mejor para utilizar la totalidad de su memoria RAM. Esto hace que sea mucho mas responsive ya que esta todo en la ram. Sigue siendo un poco problematico desactivar este sistema, lo que si es conveniente es mover el paging file a otro disco mas eficiente en caso de conseguir uno mejor que el principal.

#### Cual es mejor?

![](../../.gitbook/assets/imagen%20%28408%29.png)

### Virtual memory?

Es una tecnica de manejo de memoria que combina elementos de hardware y software. Consiste en "hacerle creer" a la aplicacion que va utilizar espacio de memoria contiguo mientras que en la realidad es dividio en distintos elementos de memoria fisica, incluidos el disco duro que puede ser usado en algunas situaciones en lugar de la ram \(a un costo de eficiencia\).

### Shared memory?

Es un tipo de memoria que quizas deba ser accedida por multiples programas con el fin de evitar copias redundates o como forma de comunicarlos. Es una forma muy eficiente de pasar informacion entre  los programas que quizas no esten corriendo en el mismo procesador u entorno. Tambien puede comunicar elementos en distintos threads.

![](../../.gitbook/assets/imagen%20%28399%29.png)



### Que es un driver de un dispositivo?

Un driver es un programa que permite al sistema operativo interactuar con un periferico haciendo una absteraccion del hardware y bridnando una api para usar el dispositivo.

![](../../.gitbook/assets/imagen%20%28396%29.png)

### Que es IOCTL?

 **ioctl** es una llamada de sistema en Unix que permite a una aplicación controlar o comunicarse con un [driver](https://es.wikipedia.org/wiki/Driver) de dispositivo, fuera de los usuales read/write de datos.

Una llamada **ioctl** toma como parámetros:

1. Un descriptor de archivos abierto
2. Un número de código de requerimiento
3. También un valor entero, posiblemente sin signo \(va al driver\), o un puntero a datos \(también va al driver y vuelve de él\)

### Que es un thread?

Es un hilo de ejecucion.

### Que es un proceso?

Son las instancias de funciones o programas **que estan corriendo en el momento** por lo que ocupan un lugar en la memoria.



### Analiza y describe como se comunican los componentes en el diagrama

![](../../.gitbook/assets/imagen%20%28407%29.png)



La figura de arriba es la estructura de los procesos en Windows.

El proceso contiene:

* **El código fuente del programa \(binario ejecutable\)** y datos adicionales para ejecutar el código en el proceso.
* **Espacio de direcciones virtual privado** que es un conjunto de direcciones de memoria virtual que se utilizan por código dentro de un proceso.
* **El token principal** es el objeto que contiene el contexto de seguridad del proceso utilizado por los subprocesos que ejecutan código dentro del proceso. Identifica a un usuario, grupos de seguridad, privilegios, atributos, estado de virtualización de Control de cuentas de usuario \(UAC\), sesión y estado de cuenta de usuario restringido asociado con un proceso, y la ID de AppContainer y su información de espacio aislado.
* **Tabla de control privada** : se utiliza para administrar objetos ejecutables como eventos, semáforos y archivos.
* **Uno o más subprocesos de ejecución** : un proceso de modo de usuario normal se crea con un subproceso \(ejecutando la función clásica principal / WinMain\). Un proceso en modo de usuario sin subprocesos es casi inútil y normalmente el kernel lo mata.

{% embed url="https://annaevanse.blogspot.com/2019/05/windows\_26.html?m=1" %}

## Volatility

{% embed url="https://www.youtube.com/watch?v=4lURQHslmMc&t=234s" %}



### Que es volatility?

Volatility es un framework para la extraccion de artefactos digitales desde la memoria volatil \(RAM\). Introduce a la gente al area de forense. 

### Instalar volatility en kali

Lo bajas de la pagina oficial [https://www.volatilityfoundation.org/](https://www.volatilityfoundation.org/)

Cambias el nombre del archivo con icono de ruedita por comodidad y lo ejecutas 

```text
./volatility -h
```

Como obtener el perfil de la imagen a analizar con volatility? \(ej Win7SPX64\)

```text
./volatility -f imagenAnalizar.vmem  imageinfo
```

### Como obtener procesos en volatility

![](../../.gitbook/assets/imagen%20%28434%29.png)



```text
volatility -f imagenAnalizar.vmem --profile=WinXPSP2x86 pslist
```

![](../../.gitbook/assets/imagen%20%28426%29.png)

Este trata de ver los procesos ocutltos:

```text
volatility -f imagenAnalizar.vmem --profile=WinXPSP2x86 psxview
```

### Como obtener conexiones de red de volatility?

![](../../.gitbook/assets/imagen%20%28439%29.png)

```text
volatility -f imagenAnalizar.vmem --profile=WinXPSP2x86 connscan
```

## Ejercicio

Seguir CTF resuelto para estudiar volatility

{% embed url="https://cyb3rbl0g.github.io/otterctf-memory-forensic/" %}



