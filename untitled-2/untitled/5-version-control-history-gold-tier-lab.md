# 5 - Version control history \(gold tier lab\)

> This lab discloses sensitive information via its version control history. To solve the lab, obtain the password for the `administrator` user then log in and delete Carlos's account.

Version control -&gt; .git \(no fue tan rapido de pensar eso jaja\)

![](../../.gitbook/assets/imagen%20%28640%29.png)

## Ennumerando lo encontrado:

### Config:

```text
[user]
	email = carlos@evil-user.net
	name = Carlos Montoya
```

### Logs

```text
0000000000000000000000000000000000000000 5ba7171d8bf587ef24a2483800b4154b3ad64da8 Carlos Montoya <carlos@evil-user.net> 1619796638 +0000	commit (initial): Add skeleton admin panel
5ba7171d8bf587ef24a2483800b4154b3ad64da8 ce18e0371f12487555fd7edbaaf8e63fe78f45ba Carlos Montoya <carlos@evil-user.net> 1619796638 +0000	commit: Remove admin password from config
```

Bien por lo que vemos en algun momento dentro de config hubo un archivo de contraseñas. Tambien evidenciado COMMIT\_EDITMSG donde dice:

```text
Remove admin password from config
```

Luego necesitamos bajar ese file para hacer la comparacion entre los archivos:

asi que en kali: **wget -r lab.net/.git**

**Nota:** para ver hidden folders es control+h o ls -a.

![](../../.gitbook/assets/imagen%20%28632%29.png)

Hacemos el **diff** entre los archivos.

Nos logeamos con esa cuenta y borramos a carlos.

