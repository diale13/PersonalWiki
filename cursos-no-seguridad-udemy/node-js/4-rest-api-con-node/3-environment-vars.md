# 3 - Environment vars

Cuando trabajas en produccion no esta bueno harcodear el puerto ya que se suele asignar dinamicamente. Para eso la pasaremos a una variable de ambiente.

![](../../../.gitbook/assets/imagen%20%28217%29.png)

Lo que dice ahi es si no tenes una variable de ambiente llamada PORT te lo manda al 3000 por defecto.

En MAC las variables se exportan con **export** y en windows con **set** ambas desde la terminal

 

```text
export (o set) PORT=5000 
```



