# 6 - Authorization Middleware

Hacemos carpta middleware

{% code title="auth.js" %}
```javascript
const jwt = require('jsonwebtoken');
const config = require('config');

module.exports = function (req, res, next) {
  const token = req.header('x-auth-token');
  if (!token) return res.status(401).send('Access denied. No token provided.');

  try {
    const decoded = jwt.verify(token, config.get('jwtPrivateKey'));
    req.user = decoded; 
    next();
  }
  catch (ex) {
    res.status(400).send('Invalid token.');
  }
}
```
{% endcode %}

La funcion recibe el next que implica cual es el siguiente middleware que se utilizara

```text
const decoded = jwt.verify(token, config.get('jwtPrivateKey'));
req.user = decoded; 
```

Recordar como funciona el jwt, se decodifica y nos trae el usuario en su totalidad, garantizado que es valido.



