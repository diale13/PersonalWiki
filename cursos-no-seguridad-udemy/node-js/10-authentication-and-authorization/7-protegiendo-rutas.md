# 7 - Protegiendo rutas

Se requiere el modulo de auth y luego entra como parametro.

```text
router.post('/', auth, async (req, res) => {
  const { error } = validate(req.body); 
  if (error) return res.status(400).send(error.details[0].message);

  let genre = new Genre({ name: req.body.name });
  genre = await genre.save();
  
  res.send(genre);
});
```

Es un middleware entonces ejecuta y listo.

