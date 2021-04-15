# 1 - Intro

Es una base documental, no usa views ni schemas, el beneficio es que se guarda el objeto JSON . Al hacer query es directo ya que no debe transformar nada.

## Instalacion Linux

{% embed url="https://itsfoss.com/install-mongodb-ubuntu/\#install-from-ubuntu-repository" %}

## Instalacion windows

Bajas el installer de la base y del compass que es el viewer. Luego desde opciones avanzadas agregamos el path de mongo a las variables de ambiente

![](../../../.gitbook/assets/imagen%20%28464%29.png)

Primero verificamos que la base se ha creado correctamente. Luego garantizamos que esta el path a la carpeta por defecto creandolo.

```text
mongod
md c:\data\db
```



