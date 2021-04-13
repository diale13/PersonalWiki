# Lab 6 - BufferOverflow

## Entendiendo la memoria \(linux\)

![](../.gitbook/assets/imagen%20%28376%29.png)

* **Kernel:** variables de ambiente u elementos de parametros para la terminal
* **Text:** codigo de un programa, lo que compilamos \(read only\)
* **Data**: variables sin inicializar y las inicializadas
* **Heap**: area muy grande donde se agregan lo que va necesitando el programa. Lo mas grande de esto.
* **Stack:** variables locales y funciones. El stack tiene tamaño fijo.

```text
static int i = 1 //Se guarda en el data
```

**Bss:** Uninitialized data segment often called the “bss” segment, named after an ancient assembler operator that stood for “block started by symbol.” Data in this segment is initialized by the kernel to arithmetic 0 before the program starts executing

![](../.gitbook/assets/imagen%20%28394%29.png)

Del stack sale el stackoverflow, y tambien los ataques a buffer suelen ir para ahi.

![](../.gitbook/assets/imagen%20%28366%29.png)

![](../.gitbook/assets/imagen%20%28386%29.png)

Vemos que el stack crece hacia esa direccion, los parametros que agregamos se ponen en esa direccion.

### Windows

1. Memory Management in Windows uses Tree data structure and Linux uses Linked List data structure.
2. Windows uses Cluster demand Paging where the pages are bought only when they are needed but simultaneously. Linux uses Demand paging where the pages will not be swapped from disk to RAM until they are needed.
3. Page Replacement Algorithm that is used in Windows is First In First Out\(F.I.F.O\) where as Linux uses Least Recently Used\(L.R.U\) Algorithm.
4. Windows on 32-bit uses 4GB of physical memory which allows each process to have its own 4GB logical address \(upper 2Gb-Kernel Mode, lower 2Gb-User Mode\). In regard to Linux, 3Gb-User mode & 1Gb-Kernel Mode.

![](../.gitbook/assets/imagen%20%28395%29.png)

## Buffer overflow

Es un tipo de ataque donde mediante un código por ejemplo en c, escribimos algo que supera el largo del bloque de memoria intencionado. Por lo que nos vamos a otro bloque.

Los ejecutables son mantenidos en memoria.

Ahora vamos a atacar:

![](../.gitbook/assets/imagen%20%28389%29.png)

Lo que hace es crear un buffer de 500 caracteres y colocar el parametro\(s\) de char en el mismo

Asi queda nuestra memoria:

![](../.gitbook/assets/imagen%20%28385%29.png)

El base pointer no importa mucho pero el return es el valor de la variable que retornaremos y/o ejecutaremos. Lo que queremos lograr es pasarnos por completo del buffer y ejecutar en el return lo que nosotros querramos.

Usaremos el compilador **gdb**

**C**orriendo eso con ayuda de un script de python no solo asigna los valores sino que se pasa

![](../.gitbook/assets/imagen%20%28387%29.png)

Obtenemos entonces un segmentation fault. Eso es bueno implica que linux se dio cuenta que tocamos algo que no deberiamos al retornar. Ver como le metimos 506 chars que manejan lo suficiente para pasarse de ese buffer pero no tanto para romper todo.

Tenemos este payload que queremos ejecutar para atacar la shell:

![](../.gitbook/assets/imagen%20%28384%29.png)

Los x90 son espacios de memoria que dicen movete a la derecha basicamente

![](../.gitbook/assets/imagen%20%28383%29.png)

![](../.gitbook/assets/imagen%20%28392%29.png)

Ademas el calcula cuanto se tiene que mover con estos agregados le da 425 

![](../.gitbook/assets/imagen%20%28391%29.png)

Viendo la memoria con el compilador tenemos lo siguiente:

![](../.gitbook/assets/imagen%20%28390%29.png)

Como es intel la lees al revez, pero lo clave es ver todos esos 0x90 que se repiten, elegimos uno que no es nuestro.

![](../.gitbook/assets/imagen%20%28388%29.png)



## Memory corruption

Memory corruption occurs in a computer program when the contents of a memory location are modified due to programmatic behavior that exceeds the intention of the original programmer or program/language constructs; this is termed violating memory safety.

* Using uninitialized memory
* Using non-owned memory
* Using memory beyond the memory that was allocated \(buffer overflow\)
* Faulty heap memory management

### 

### Debugger and Dissambler

[**Disassembler**](https://reverseengineering.stackexchange.com/questions/tagged/disassemblers):

> Convierte codigo de maquina en algo legible por un humano

[**Debugger**](https://reverseengineering.stackexchange.com/questions/tagged/debuggers):

> Permite pausar y reanudar la ejecucion de un programa con el fin de analizar su estado.

