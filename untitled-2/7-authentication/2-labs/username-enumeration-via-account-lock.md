# Username enumeration via account lock

> This lab is vulnerable to username enumeration. It uses account locking, but this contains a logic flaw. To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.
>
> *  [Candidate usernames](https://portswigger.net/web-security/authentication/auth-lab-usernames)
> *  [Candidate passwords](https://portswigger.net/web-security/authentication/auth-lab-passwords)

Lo que realizamos aqui es un ataque a todas las cuentas de la lista buscando ver cuales se bloquean tras muchos intentos. Hacemos un ataque cluster bomb con 5 payloads en null en la zona de passwords.

![Also me cambie al pro](../../../.gitbook/assets/imagen%20%28719%29.png)

Luego hacemos un ataque sniper con las passwords. Lo que se destaca es que una no ocasiona el error de espera.

![](../../../.gitbook/assets/imagen%20%28715%29.png)

Entramos con la misma para resolver nuestro lab.



