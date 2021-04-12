# 6 -Password spray && Credential stuffing -Burpsuit

Agarramos credenciales filtradas y las lanzamos contra un sitio

![](../../../.gitbook/assets/imagen%20%28368%29.png)

### **Froxy proxy** 

**Es una herramienta usada para apgar y prender rapidamente el burpsuit proxy**

![](../../../.gitbook/assets/imagen%20%28376%29.png)

## Burpsuit attacking

Hacemos un falso login para que el proxy lo detecte:

![](../../../.gitbook/assets/imagen%20%28363%29.png)

Hacemos click en ellos y en click derecho tocamos SEND TO INTRUDER

Luego en intruder vamos a positions y a la derecha le damos clear.

Hacemos highlight de user y pass 

![](../../../.gitbook/assets/imagen%20%28369%29.png)

Cambiamos de sniper a pitchfork

Ahora lo que hicimos ahi fue decir "aca va el payload 1 y aca el 2". Bien con eso vamos a payloads y ponemos para el 1 la lista de usuarios que vimos lekeada y en el 2 la de pass

![](../../../.gitbook/assets/imagen%20%28377%29.png)

![](../../../.gitbook/assets/imagen%20%28379%29.png)

Llegan respuestas, el 200 no necesariamente tiene que ser que estamos in. La respuesta incluye comentarios como "we could not sign you in"

Vamos con eso a opciones y lo podemos poner en la parte de grep para que haga match y nos diga si dice eso.

Consultar con los de la empresa porque podes lockear a alguien fuera de su cuenta.







