# 9999 - Para ver terminado eso

{% embed url="https://www.youtube.com/watch?v=vn3tm0quoqE" %}



## About the event loop

{% embed url="https://www.youtube.com/watch?v=8aGhZQkoFbQ" %}



### **¿Qué es event loop?**

 Esto es el runtime de javascript. Es compuesto por un Heap para la memoria y un Stack de ejecución.

![](../../../.gitbook/assets/imagen%20%28353%29.png)

![](../../../.gitbook/assets/imagen%20%28351%29.png)

The call stack: solo tiene un thread == un call stack == una cosa a la vez

![](../../../.gitbook/assets/imagen%20%28354%29.png)

![](../../../.gitbook/assets/imagen%20%28349%29.png)

Luego cuando toca retornar se saca multiply del stack, luego eso para el square y sigue así. Al lanzar un error vemos el callstack. De agregarse muchas cosas al stack se lanza un stackoverflow.

![](../../../.gitbook/assets/imagen%20%28352%29.png)

Al llamar a las sync se va ejecutando a medida que se agregan al stack. Debemos esperar a que se termine. De ejecutar este código SINCRONICO el navegador se cuelga, no podes hacer nada de mientras y no puede ejecutar otras cosas.

La solución? Asyncronus callbacks

![](../../../.gitbook/assets/imagen%20%28355%29.png)

Lo que trate de ilustrar en el dibujo es como va a imprimir: hi, luego JSConfEU y luego recién There, todo eso mostrando en el stack el orden propuesto. La foto es sacada en el momento 2’

![](../../../.gitbook/assets/imagen%20%28356%29.png)

Esto es lo que sucede realmente, se manda a otro thread. Luego lo manda a la task queue para no ponerlas en mal orden denuevo al stack.

 **¿¿Porque lo pondríamos con setTimeout 0??** El eventloop debe esperar a que el stack este liberado pero al hacerlo con tiempo 0 se coloca de forma que no bloquea ni afecta la ejecución. Es como una introducción a la asincronía

![](../../../.gitbook/assets/imagen%20%28350%29.png)

{% embed url="https://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D" %}





