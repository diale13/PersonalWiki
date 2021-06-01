# 1 - I am rich!

## Objetivo:

![](https://lh6.googleusercontent.com/HyMdYBFpoUyd1s1gCQb2j7DRi1PsOkwTkHoDalh8gY6e-lFaEWAqFYioWyGR3CpAHIQI8hCabVBahtTq-a6X0QNOb3tVcP4jIFKT4mRdV_6Akm37j-plXLZTfgxk7IvYgBoAHRh6)

Al crear el proyecto se sigue la estructura de nombres compania.com.nombre. Esto es clave para que la palystore sepa identificar apropiadamente los niveles correspondientes y separar en compañías distintas.



![](https://lh3.googleusercontent.com/3yrB8HHVYg68Lxm-7dbxIcQfefpqf9ElaMKQG3D9CawbgzLnbmZw2AUyvAPr6zc2m8ax650towhRdZoCwkbJLKGZKOH6Oy8nmF5_p403rkXmmGEBCJS6bXBGrDsKQ0dAwdaZupFl)

Al comenzar se nos presenta la main activity, las activities van separadas en layout y la actividad misma

![](https://lh5.googleusercontent.com/mLUS5qzXCpsTJZ5xU22H61cVhBXu3rkzAlykHtSF-6PuR5MVwj5aXPV86GnYbNHr_nZ2CsoBN4MYHVP7cGdwMAj1vRorbqouMFdrb5jwzMPS8lwQD-OwBy-2v71gcxw4MPL3StP6)

El layout marca como se ve y la actividad que se hace. El layout se encuentra dentro de la carpetaa res y layout.

* _Gradle es el que construye la app. Podemos monitorear el proceso por debajo._

## Working with the Layout Editor, Strings, and App Themes:

![](https://lh5.googleusercontent.com/ZfdpVlp8prPMZ5R22T69xjfSuwRxc9jNxB8SyN-xBP_G1jt86_0P1a-FFK7_IUEBTEuYlpiIdH2rNHH90pOyRSLtf7sFK4ih5QCaFf9Tlu2XMQpkSt06ic7OjmzJnwbcuVNI1lIQ)

Este es el editor de layout encontrado en res. Podemos verlo a modo de diseño de la app y de texto   


![](https://lh5.googleusercontent.com/RDSiBSRwnNI7utpSFYyPAcwdlFfO0ywNzWb3sO4qxRvzKfazzufUBD2wCZ4D45JMTdsggahD9-Qd15fz2BXulSxNCSrguw-NF095bNbd5-6uv52n6DfKW4nsX45vztTCD_l66v0T)

En el modo texto lo vemos en XML.  


### Eliminando la barra

![](https://lh3.googleusercontent.com/1oJ5z1iFPPClxniYtiZ78SqNAlmbj1WTtXfnH819WIvu-PA13oYEUkAKoK1XSv82L3pbrncs4nTbEp4hQjs8V6B3QIskudxYZ3v8GFZODL7S8ZYCo6FzIOpuQfdgAzT_Lo-z24hz)

![](../../.gitbook/assets/imagen%20%28752%29.png)

Si le ponemos **NoActionBar** se va la barra.

![](../../.gitbook/assets/imagen%20%28762%29.png)

Cambiando esas propiedades va a poner un I AM RICH grande y centrado.

Ahora con eso nos saltara un warning que nos avisa de porque esta mal tener strings harcodeados. 

![](../../.gitbook/assets/imagen%20%28759%29.png)

Para corregir nuestras infracciones debemos ir y modificarlo directamente sobre **strings.xml** dentro de la carpeta values.

En carpeta strings

![](../../.gitbook/assets/imagen%20%28764%29.png)

Nuevamente en layout:

![](../../.gitbook/assets/imagen%20%28763%29.png)

## Adding Graphics to a Project and using ImageViews

Bajamos los assets para el proyecto \(basicamente la foto del diamante\) y la misma debe ser colocada en la carpeta drawable dentro de res.

Luego basta con poner una **image view** que sea nuestro diamante. La misma apunta al archivo colocado en drawable.

![](../../.gitbook/assets/imagen%20%28753%29.png)

Si pintamos el fondo podemos ver como estan colocados los archivos, con la imagen adelante del texto.

![](../../.gitbook/assets/imagen%20%28755%29.png)

Aqui muestra como asignando distintas propiedades al layout se logran diferentes estilos y objetivos. Desde centrar el layout a ponerlo en horizontal.

## XML and How Does it Work?

![Component tree](../../.gitbook/assets/imagen%20%28754%29.png)

![](../../.gitbook/assets/imagen%20%28756%29.png)

Facil de buscar por tags, prety easy

## Setting a Custom Launcher Icon

![](../../.gitbook/assets/imagen%20%28760%29.png)

Hay muchas versiones del mismo logo pues varian segun la resolucion del telefono y que tanto soporta.

Lo que hace es cambiar por logos propios \(con la foto del diamante\) cada uno de esos con su sustituto apropiado \(varias veces\).  Luego para actualizar el logo debemos ir a **android manifest.**

![](../../.gitbook/assets/imagen%20%28758%29.png)

![](../../.gitbook/assets/imagen%20%28761%29.png)

## Editando la home screen 

![](../../.gitbook/assets/imagen%20%28766%29.png)

Podemos elegir el posicionamiento de forma mas precisa editando el xml 





