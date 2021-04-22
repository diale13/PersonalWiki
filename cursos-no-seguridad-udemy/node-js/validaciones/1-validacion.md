# 1 - Validacion

## Validacion base

Los objetos como lo puede ser Course traen un metodo **.validate\(\)** donde si falta algo se retorna una excepcion que podes atajar en un trycatch

![](../../../.gitbook/assets/imagen%20%28539%29.png)

En mongo no podemos pedir nada required directamente en la bd, si algo cae null queda como null en mongo sin molestar.

## Built-in validator

Estos estan buenos si queres que se retorne una validacion acorde a una propiedad, en el caso siguiente el precio solo es requerido si esta publicado.

![](../../../.gitbook/assets/imagen%20%28537%29.png)

Tambien podes usar tags como **minlength, maxlength** 

![](../../../.gitbook/assets/imagen%20%28541%29.png)

## Custom validator

![](../../../.gitbook/assets/imagen%20%28542%29.png)

## Async validation

Lo anterior pero async

![](../../../.gitbook/assets/imagen%20%28540%29.png)















