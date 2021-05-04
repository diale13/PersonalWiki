# Username enumeration via subtly different responses

> This lab is subtly vulnerable to username enumeration and password brute-force attacks. It has an account with a predictable username and password, which can be found in the following wordlists:
>
> *  [Candidate usernames](https://portswigger.net/web-security/authentication/auth-lab-usernames)
> *  [Candidate passwords](https://portswigger.net/web-security/authentication/auth-lab-passwords)
>
>  To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.

Haciendo lo mismo que la vez anterior no nos lleva a nada pero agregamos un Grep-Extract desde options que nos marca si dice  Invalid username or password. Hay uno que es distinto porque tiene un pequeño espacio.

![](../../../.gitbook/assets/imagen%20%28656%29.png)

ae es nuestro user entonces. Probemos bruteforcearle la pass 

Igual al otro llegamos a que es **football.**



