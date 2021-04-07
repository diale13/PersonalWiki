# 5 - Config

{% embed url="https://www.npmjs.com/package/config" %}

```text
npm -i config
```

Te haces una carpeta llamada config y dentro de ella un default.json

```javascript
{
    "name": "my app"
}
```

Y otra development.json para configuara eso

![](../../../.gitbook/assets/imagen%20%28242%29.png)

![](../../../.gitbook/assets/imagen%20%28229%29.png)

![](../../../.gitbook/assets/imagen%20%28256%29.png)

Las variables mas sensibles como las contraseñas no las guardas ahi, para eso usas variables de ambiente 

```javascript
$ export usrPass=1234
```

Creamos otro archivo dentro de la carpeta config llamado **custom-environment-variables.json** clave el nombre asi

![](../../../.gitbook/assets/imagen%20%28249%29.png)





