# 5 - Poniendo nuestro metodo de auth en header

```text
 const token = user.generateAuthToken();
 res.header('x-auth-token', token).send(_.pick(user, ['_id', 'name', 'email']));
```

![](../../../.gitbook/assets/imagen%20%28663%29.png)

Ahora un tema con eso es que cada vez que necesitamos mandar un token para auth de user tenemos que crear una funcion o encapsularla en algun lado. El information expert aca es user asi que esa funcion queda para user.js

![](../../../.gitbook/assets/imagen%20%28674%29.png)

```javascript
userSchema.methods.generateAuthToken = function() { 
  const token = jwt.sign({ _id: this._id, isAdmin: this.isAdmin }, config.get('jwtPrivateKey'));
  return token;
}
```



