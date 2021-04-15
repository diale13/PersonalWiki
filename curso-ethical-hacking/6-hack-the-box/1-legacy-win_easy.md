# 1 - Legacy \(win\_easy\)

Comenzaremos lanzandole un **nmap** a la maquina

```text
nmap -T4 -p- -A -sS 10.10.10.4
```

![](../../.gitbook/assets/imagen%20%28455%29.png)

Vemos **139 y 445** relacionados con SMB -&gt; SAMBA file share.

![](../../.gitbook/assets/imagen%20%28456%29.png)

Es algo a destacar en los reportes, puede dar acceso a alguna shell.

Vamos a atacar SMB porque es lo abierto.







