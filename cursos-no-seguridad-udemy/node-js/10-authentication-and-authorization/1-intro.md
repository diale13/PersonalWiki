# 1 - Intro

![](../../../.gitbook/assets/imagen%20%28650%29.png)

## Modelo de usuarios

```javascript
const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
    minlength: 5,
    maxlength: 50
  },
  email: {
    type: String,
    required: true,
    minlength: 5,
    maxlength: 255,
    unique: true       //Notar mail unico
  },
  password: {
    type: String,
    required: true,
    minlength: 5,
    maxlength: 1024  //Notar largo adicional para hashear
  },
  isAdmin: Boolean
});
```

Ahora la validacion

```javascript
function validateUser(user) {
  const schema = {
    name: Joi.string().min(5).max(50).required(),
    email: Joi.string().min(5).max(255).required().email(),
    password: Joi.string().min(5).max(255).required()
  };

  return Joi.validate(user, schema);
}
```

Ver ese .email\(\) para la validacion

## Register new user

No olvidar agregar los controllers creados al index:

![](../../../.gitbook/assets/imagen%20%28652%29.png)

Volviendo al controlador puntual vamos a empezar con el post:

```javascript
router.post('/', async (req, res) => {
  const { error } = validate(req.body); 
  if (error) return res.status(400).send(error.details[0].message);

  let user = await User.findOne({ email: req.body.email });
  if (user) return res.status(400).send('User already registered.');

  user = new User(_.pick(req.body, ['name', 'email', 'password']));
  const salt = await bcrypt.genSalt(10);
  user.password = await bcrypt.hash(user.password, salt);
  await user.save();

  const token = user.generateAuthToken();
  res.header('x-auth-token', token).send(_.pick(user, ['_id', 'name', 'email']));
});

```

Notas clave:

```javascript
  let user = await User.findOne({ email: req.body.email });
```

Esto implica que estamos buscando por su propiedad de correo.

Recordar que con la funcion validate ya se valida de base todo lo acalarado en el modelo. Esto es mismo el body debe ser correcto \(tener nombre, contraseña, mail validos\) y que no le falte nada.

## Modificando la respuesta del endpoint

No queremos que retorne su contraseña por ejemplo.

1 enfoque seria retornar una custom response:

![](../../../.gitbook/assets/imagen%20%28649%29.png)

Esta bien pero hay librerias mejores para hacer eso: **Lodash**

Desde la terminal: 

```javascript
npm install lodash
```







