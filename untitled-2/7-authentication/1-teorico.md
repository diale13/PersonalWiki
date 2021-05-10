# 1 - Teorico

## Authentification

 Conceptualmente son snecillas. Se busca hacer bypass de las protecciones inpuestas para loggearse.

![](../../.gitbook/assets/imagen%20%28716%29.png)

Conceptos manejados:

*  Something you **know**, such as a password or the answer to a security question. These are sometimes referred to as "knowledge factors".
*  Something you **have**, that is, a physical object like a mobile phone or security token. These are sometimes referred to as "possession factors".
*  Something you **are** or do, for example, your biometrics or patterns of behavior. These are sometimes referred to as "inherence factors".

La authentification maneja la verificacion de uno o mas de estos controles.

## Vulnerabilities in multi-factor authentication

 El doble factor complica al atacante que ahora debe hacer bypass de dos cosas distintas. Pero este doble factor es solo tan seguro como su implementacion. 

Verificar dos veces el mismo factor de dos formas distintas no es realmente 2FA, por ejemplo verificacion con correo. Acceder al correo requiere las credenciales del mismo del mismo modo algo que podria ya haber sido comprometido.

### Two-factor authentication tokens <a id="two-factor-authentication-tokens"></a>

Ahora se manejan gestores de accesos fisicos. De igual modo se pueden manejar controles de SMS pero crea el potencial para la intercepcion del codigo, SIM swapping o algun otro ataque.

### Bypassing two-factor authentication <a id="bypassing-two-factor-authentication"></a>

 Hay veces que el control del 2fa puede ser saltado por completo. Por ejemplo pedir el codigo pero solo en una pagina y al cambiar el url saltearlo.

### Flawed two-factor verification logic <a id="flawed-two-factor-verification-logic"></a>

 Algunas veces el problema del 2fa esta luego del login, donde la pagina no verifica que el usuario este haciendo el segundo paso.

Por ejemplo para un usuario comun hace esto:.

 `POST /login-steps/first HTTP/1.1  
 Host: vulnerable-website.com  
 ...  
 username=carlos&password=qwerty`

 Aqui se le asigna una cookie que se relaciona con su cuenta antes del login. 

 `HTTP/1.1 200 OK  
 Set-Cookie: account=carlos  
  
GET /login-steps/second HTTP/1.1  
Cookie: account=carlos`

 Al hacer la verificacion se verificaa via cookie que account intenta acceder.

 `POST /login-steps/second HTTP/1.1  
 Host: vulnerable-website.com  
 Cookie: account=carlos  
 ...  
 verification-code=123456`

En esa ocasion se puede cambiar la cookie a la victima y hacer bypass.

`POST /login-steps/second HTTP/1.1  
 Host: vulnerable-website.com  
 Cookie: account=victim-user  
 ...  
 verification-code=123456`

El poder de esto radica en que la victima ni necesita ser accedida realmente, solo con saber su usario es suficiente.



