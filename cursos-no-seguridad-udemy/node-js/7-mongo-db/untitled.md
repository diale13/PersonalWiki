# 5 - Update y delete

## Enfoques para update

### Query First

En este enfoque:

1.  Lo buscamos por id
2.  Lo modificamos acorde al parametro
3. Guardamos denuevo en la bd

![](../../../.gitbook/assets/imagen%20%28495%29.png)

### Update First

En este enfoque:

1.  Lo modificamos acorde al parametro **directamente sobre la bd**
2.  lo traemos denuevo al backend \(opcional\)

Aca leer esto como guia basica de los opeadores

{% embed url="https://docs.mongodb.com/manual/reference/operator/update/" %}

![](../../../.gitbook/assets/imagen%20%28499%29.png)

Sencilla y clean. Si queremos retornar lo modificado podemos usar FIndByIdAndUpdate

![](../../../.gitbook/assets/imagen%20%28502%29.png)

## Delete

![Borrado basico](../../../.gitbook/assets/imagen%20%28501%29.png)

![Borrado con retorno](../../../.gitbook/assets/imagen%20%28494%29.png)



