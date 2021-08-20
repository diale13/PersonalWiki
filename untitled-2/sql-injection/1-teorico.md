# 1 - Teorico

## Intro

Permite introducir codigo sql donde normalmente no estaria permitido y obtener informacion directamente de la base de datos. O modificarla. Es incluso posible escalar esta amenaza a conseguir informacion del servidor.

![](../../.gitbook/assets/imagen%20%28605%29.png)

## Impacto de una inyeccion de SQL

Un ataque exitoso puede resultar en el acceso sin autorizacion o la obtencion de informacion. El atacante puede incluso dejar un backdoor a la organizacion llevando a un impacto a largo tiempo.



## Atacando la URI

![](../../.gitbook/assets/imagen%20%28607%29.png)

Releleased es un atributo interno dentro de la aplicacion.

Ahora si un atacante modificase el codigo de la uri para agregar un comentario y este input no es sanitizado ocurre lo siguiente

![](../../.gitbook/assets/imagen%20%28593%29.png)

Comenta el codigo y revela informacion de objetos sin release.

### Agregando una condicion para obtener todo

![](../../.gitbook/assets/imagen%20%28603%29.png)

## Atacando Log-In

Que sucede cuando hacemos log in con nuestro user= wiener y nuestro pass= bluecheese

![](../../.gitbook/assets/imagen%20%28602%29.png)

Curioso que pasaria si ponemos de usuario \(sin siquiera pas\) administrator'--

![](../../.gitbook/assets/imagen%20%28611%29.png)

 `SELECT * FROM users WHERE username = 'administrator'--' AND password = ''`

## Obteniendo datos de otras tablas

Usando union lo sumamos a nuestra query.

![](../../.gitbook/assets/imagen%20%28604%29.png)

## Obteniendo informacion de la base

Algo relevante puede ser obtener informacion de la base a modo de seguir atacandola y obtener activos mas criticos.

Se puede obtener informacion de las version:

**En oracle:**

```text
SELECT * FROM v$version
```

Otra forma de obtener info es obtener a travez de esto:

![](../../.gitbook/assets/imagen%20%28596%29.png)

## Inyeccion a ciegas

Cuando el atacante no sabe contra que motor de base de datos se esta enfrentando.

Podemos cambiar la query acorde a elementos logicos que revelan esto. Por ejemplo delays en las query que difieren entre motores.

![](../../.gitbook/assets/imagen%20%28598%29.png)

Lo ultimo implica exifltrar info poniendo informacion en un dominio controlado por nosotros.

## Usando Burpsuit 

Posee una tool que detecta inputs y busca inyectarle sql de forma automatica.

![](../../.gitbook/assets/imagen%20%28600%29.png)

## Inyeccion de segundo orden

![](../../.gitbook/assets/imagen%20%28608%29.png)

La diferencia radica en que en este ataque se mantiene el ataque persistido en la base, el siguiente usuario que entra lo sigue viendo.

