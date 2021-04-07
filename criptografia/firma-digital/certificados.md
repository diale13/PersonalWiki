# Certificados

Certificados 

• Un certificado es el equivalente electrónico de una “carta de introducción” o de “presentación”. 

• Un certificado se construye con firmas digitales y funciones de Hash.

 • Una clave pública y la identidad de un usuario están vinculadas dentro de un certificado, firmado por una autoridad certificadora, que avala la precisión de la unión.

![](../../.gitbook/assets/imagen%20%2821%29.png)

Como podría funcionar

 • Supongamos que X es el presidente de una compañía; Y es su subordinado.

 • Cada uno tiene un par de claves públicas RSA. 

• Esto último se convierte en el certificado de Y, firmado por X.



## Validando el Certificado

 • Supongamos que Y le presenta a Z el certificado: 

![](../../.gitbook/assets/imagen%20%2839%29.png)

• ¿Qué hace Z con esto? ¿Qué ha aprendido Z?

 • El mensaje certifica el vinculo entre Y y la KY

 • X es la autoridad certificante • Los elementos de datos Y y KY no han sido alterados o corrompidos

 • Este esquema supone que Z tiene una clave pública confiable de X, para verificar la firma de X.

## Resumen

• Los certificados son necesarios para establecer una red de confianza en un entorno distribuido. 

• Una persona de confianza puede “avalar” a otra parte mediante la certificación del vínculo entre la identidad y la clave pública.

• Un tercero puede verificar la validez del vinculo.



## Certificados y confianza 

• Lo certificados abordan la necesidad de construir una red de confianza en sistemas informática

• ¿Cómo establecen las entidades mutuamente sospechosas una relación de confianza?

•Una forma es confiar en que un tercero conocido “avale” a una o a ambas partes.

• En un contexto digital, esto normalmente significa certificar el vinculo entre la identidad y la clave pública.



## Cadena de Confianza 

• Supongamos que Y tiene un certificado firmado por X, pero Y ahora necesita certificar a W. Él podría producir un certificado para W y anexar el certificado de X para ello.

• Esto crea una cadena de confianza de W a Y a X. 

• Idealmente, la cadena tiene sus raíces en alguna autoridad irrecusable.

## Autoridad Certificante 

• Una entidad puede obtener la autoridad para certificar en virtud de la posición, en lugar de la familiaridad.

• En transacciones fuera de línea, esto podría ser un notario público, un oficial personal, un oficial de seguridad de una empresa, etc. 

• En Internet, varios grupos sirven como “Autoridad Raíz Certificante”. Verisign, SecureNet, Baltimore Technologies, Deutsche Telecom, Certiposte, Agesic, y muchos otros.



## Certificados X.509

 • X.509 es un estándar ampliamente utilizado para certificados digitales. 

• Un certificado X.509v3 tiene los siguientes componentes: 

• \(1\) – Versión: versión de X.509 utilizada

 • \(2\) – Número de serie: único entre los certificados emitidos por este emisor 

• \(3\) – Identificador del algoritmo de firma: Identifica el algoritmo y parámetros utilizados para firmar el certificado 

• \(4\) – Nombre distinguido del emisor: con número de serie, hace único a cada certificado • \(5\) – Intervalo de validez: tiempo de inicio y fin de la validez

 • \(6\) – Nombre distinguido del sujeto: identifica la persona que esta siendo “avalada”.

 • \(7\) – Información de la clave pública del sujeto: identifica el algoritmos, los parámetros y la clave pública.



•\(8\) – ID único del Emisor: se utiliza si el nombre completo de un Emisor es reutilizado alguna vez 

• \(9\) – ID único del Sujeto: igual que el campo 8, pero para el sujeto

 • \(10\) – Extensiones: información específica de la versión utilizada

 • \(11\) – Firma: identifica el algoritmo, y los parámetros y la firma \(hash encriptado de los campos 1 a 10\) 

## Para validar el certificado, el usuario:

 • Obtiene la clave pública del emisor para el algoritmo \(3\)

 • Verificar la firma \(11\) • Vuelva a calcular el hash y comparar con el valor recibido

 • Verificar el intervalo de validez

