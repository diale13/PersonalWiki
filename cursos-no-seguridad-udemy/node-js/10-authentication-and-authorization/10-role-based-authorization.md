# 10 - Role Based Authorization

Agregamos middleware admin :

{% code title="admin.js middleware" %}
```javascript
module.exports = function (req, res, next) { 
  // 401 Unauthorized
  // 403 Forbidden 
  
  if (!req.user.isAdmin) return res.status(403).send('Access denied.');

  next();
}
```
{% endcode %}

Entonces primero llamamos al middleware de auth y luego a este

```javascript
router.delete('/:id', [auth, admin], async (req, res) => {
  const genre = await Genre.findByIdAndRemove(req.params.id);

  if (!genre) return res.status(404).send('The genre with the given ID was not found.');

  res.send(genre);
});
```

