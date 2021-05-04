# 2 - Hashing passwords

```javascript
const salt = await bcrypt.genSalt(10);
user.password = await bcrypt.hash(user.password, salt);
```

El salt agrega los elementos generados por el mismo a la contraseña.

Cuando las obtenemos nuevamente en auth ese salt debe ser el mismo para validar para eso usamos bcrypt

```javascript
const validPassword = await bcrypt.compare(req.body.password, user.password);
if (!validPassword) return res.status(400).send('Invalid email or password.');
```

