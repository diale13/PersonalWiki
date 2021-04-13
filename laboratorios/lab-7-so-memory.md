# Lab 7 - SO Memory

![](../.gitbook/assets/imagen%20%28398%29.png)

## Introduccion

No es solicitado pero para introducir los sistemas paginados comienzan con un marco teorico para los segmentados.

![](../.gitbook/assets/imagen%20%28402%29.png)

![](../.gitbook/assets/imagen%20%28401%29.png)

### Que es pagin o paginacion en un sistema operativo?

En la memoria paginada los programas tienen \(para ellos\) toda la memoria disponible para ellos. Esto no es realmente cierto pero el SO les hace creer que si. Lo que ve un programa es la Logical Memory. Cada uno ve una "pagina" de un tamaño fijo.

![](../.gitbook/assets/imagen%20%28400%29.png)

Como se ve en la figura de arriba el reparto no tiene que ser necesariamente uniforme y se va creando una suerte de memoria fragmentada sumada a la paginada.

![](../.gitbook/assets/imagen%20%28395%29.png)

_Multiples vistas logicas para las aplicaciones, una page table, y un lugar para hacer el swap a la memoria virtual_

![Paged memory key points](../.gitbook/assets/imagen%20%28396%29.png)

#### Pagin file en windows

El paging es un overflow para la running memory o para el mismo sistema operativo donde se colocan cosas que no necesariamente tienen que ir a la ram. En windows existe el archivo pagingfile. Es mas lento que la ram pero es mejor que la ram sea saturada.

![](../.gitbook/assets/imagen%20%28397%29.png)

Porque limitar? Hay usuarios que creen que es mejor para utilizar la totalidad de su memoria RAM. Esto hace que sea mucho mas responsive ya que esta todo en la ram. Sigue siendo un poco problematico desactivar este sistema, lo que si es conveniente es mover el paging file a otro disco mas eficiente en caso de conseguir uno mejor que el principal.









* Virtual memory?



* Shared memory?



* Que es un driver de un dispositivo?



* Que es IOCTL?



* Que es un thread?



### Que es un proceso?

Son las instancias de funciones o programas **que estan corriendo en el momento** por lo que ocupan un lugar en la memoria.



* Analiza y describe como se comunican los componentes en el diagrama

![](../.gitbook/assets/imagen%20%28403%29.png)

## Volatility

* Que es volatility?
* Instalar volatility en kali
* Como obtener el perfil de l aimagen a analizar con volatility? \(ej Win7SPX64\)
* Como obtener procesos en volatility
* Como obtener conexiones de red de volatility?

## Ejercicio

Seguir CTF resuelto para estudiar volatility

{% embed url="https://cyb3rbl0g.github.io/otterctf-memory-forensic/" %}



