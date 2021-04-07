# 4 - Enumerando SMB \(139\) - METASPLOIT

SMB es un sistema de transferencia de archivos

![](../../../.gitbook/assets/imagen%20%28206%29%20%281%29.png)

Comenta ademas que usan samba

## METASPLOIT

Framework para exploit

```text
msfconsole
```

![](../../../.gitbook/assets/imagen%20%28203%29.png)

```text
search smb
```

![Salen muchisimos modulos](../../../.gitbook/assets/imagen%20%28197%29.png)

Se copia el 60 que es auxiliary/scanner/smb/smb\_version

![](../../../.gitbook/assets/imagen%20%28205%29.png)

Tambien podes poner "use 60"

![](../../../.gitbook/assets/imagen%20%28200%29.png)

Abajo pone options para ver que hacer

RHOSTS -&gt; El objetivo \(s\) 

### Con esto consigue la version

![](../../../.gitbook/assets/imagen%20%28208%29.png)

Asi que setea el rhost y luego usa run para atacar el target

## Smbclient

![](../../../.gitbook/assets/imagen%20%28199%29.png)

Con eso no pudo conectarse, el lo intenta dos veces mas y logra conectarse

![](../../../.gitbook/assets/imagen%20%28210%29.png)

We are in boys 😎😎😎

Ahora con esto esta dentro de una especie de maquina linux para trasnferir archivos. Lo clave fue probar **admins** y luego **ipc.**

Resulta que no nos aporto mucho y fue un dead end, pero pudimos listar eso.











