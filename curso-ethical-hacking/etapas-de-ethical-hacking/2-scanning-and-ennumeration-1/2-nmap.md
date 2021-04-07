# 2 - NMAP

Antes de usar nmap podemos lanzar 

```text
$ netdiscover -r 192.168.57.0/24
```

![](../../../.gitbook/assets/imagen%20%28189%29.png)

## NMAP

Lo que hace al correr un escaneo en modo stealth \(-sS\) es lanzarlo en modo sigilo de la siguiente forma:

![Amo paint es mi pasion](../../../.gitbook/assets/imagen%20%28188%29.png)

Ahora eso marca que casi hace la conexion con el puerto PERO no la aestablece del todo, ergo no lo detecta el puerto...en teoria es asi sigiloso pero hoy existen tecnicas de deteccion. Dicho eso no siempre estan implementadas.

```text
nmap -T4 -p- -A IP 
```

**T4:** es la velocidad con la que lo hacemos. Va de 1 a 5. 5 es muy rapido y puede fallar, lo otro es mas lento que puede ser beneficioso al ser dificil de detectar...pero mas lento

**p:** sin la p escanea los puertos comunes y conocidos de los objetivos, con la p escanea TODOS LOS PUERTOS. Configuraciones adicionales es poner -p 80,443 como un ejemplo de escaneo a un web service

**-A:** ALL OF IT. Quiero la version, el sistema operativo, fingerprinting, toodoooooooooo

![](../../../.gitbook/assets/imagen%20%28181%29.png)

-**sU** scaneo de puertos udp

```text
nmap -sU -T4 -p- -A IP 
```

El problema con -A es que consume mucho ya que intenta usar scripts y tecnicas adicionales para identificar esos elementos adicionales. Lo ideal entonces es largar el nmap para ver todos los puertos y luego usar el -A en aquellos que esten abiertos. -&gt; Es scripteable esto tambien

![Resultado de script](../../../.gitbook/assets/imagen%20%28182%29.png)

Esto muestra puertos abiertos y versiones de los mismos





