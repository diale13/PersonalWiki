# 2 - Iniciando proyecto y MongoDb

## Creando proyecto

```text
npm init --yes
npm install mongoose
```

Con el proyecto creado hacemos nuestra **conexion**:

```javascript
const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost/playground')
	.then(()=> console.log('Connected to MongoDB'))
	.catch(err => console.error('Could not connect to MongoDB...', err))
```

## Analizando MongoDb

![](../../../.gitbook/assets/imagen%20%28468%29.png)

El nombre de la coleccion es como las tablas en una base de datos relacional.  Cada documento equivale a una fila en una relacional.

![](../../../.gitbook/assets/imagen%20%28466%29.png)

![](../../../.gitbook/assets/imagen%20%28467%29.png)

En azul vemos como marca el objeto date por defecto en caso de no especificarse.

Para trabajar con un "objeto" de la base de datos utilizamos lo siguiente

![](../../../.gitbook/assets/imagen%20%28465%29.png)

## Guardando un cambio

![](../../../.gitbook/assets/imagen%20%28464%29.png)

