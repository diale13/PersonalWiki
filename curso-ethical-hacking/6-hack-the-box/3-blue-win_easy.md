# 3 - Blue \(win\_easy\)

```text
nmap -T4 -p- -A -sS 10.10.10.40
```

La gracia de este es explotar **ETERNAL BLUE** super famoso y permitie ejecutar codigo y ganar acceso en computadoras remotas.

![](../../.gitbook/assets/imagen%20%28508%29.png)

Cuando vemos esas versiones de windows 7 suena nuestra alarma hacker y decimos ETERNAL BLUE.

Primero checkeamos si esta para darle al eternal blue, no queremos dispararlo sin estar seguro de que existe en la maquina.

![](../../.gitbook/assets/imagen%20%28503%29.png)

![](../../.gitbook/assets/imagen%20%28509%29.png)

![Funciona a la primera](../../.gitbook/assets/imagen%20%28505%29.png)

Esta bien pero podemos mejorar la reverse shell

![](../../.gitbook/assets/imagen%20%28510%29.png)

Probemos con reverse tcp. 

## We are in

![](../../.gitbook/assets/imagen%20%28504%29.png)

Tiramos algunos para estudiar la red

```text
route print
arp -a
netstat -ano
```

### Usando kiwi

```text
meterpreter > load
(tira lista de extensiones)

meterpreter > load kiwi
```

![](../../.gitbook/assets/imagen%20%28506%29.png)

Otra extension muy buena es **incognito**.

![](../../.gitbook/assets/imagen%20%28507%29.png)

