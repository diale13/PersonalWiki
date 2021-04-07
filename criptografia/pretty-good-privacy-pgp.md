# Pretty Good Privacy \(PGP\)

Varios algoritmos y productos criptográficos proporcionan encriptación fuerte pero no son articularmente fáciles de usar. 

•Phil Zimmerman tenía el objetivo de proporcionar cifrado fuerte a todos, en la forma de un sistema de encriptación de correo electrónico que es: 

• Extremadamente fuerte, utilizando lo último en algoritmos criptográficos 

• Fácil de usar y accesible para todos.

• PGP es “lo más cercano que se puede llegar a un algoritmo de cifrado de nivel militar”. – Bruce Schneier, Applied Cryptography.

![](../.gitbook/assets/imagen%20%2840%29.png)

## Phil Zimmerman 

[https://www.philzimmermann.com/EN/essays/WhyIWrotePGP.html](https://www.philzimmermann.com/EN/essays/WhyIWrotePGP.html)

• Zimmermann tenía una gran desconfianza hacia el gobierno, y creía firmemente que todos tenían un derecho absoluto a la privacidad. 

• El gobierno generalmente cree que el derecho a la privacidad es limitado por la necesidad del gobierno de leer mensajes bajo ciertas circunstancias. Históricamente, el gobierno restringió el acceso a la encriptación fuerte.

•PGP es una “etapa final” alrededor de las restricciones gubernamentales, y casi llevaron a Zimmermann a la cárcel.

•En 2003, un incidente involucrando PDA Psion incautadas, pertenecientes a miembros de la Brigada Roja italiana, indicaron que ni la policía italiana ni el FBI pudieron decodificar los archivos cifrados con PGP que estaban almacenados en los dispositivos. 

•Un incidente más reciente, en diciembre de 2006 \(ver Estados Unidos vs Boucher\) que involucra agentes de aduana estadounidenses y un PC portátil que fue secuestrado, que supuestamente contenía pornografía infantil indicó que para las agencias del gobierno estadounidense fue “casi imposible” acceder a los archivos cifrados con PGP.



•Zimmermann desarrolló PGP \(Pretty Good Privacy\) a fines de los años 1980 y principios de 1990. Algunas características incluyen: 

•\(1\) – Utiliza los mejores algoritmos criptográficos disponibles como bloque de construcción. 

•\(2\) – Integra estos en un algoritmo de propósito general que es independiente del procesador y fácil de usar.

•\(3\) – El paquete y la documentación, incluido el código fuente, están libremente disponibles en línea. 

•\(4\) – PGP ahora es provisto por Viacrypt en un producto compatible, de bajo costo comercial.

## Sobre PGP

• PGP ha crecido explosivamente y es ampliamente utilizado. 

• \(1\) – Disponible en todo el mundo para Windows, Unix, Macintosh y otros. La versión comercial satisface las necesidades de las empresas requiriendo soporte del vendedor. 

• \(2\) Basado en algoritmos con amplia revisión pública.

_**Cifrado de clave pública**_: RSA, DSS, Diffie-Hellman 

_**Cifrado simétrico**_: CAST-128, IDEA y 3DES 

_**Código Hash**_: SHA-1 

 \(3\) – Aplicabilidad amplia: esquema estandarizado para encriptación, admite una comunicación segura a través de Internet y otras redes.

• \(4\) – No desarrollado ni controlado por ningún gobierno.

• \(5\) – Ahora está en camino de convertirse en un estándar de Internet \(RFC 3156\).

## **PGP servicios básicos:** 

• \(1\) – Autenticación

 • \(2\) – Confidencialidad 

• \(3\) – Compresión 

• \(4\) – Compatibilidad con correo electrónico 

• \(5\) - Segmentación

### Autenticación de PGP 

• Esta es una función de firma digital.

• \(1\) – El emisor crea un mensaje M. 

• \(2\) – El emisor genera un código hash de M. 

• \(3\) – El emisor firma el hash con su clave privada y antepone el resultado al mensaje. 

• \(4\) – El receptor usa la clave pública del remitente para verificar la firma y recuperar el código hash. 

• \(5\) – El receptor genera un nuevo código hash para M y lo compara con el código hash descifrado.

![](../.gitbook/assets/imagen%20%2830%29.png)

### Confidencialidad de PGP 

• PGP proporciona cifrado para los mensajes enviados o almacenados como archivos.

• \(1\) – El emisor genera un mensaje M y una clave de sesión aleatoria K.

• \(2\) – M está encriptado usando la clave K. 

• \(3\) – K se cifra con la clave pública del receptor, y se antepone al mensaje.

• \(4\) – el receptor usa su clave privada para recuperar la clave de sesión. 

• \(5\) – La clave de sesión se utiliza para descifrar el mensaje.

![](../.gitbook/assets/imagen%20%286%29%20%281%29.png)

### Confidencialidad y Autenticación

• Tanto la autenticación como la confidencialidad pueden combinarse para un mensaje dado. 

• \(1\) – Aplicar el paso de autenticación al mensaje original. 

• \(2\) – Aplicar el paso de confidencialidad al mensaje resultante.

## Compresión

 •Por defecto, PGP comprime el mensaje, usando el algoritmo de compresión de ZIP, **después de aplicar la firma y antes del cifrado.** 

Se hace en este orden porque: 

• Es preferible firmar un mensaje sin comprimir para que la firma no dependa del algoritmo de compresión. 

• Las versiones del algoritmo de compresión se comportan ligeramente de manera diferente, aunque todas las versiones son interoperables. 

• El cifrado después de la compresión fortalece el cifrado, ya que la compresión reduce la redundancia en el mensaje.

## Segmentación y Reensamblaje 

•Los sistemas de correo electrónico a menudo restringen la longitud del mensaje. Mensajes más largos deben dividirse en segmentos, que se envían por correos separados. 

• PGP segmenta automáticamente los mensajes que son demasiado grandes. Esto se hace después de todos los demás pasos, incluida la conversión de radix-64. Por lo tanto, la firma y la clave de sesión aparece solo una vez.

 • En el extremo receptor, PGP elimina los encabezados del correo y vuelve a armar el mensaje de sus piezas componentes.

## Gestión de Claves

•PGP hace uso de cuatro tipos de claves: clave simétrica única de la sesión, claves públicas, claves privadas, claves simétricas basadas en frases de contraseña.

• Claves de sesión: se usa una vez y se genera para cada nuevo mensaje. 

• Claves públicas: se usan en cifrado asimétrico 

• Claves privadas: se usan en cifrado asimétrico, junto a las anteriores 

• Claves basadas en frases de contraseña: se usan para proteger claves privadas. 

• Un solo usuario puede tener múltiples pares de claves pública / privada.

Resaltando:

• En PGP, las claves de sesión y las claves basadas en frase de contraseña se generan en el momento, se usan una vez y son descartadas. 

• Las claves públicas y privadas son persistentes y deben conservarse y gestionarse. Recordar que un usuario puede tener múltiples pares de claves pública / privada.

### Generación de Clave de Sesión

•Cada clave de sesión está asociada con un solo mensaje y solo se usa una vez. El tamaño de la clave depende del algoritmo de cifrado E. Por ejemplo: CAST-128: 128 bits, 3DES: 68 bits, etc. 

• El algoritmo de cifrado E se usa para generar una nueva clave de n bits a partir de una clave de la sesión anterior y dos bloques de n / 2 bis que se generan en base a las pulsaciones de las teclas del usuario, incluida la sincronización de las pulsaciones de las teclas. Los dos bloques se encriptan usando E y la clave anterior, y combinados para formar la nueva clave.

### Generación de Clave Pública / Privada

 •Para las nuevas claves RSA, se genera un número impar “n” de tamaño suficientemente grande \(generalmente mayor a 200 bits\) y se prueba su primalidad. Si no es primo, se repite el proceso con otro número generado aleatoriamente, hasta que se encuentre un número primo.

•Los números primos aparecen en las cercanías de “n” aproximadamente cada números.

•Ya que podemos excluir los números pares, para encontrar un primo de alrededor de 200 bits, toma aproximadamente intentos.

•Esta es una operación costosa, pero se realiza relativamente con poca frecuencia.

#### Encriptando la Clave Privada 

•La clave privada se almacena cifrada con una frase de contraseña proporcionada por el usuario:

• \(1\) – El usuario selecciona una frase de contraseña para encriptar claves privadas.

• \(2\) – Cuando se genera un nuevo par de claves pública / privada, el sistema pregunta por la frase de contraseña. Usando el SHA-1, se genera un código de hash de 160-bits a partir de la frase de contraseña, que se descarta. 

•\(3\) – La clave privada se cifra con CAST-128 con 128 bits del código hash como clave. La clave se descarta. 

•Cuando el usuario quiera acceder a la clave privada, debe proporcionar la frase de contraseña.

## Gestionando Pares de Claves 

• Dado que un usuario puede tener múltiples pares de claves pública / privada, ¿Cómo sabemos qué clave pública se utilizó para encriptar un mensaje? 

• **Enviar la clave pública junto con el mensaje**. Es ineficiente, ya que la clave puede ser de miles de bits. • Asociar un ID único con cada par de claves y enviarlo con el mensaje. Requeriría que todos los remitentes conozcan el mapeo de claves a IDs para todos los destinatarios.

• **Generar un ID que sea único para un usuario determinado**. Esta es la solución de PGP. Utiliza los 64 bits menos significativos de la clave como la identificación. 

• **Esto es utilizado por el receptor para verificar que tenga esa clave en su “llavero”.** La clave privada asociada se utiliza para el descifrado.

### Llavero privado

•Cada usuario mantiene dos estructuras de datos de claves: una llavero de clave privada para sus propias pares de claves públicas / privadas, y un llavero de claves públicas para las claves públicas de los corresponsales.

El llavero de claves privadas es una tabla de filas que contiene:

• Marca de tiempo: cuando se generó el par de claves. 

• ID de la clave: 64 dígitos menos significativos de la clave pública. 

• Clave pública: la parte pública de la clave. 

• Clave privada: la parte privada, encriptada usando una frase de contraseña. 

• ID de usuario: generalmente la dirección de correo electrónico del usuario. Puede ser diferente para diferentes pares de claves.

### Llavero Público 

• Las claves públicas de otros usuarios se almacenan en el llavero de claves públicas del usuario. • Esta es una tabla de filas que contiene \(entre otros campos\): 

• Marca de tiempo: cuando se generó la entrada.

• ID de clave: 64 dígitos menos significativos de la clave. 

• Clave pública: la clave pública para la entrada. 

• ID de usuario: identificador para el propietario de esta clave. Múltiples identificaciones pueden estar asociado con una sola clave pública. 

• La clave pública puede indexarse mediante ID de usuario o ID de clave.

### Recuperando una Clave Privada 

•Siempre que PGP deba usar una clave privada, debe descifrarla, por ejemplo, supongamos que R recibe un mensaje cifrado por KR. 

•\(1\) – PGP recupera la clave privada encriptada del receptor del llavero de claves privadas, usando el campo ID de clave como un índice, que viene incluido en la clave de sesión del mensaje. 

•\(2\) – PGP solicita al usuario la frase de contraseña para recuperar la clave privada no encriptada. 

•\(3\) – PGP recupera la clave de sesión y descifra el mensaje

### Validación de la Clave Pública 

• Asociado con cada clave pública en el llavero de claves públicas del usuario, hay un campo de legitimidad de la clave que indica la medida en que PGP confía que esta es una clave pública válida para este usuarios

 • La legitimidad se determina a partir de certificados y cadenas de certificados, de la evaluación del usuario de la confianza que se asignará a la clave y varias heurísticas para calcular la confianza.

### Revocación de Claves Públicas

 • Un usuario puede querer revocar una clave pública porque: • se sospecha que está comprometida, • para limitar el periodo de uso de la clave. 

• El propietario emite un certificado de revocación de clave firmado. Se espera que los destinatarios actualicen sus llaveros de claves públicas.

### Resumen

• Cada usuario de PGP debe administrar sus propias claves privadas y las claves públicas de otros. • Estas se almacenan en llaveros de claves separadas.

• Las claves privadas están protegidas por encriptación; las claves pública son almacenadas con los certificados que acreditan su confiabilidad.

• Las llaves pueden ser revocadas.

















