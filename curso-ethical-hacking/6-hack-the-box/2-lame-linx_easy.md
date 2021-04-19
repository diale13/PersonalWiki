# 2 - Lame \(Linx\_easy\)

## Scanning

```text
nmap -T4 -p- -A -sS 10.10.10.3
```

![](../../.gitbook/assets/imagen%20%28479%29.png)

**Sobre FTP:** No necesariamente el poder subir archivos es considerado malicioso, realmente necesitariamos algo mas ejecutable que eso.

**SSH**: Puede ser explotado, pero muy rara vez se lo ve en una version vieja.

Como pentest podemos tomar el enfoque de entrar y hacer RUIDOOOO pero si nos detectan empezar a ser un poco mas sigilosos.

Este tine **SMB** abierto tambien.

## Viendo SMB

![](../../.gitbook/assets/imagen%20%28478%29.png)

![](../../.gitbook/assets/imagen%20%28480%29.png)

Entonces para entrar a una carpeta de smb

```text
smbclient \\\\10.10.10.3\\tmp
```

Bueno tiramos metasploit bla bla

![](../../.gitbook/assets/imagen%20%28476%29.png)

![](../../.gitbook/assets/imagen%20%28477%29.png)

Bum pop shell.

```text
locate root.txt
locate user.txt
```

Ahi estan nuestras flags.

