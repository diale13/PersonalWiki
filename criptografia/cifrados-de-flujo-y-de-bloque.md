# Cifrados de flujo y de bloque

• Los algoritmos criptográficos simétricos se diferencian entre los cifrados de flujo y de bloques.

• Los cifrados de flujos convierten un símbolo de texto plano directamente en un símbolo del texto cifrado.

• Los cifrados de bloques cifran un grupo de símbolos de texto plano como un bloque.

• La sustitución simple es un ejemplo de un cifrado de flujo.

• La transposición de columnas en un cifrado de bloques.

• La mayoría de los algoritmos de cifrado simétricos modernos son cifrados de bloques.

• Los tamaños de los bloques varían \(64 bits para DES, 128 bits para AES, etc.\)  


## Cifrado de Flujos \(Stream\) \(Tipo cifrado cesar\)

**Ventajas:**

• Velocidad de transformación: los algoritmos son lineales en el tiempo y constante en el espacio.

• Baja propagación de errores: un error al cifrar un símbolo probablemente no afectará a los símbolos subsecuentes.

**Desventajas:**

• Baja difusión: toda la información de un símbolo de texto plano es contenido en un solo símbolo de texto cifrado.

• Susceptibilidad a inserciones / modificaciones: un interceptor activo que rompe el algoritmo podría insertar texto espurio que parece auténtico.  


## Cifrado de Bloques \(tipo aes\)

**Ventajas**

• Alta difusión: la información de un símbolo de texto plano es difundido en varios símbolos de texto cifrado.

• Inmunidad a la manipulación: dificultad de insertar símbolos sin detección.  


**Desventajas**

• Lentitud del cifrado: se debe acumular un bloque completo antes de que el cifrado / descifrado pueda comenzar.

• Propagación de errores: un error en un símbolo puede dañar el bloque completo.  


## Maleabilidad

Se dice que un algoritmo de cifrado es maleable si las transformaciones en el texto cifrado producen cambios significativos en el texto plano.  


Es decir, dado un texto plano P y el texto cifrado correspondiente

C = E \(P\), es posible generar C1 = f \(C\) para que D \(C1\) = P1 = f’ \(P\)

con funciones arbitrarias, pero conocidas, f y f’.

La mayoría de los cifrados de estructura de bloques modernos no son maleables.  
  


