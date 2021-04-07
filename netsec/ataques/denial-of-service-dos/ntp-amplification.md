# NTP Amplification

{% embed url="https://www.youtube.com/watch?v=BcDZS7iYNsA" caption="Video original" %}

El NTP o network time protocol es lo que maneja los tiempos de nuestras computadoras, celulares y otros IOT objects coordinados hasta el milisegundo. La existencia de los servidores de tiempo en si no es algo necesariamente malo solamente la existencia de un comando totalmente mal diseñado llamado 

```text
monlist 
```

El comando monolist permite obtener los tiempos de las ultimas 600 personas que hicieron una solicitud. Algo que no tiene mucho sentido solicitar. Ahora el problema es que eso es enviado de a uno, algo que de por si solo ya puede hacer daño, esto se puede convertir en un DoS al usar diversas computadoras para hacer esa solicitud en nombre de una victima que recibira toda esa informacion. Bien hecho podemos estar hablando de un ataque de terabytes de informacion.

![](../../../.gitbook/assets/imagen%20%2848%29.png)

## ¿Que hacer al respecto?

Nosotros, incluso como asesores de seguridad no podemos hacer mucho, sino que todo depende de los NTP servers. Estos han de tener las verificaciones de seguridad y prohibir el comando **monlist.** Por lo demas un padre nuestro y buena suerte.

\*\*\*\*





