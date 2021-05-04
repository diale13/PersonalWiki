# 5 - Poniendo nuestro metodo de auth en header

```text
 const token = user.generateAuthToken();
 res.header('x-auth-token', token).send(_.pick(user, ['_id', 'name', 'email']));
```

![](../../../.gitbook/assets/imagen%20%28663%29.png)

