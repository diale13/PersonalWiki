# 7 - Automatizacion basica

Cuando lanzamos un ping por ejemplo los resultados se lanzan a la consola pero se puede llevar a un archivo de forma automatica

```text
$ ping ip -c 1 > ip.txt
```

Recordar -c 1 hace que solo pingue 1 vez.

Queda bien eso pero por ejemplo si solo nos interesa quedarnos con la respuesta deberiamos usar algo llamado **grep.** Al usar pipe separamos los comandos que vamos a continuacion.

![](../../.gitbook/assets/imagen%20%28109%29.png)

## Comando cut

![](../../.gitbook/assets/imagen%20%28107%29.png)

Lo que hace es como un split, la -d es el delimitante, es donde vamos a cortar. La f es para for, haremos 4 de eso -&gt; obtenemos solo las ip entonces.

## Comando translate tr

![](../../.gitbook/assets/imagen%20%28106%29.png)

Es un trim para esos dos puntos basicamente, sigue ese formato

## Creando un script en bash

Podes usar tu editor favorito, el del tutorial usa **mousepad** para crear ipsweep.sh

```text
#!/bin/bash
for ip in ´seq 1 254´; do
ping $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
done
```

Notas: 

!/bin/bash indica que es un codigo de bash.

Ahora el $1 tiene la funcion de ser **el primer parametro** es decir que aqui le pondremos la ip que querramos empezar a testeaar. Se usa entonces: \.ipsweep.sh 192.168.4\(y aca el programa prueba una por una que ips estan vivas\)

**Ideal para las subnets /24**

Mejora al script

```text
#!/bin/bash
if [$1 == " "]
echo "bad syntax add ip to first arg"
else
for ip in ´seq 1 254´; do
ping $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
done
fi
```

Algo a notar es el **&** al final del ping. Esto hace que se manden concurrentes los comandos, en caaso de querer hacerlos lineal poner un ;

![El uso final es asi y te permite ver que ips estan vivas en un txt](../../.gitbook/assets/imagen%20%28110%29.png)

## **Uso de bash con nmap**

![](../../.gitbook/assets/imagen%20%28108%29.png)

\*\*\*\*





