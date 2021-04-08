# Nivel 3

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

Entonces probemos

