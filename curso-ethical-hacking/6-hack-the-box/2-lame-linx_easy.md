# 2 - Lame \(Linx\_easy\)

## Scanning

```text
nmap -T4 -p- -A -sS 10.10.10.3
```

![](../../.gitbook/assets/imagen%20%28480%29.png)

**Sobre FTP:** No necesariamente el poder subir archivos es considerado malicioso, realmente necesitariamos algo mas ejecutable que eso.

**SSH**: Puede ser explotado, pero muy rara vez se lo ve en una version vieja.

Como pentest podemos tomar el enfoque de entrar y hacer RUIDOOOO pero si nos detectan empezar a ser un poco mas sigilosos.

Este tine **SMB** abierto tambien.

## Viendo SMB

![](../../.gitbook/assets/imagen%20%28479%29.png)

![](../../.gitbook/assets/imagen%20%28482%29.png)

Entonces para entrar a una carpeta de smb

```text
smbclient \\\\10.10.10.3\\tmp
```

Bueno tiramos metasploit bla bla

![](../../.gitbook/assets/imagen%20%28476%29.png)

![](../../.gitbook/assets/imagen%20%28478%29.png)

Bum pop shell.

```text
locate root.txt
locate user.txt
```

Ahi estan nuestras flags.

## Shadow and UnShadow

Recordar que los archivos con las contraseñas ya no estan en la carpeta passwd y estan en shadow

La gracia de la tool unshadow es que le pases el contenido de passwd y shaddow y te los mergea como el sistema viejo.

![](../../.gitbook/assets/imagen%20%28481%29.png)

1: Etapa de creacion de archivos, copiamos y pegamos

2: Unshadow.

Con esto el paso 3 es usar [hashcat](https://www.youtube.com/watch?v=eq097dEB8Sw).

## FTP

![](../../.gitbook/assets/imagen%20%28477%29.png)

Podes conectarte con anonymous y la misma pass

Luego usar **ls.** No habia nada





