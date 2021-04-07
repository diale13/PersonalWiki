# 8 - Estructurando bien las cosas

Claramente no queres todo en el index, para eso modificaremos la estructura del proyecto.

Debemos poner courses.js por separado como el controler por ejemplo

![](../../../.gitbook/assets/imagen%20%28260%29.png)

![](../../../.gitbook/assets/imagen%20%28259%29.png)

Y al final del codigo haces

```text
module.exports = router;
```

![En index agregamos eso](../../../.gitbook/assets/imagen%20%28258%29.png)

Ahora como especificamos esas rutas cambian dentro de courses.js

![](../../../.gitbook/assets/imagen%20%28261%29.png)

Hace cambios similares para tener el index por separado.



