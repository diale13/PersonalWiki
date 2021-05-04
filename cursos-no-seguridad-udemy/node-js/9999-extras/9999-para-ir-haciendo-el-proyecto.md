# Para ir haciendo el proyecto

## Iniciando

```text
npm init --yes
```

## Paquetes a bajar

```text
npm -i debug // debuger para no usar full console.log
npm install mongoose //bd
npm i express  // para api
npm i -g nodemon // para no tener que "recompliar". Lo corres con nodemon y no con node.
npm i joi // validador de elementos de api
npm i lodash // clave para retornar bodys no reveladores en la api (ej no retornar pass del user creado)
npm i bcript //permite hacer el hasheo de contraseñas.

npm i jsonwebtoken //jwt
npm -i config
```

## Paquetes bastante opcionales

```text
npm -i helmet // seguridad
npm -i morgan // logger de requests http
```

## Notas buenas

* Si tenes una funcion es buena practica ver si retorna una promesa, si lo hace ponerle await adelante.
* 


