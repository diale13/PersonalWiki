# 6- Weather App - Use GPS and APIs toGet Data from the Web

## Objetivo

Una app para ver el tiempo, vamos a ver gradle dependencies, coneccion a apis

![](../../.gitbook/assets/imagen%20%28846%29.png)

Tambien trae multiples pantallas ****al tocar el boton de arriba a la derecha.

![](../../.gitbook/assets/imagen%20%28833%29.png)

### Esqueleto

{% embed url="https://github.com/londonappbrewery/clima-android" %}

**El esqueleto contiene**

* Pantalla principal y secundaria, separadas en activities

![](../../.gitbook/assets/imagen%20%28829%29.png)

* Imagenes el drawable que coinciden con aspectos como lo son "soleado" "lluvioso"
* Para solicitar api key de clima solicitar aqui openweathermap.org/appid

## Gradle Project & Module Scripts and Android SDK Compatibility

Diferencia entre build.gradle de proyect y de app:

El del proyecto es general a todos los dispositivos donde se implemente esta solucion. Este en particular es de celular pero podria ser usado por smart watches:

![](../../.gitbook/assets/imagen%20%28848%29.png)

De incluirlo aqui tendriamos lo siguiente:

![](../../.gitbook/assets/imagen%20%28834%29.png)

Entonces aqui tenemos **DOS MODULOS** uno siendo el de wear y el otro la app. 

Como no nos interesa hacer un modulo de wear lo borramos.

### En gradle app 

![](../../.gitbook/assets/imagen%20%28843%29.png)

Aqui vemos como se controla el minSdk y elementos similares, tambien podemos obtener una nocion de como se veria nuestra app de usar un sdk anterior cambiando los themes.

![](../../.gitbook/assets/imagen%20%28845%29.png)

Es importante notar como esto es antes de **material design \(**lo cual deberia incluir en este resumen\).

## Adding External Libraries as Dependencies with Gradle

Una forma de añadir nuestras dependencias es tenerlas en el propio proyecto en forma de .jars

![Es necesario que este eso en el gradle](../../.gitbook/assets/imagen%20%28826%29.png)

Esa es una forma que no mantiene las versiones actualizadas e implica descargarlas. La mas comun sin embargo es usar los repositorios de acceso. Se puede usar el mismo git, uno de maven o jcenter \(de los mas populares en android\)

![](../../.gitbook/assets/imagen%20%28835%29.png)

Con esto es suficiente para usar [https://loopj.com/android-async-http/](https://loopj.com/android-async-http/) una de las mejores liberias para conectar con http \(es usada por apps de gran porte como pinterest\)

![](../../.gitbook/assets/imagen%20%28828%29.png)























