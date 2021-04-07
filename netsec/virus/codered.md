# CodeRed

• El 18 de junio de 2001, eEye publicitó una vulnerabilidad de desbordamiento de búffer en los servidores web Microsoft IIS: comprobación de límites inadecuados en algunos “buffers” de entrada permiten la ejecución de código a nivel del sistema. 

• El 12 de julio de 2001, el virus CodeRed comenzó a atacar a los equipo sin los parches de seguridad. 

## Funcionaba de la siguiente manera: 

• Si la fecha es entre el 1 y el 19 del mes, genera una lista aleatoria de direcciones IP e intenta infectar esas máquinas.

• Del 20 al 28 del mes, lanza un ataque de inundación DoS a la dirección www1.whitehouse.gov.

 • El gusano también desfigura algunas páginas web con las palabras “Hackeado por los chinos”

## Análisis del CodeRed

 • Debido a defectos en el diseño, especialmente en la semilla estática, CodeRed hizo muy poco daño.

• El gusano CodeRed reside en la memoria. Una máquina puede ser desinfectado simplemente reiniciándola. 

•Una vez reiniciada, la máquina permanece vulnerable a repetir la infección, probablemente debido a que cada nueva máquina infectada sondea la misma lista de direcciones IP.

## CodeRed Versión 2 

• El 19 de julio de 2001 comenzó a circular una variante que era idéntica pero usa una semilla al azar en el generador de número aleatorios.

• Esto tuvo un gran impacto: más de 359.000 máquinas fueron infectadas con CodeRed \(versión 2\) en solo catorce horas. 

• La versión 2 tuvo un impacto mucho mayor en la infraestructura global debido al gran volumen de equipos infectados y las sondas enviadas a infectar nuevos equipos. 

• Causó estragos en algunos dispositivos adicionales con interface web: routers, switches, módems DSL e impresoras. Se bloquearon o reiniciaron cuando una máquina infectada intentó enviarles una copia del gusano.

## CodeRed II

•El 4 de agosto de 2001, un gusano completamente nuevo comenzó a explotar la vulnerabilidad de desbordamiento de buffer en los servidores web Microsoft IIS.

• El código contiene la cadena “CodeRedII” que se convirtió en el nombre. 

• Cuando el gusano infecta a un nuevo equipo, primero determina si el sistema ya ha sido infectado. • Si no, el gusano inicia su mecanismo de propagación, establece una “puerta trasera” en la máquina infectada, queda inactiva durante un día, y luego reinicia la máquina.

• Lanza 300 o 600 hilos \(threads\) en un intento de propagación.

• CodRed II genera una dirección IP aleatoria y luego aplica una máscara para producir las direcciones para sondear. 

• 1/8vos de las veces, sondea una dirección IP completamente aleatoria. 

• 1/2 de las veces, sondea una máquina en el mismo /8 \(la nueva dirección IP tiene los primeros 8 bits iguales\). 

• 3/8vos del tiempo, sondea una máquina en el mismo /16 \(mismos primeros 16 bits\). •

 Evita buscar direcciones en 224.0.0.0/8 \(multicast\) y 127.0.0.0/8 \(loopback\). 

• Las máquinas en la misma red o subred probablemente estén ejecutando software similar.

## Peligro de CodeRed II

 • A diferencia de CodeRed, CodeRedII no estropea las páginas web en las máquinas infectadas ni lanza un ataque de denegación de servicio.

• También a diferencia de CodeRed, CodeRedII no reside en la memoria, por lo que reiniciar una máquina infectada no elimina CodeRedII. 

• Instala un mecanismo para el acceso remoto a nivel raíz a las máquinas infectadas. Esta puerta trasera permite que se ejecute cualquier código, por lo que las máquinas podrían usarse como zombies para futuros ataques.



Tasas de respuesta 

• Los estudios mostraron que la tasa de parcheado de las máquinas vulnerables variaba ampliamente. El ataque comenzó el 19 de julio; el 14 de agosto se estimaron las siguientes estadísticas.

![Una gran cantidad de m&#xE1;quinas sigue siendo vulnerable a la mismo ataque o similar.](../../.gitbook/assets/imagen%20%2814%29.png)

• \(Un informe de Verizon Business\) que cubre 500 investigaciones forenses, que involucran a 230 millones de registros de clientes comprometidos, descubrieron que 9 de cada 10 infracciones atribuidas a ataques de piratería aprovecharon una vulnerabilidad para la cual había una solución disponible al menos seis meses antes del ataque.



