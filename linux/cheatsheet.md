# Cheatsheet

## Intro

Sobre todos los comandos podes usar **man** command para obtener ayuda

ejemplo: **man** ls para obtener ayuda.

## Filesystem

| **Command** | Explain |
| :--- | :--- |
| ls carpeta | muestra contenido carpeta |
| _ls **-la** carpeta_ | muestra conenido y carpetas ocultas |
| **mkdir** carpeta | Crea directorio carpeta |
| **echo** "a" **&gt;** hola.txt | coloca en el documento esa linea |
| **cp** hola.txt Downloads/ | Mueve hola.txt a Downloads |
| **rm** hola.txt | borra hola.txt \(se puede lanzar desde afuera\) |
| **mv** hola.txt Downloads/ | mueve archivo |
| **locate** Bash | busca todo lo relacionado a bash |
|  | ligado a eso quizas es bueno poner **updatedb** |
|  | reindexa todo para mejorar locate |
| chmod 777 | brinda permisos completos a un archivo  |
|  | claramente hay que ser root o similar |

## Networking

| Command | Result |
| :--- | :--- |
| ifconfig | Muestra configuracion de red, ip, mascaras y relacionados |
| iwconfig | configuracion de wireless |
| ping ip | la diferencia con el de windows es que este es infinito |
|  | debes cancelarlo con cntrl+c |
| arp -a | Muestra con que ips habla y la direccion mac de las mismas |
| netstat -ano | muestra conexiones activas de nuestra computadora |
| route | muestra por donde se va el trafico de red |
|  | Si hay varias bandas u redes puede mostrar mas de uno |
| ip a | **version mejorada de ifconfig** |
| ip r | muestra routing |
| arp-scan -l | muestra objetos en red mediante scaneo arp |
| netdiscover -r ip/mask | Descubre elementos de red |

## Usuarios

| Command | Result |
| :--- | :--- |
| **passwd** | promptea cambio de pass para usuario |
| adduser name | crea usuario |
| sudo | magia |
|  |  |

