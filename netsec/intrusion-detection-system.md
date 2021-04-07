# Intrusion detection system

• Un sistema de detección de intrusos \(IDS\) puede analizar los patrones de tráfico y reacciona a patrones anómalos. Sin embargo, a menudo no hay nada aparentemente incorrecto pero el volumen de solicitudes. • Tener en cuenta que un IDS es intrínsecamente reactivo; el ataque ya ha comenzado cuando el IDS actúa.

### Errores en la Detección de Intrusos

• Hay dos tipos de errores cuando se considera cualquier sistema de detección de intrusos. • Falso negativo: un ataque genuino no es detectado. • Falso positivo: el comportamiento inofensivo se clasifica erróneamente como un ataque. • ¿Qué crees que es un problema mayor?

• Un sistema de detección de intrusos es: 

• **Exacto**: si detecta todos los ataques genuinos 

• **Preciso**: si nunca informa un comportamiento legítimo como un ataque. 

• Es fácil hacer un IDS que sea exacto o preciso. 

• Es difícil hacer ambas cosas a la vez.

• Un ataque no detectado podría ocasionar problemas graves. Pero falsas alarmas frecuentes pueden provocar que el sistema se desactive o se ignore. Un IDS perfecto sería tanto exacto y preciso. • Estadísticamente, los ataques son eventos bastante raros. • La mayoría de los sistemas de detección de intrusos sufren de la tasa básica de falacia \(engaño o mentira que se esconde bajo algo\)

### Tasa básica de Falacia

• Supongamos que solo el 1% del tráfico son en realidad ataques y que la exactitud de detección del IDS es del 90%. ¿Qué significa eso? • El IDS clasifica un ataque como un ataque con una probabilidad del 90% • El IDS clasifica una conexión válida como un ataque con una probabilidad del 10% • Hay aproximadamente un 92% de posibilidades de que una alarma detectada sea falsa.

### Comparación con Firewalls

Si bien ambos están relacionados con [seguridad en redes](https://es.wikipedia.org/wiki/Seguridad_de_la_informaci%C3%B3n) de información, un IDS, difiere de un cortafuegos, en que este último generalmente examina exteriormente por intrusiones para evitar que estas ocurran.

Un cortafuegos limita el acceso entre redes, para prevenir una intrusión, pero no determina un ataque que pueda estar ocurriendo internamente en la red. Un IDS, evalúa una intrusión cuando esta toma lugar, y genera una alarma. Un IDS además observa ataques que se originan dentro del sistema. Este normalmente se consigue examinando comunicaciones, e identificando mediante heurística, o patrones \(conocidos como firmas\), ataques comunes ya clasificados, y toma una acción para alertar a un operador. Los sistemas de detección de intrusiones son fundamentales para proteger adecuadamente en el perímetro de la red, muy cerca del cortafuegos, ya que trabajan conjuntamente para impedir que usuarios malintencionados puedan acceder a una organización.

