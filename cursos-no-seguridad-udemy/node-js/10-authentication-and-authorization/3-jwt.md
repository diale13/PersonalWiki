# 3 - JWT

![](../../../.gitbook/assets/imagen%20%28666%29.png)

## Estructura

![](../../../.gitbook/assets/imagen%20%28671%29.png)

En rojo el header que no nos preocupa mucho pues es interno del JWT, luego el payload que es lo que nos interesa, ahi podria estar el body donde dice "isAdmin" pero no va a ser cambiable porque al final hay un checksum

![](../../../.gitbook/assets/imagen%20%28670%29.png)

## Configurando en nuestra app

```text
npm i jsonwebtoken
```

![](../../../.gitbook/assets/imagen%20%28669%29.png)

Luego extraemos ese sign y su clave que sera puesta en una variable de ambiente.



