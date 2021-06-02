# 5 - Quiz App and MVCDesign Pattern

## Objetivo

![](../../.gitbook/assets/imagen%20%28798%29.png)

Ver como haremos un quizz app con una progresion abajo, un contador de restantes y que maneje preguntas y respuestas.

## Descargando esqueleto

{% embed url="https://github.com/londonappbrewery/Quizzler-Android" %}

Viene con esto en **res/strings**

![](../../.gitbook/assets/imagen%20%28803%29.png)

Tambien viene con esto

![](../../.gitbook/assets/imagen%20%28785%29.png)

![](../../.gitbook/assets/imagen%20%28804%29.png)

Hay unos colores extraidos de aqui:

{% embed url="https://flatuicolors.com/" %}

## Understand Casting & Link the Layout to the Java Code

En main activity

![](../../.gitbook/assets/imagen%20%28805%29.png)

Recordando de otros proyectos lo que hacemos es declarar la variable de clase mTrueButton para referirnos a nuestro boton y luego encontrar la view del mismo.

{% embed url="https://developer.android.com/reference/android/app/Activity" %}

Ahi vemos como se define el findviewbyid

![](../../.gitbook/assets/imagen%20%28790%29.png)

![Resultado](../../.gitbook/assets/imagen%20%28808%29.png)

## OnClickListener & Implement a Toast Message

![](../../.gitbook/assets/imagen%20%28807%29.png)

Comienza haciendo la implementacion de los botones

![](../../.gitbook/assets/imagen%20%28809%29.png)

Al hacer click en el boton de true se logea ese mensaje.

Otra forma de hacer este listener es ponerlo como una funcion anonima similar a lo que se hace en js.

![](../../.gitbook/assets/imagen%20%28813%29.png)

**Creando el toast**

![](../../.gitbook/assets/imagen%20%28797%29.png)

Se puede simplificar poniendo .show\(\) al final de la creacion para dejarlo en una linea sin reservar memoria.



## Creando true or false

En el mismo lugar donde manejamos nuestra mainactivity.java creamos un objeto nuevo TrueFalse.java

![](../../.gitbook/assets/imagen%20%28787%29.png)

La clase truefalse puede ser instanciada dentro de la actividad principal

```text
TrueFalse exampleQuestion = new TrueFalse(R.string.question_1, true);
```

La clase R. es la encargada de acceder a nuestros elementos xml dentro de strings, values, id..

![](../../.gitbook/assets/imagen%20%28792%29.png)

Luego como es java y es horrible tenes que hacer los get y set.

## The Model View Controller \(MVC\) Design Pattern and Why We Use It

![](../../.gitbook/assets/imagen%20%28802%29.png)

## Retrieve Quiz Questions from an Array and Display them on Screen

![](../../.gitbook/assets/imagen%20%28801%29.png)

Coloca las preguntas en un array acorde a un indice que esta colocado como global. Luego al hacer .setText en la view coloca el texto de la pregunta en la misma. 

## Update Questions on Screen and Interpret Errors in the Logcat

Generamos un metodo update question

![](../../.gitbook/assets/imagen%20%28814%29.png)

Ahora esto claramente se cae una vez que llegamos al final.

![](../../.gitbook/assets/imagen%20%28820%29.png)

Luego cambiamos ese 13 por una constante.

Generamos este metodo

![](../../.gitbook/assets/imagen%20%28818%29.png)

![](../../.gitbook/assets/imagen%20%28821%29.png)

## Working with the Progress Bar and Tracking Score

Ahora para esta seccion incluimos nuevos componentes que manejen la barra y el score

![](../../.gitbook/assets/imagen%20%28815%29.png)

En update question sumamos un tamañano a la barra y en el check answer sumamos uno si la tiene bien a la variable global

![](../../.gitbook/assets/imagen%20%28816%29.png)



Esto sumado a un cambio del progress bar increment ya nos deja con una app casi completa

![](../../.gitbook/assets/imagen%20%28817%29.png)

La app funciona correctamente \(sin terminar el programa ya que una vez llega a 13 vuelve a 0\) pero tambien presenta el problema de que si se rota vuelve a la primer pregunta y pone nuestro score en 0.

![](../../.gitbook/assets/imagen%20%28819%29.png)



