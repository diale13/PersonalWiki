# One-Time Pad

• Un “one-time pad”, inventado por Miller \(1882\) e independientemente por Vernam y Mauborgne \(1917\), es un cifrado teóricamente perfecto. La idea es usar una clave que tenga la misma longitud que el texto plano, y usarlo solo una vez. Se hace un XOR entre la clave y el texto plano, y se obtiene el texto cifrado.

• **Ejemplo**: Dado un mensaje binario de 15-bits

Texto plano: 10110010111001

Clave: 11010001010100

Texto cifrado: 01100011101101

•Observe que el espacio de textos planos, textos cifrados y claves son el mismo, flujos binarias de 15 bits.  


Supongamos que el atacante intercepta el texto cifrado \(“101”\) y sabe que el “One-Time Pad” fue utilizado.

  
• Cada texto plano posible podría ser la imagen previa de ese texto cifrado bajo una clave plausible.

• Por lo tanto, no es posible reducir el espacio de búsqueda.  
  


![Alto raton ni lo copio solo le saco captura.](https://lh4.googleusercontent.com/dzqmD1qZXbT2ceXlgK_m3aP_VXyqZMY6f9fpNNnU0W2yXEHzHpjEH51fjhCBJ2QmFq8_Oxy1L6UFyxHtjgvZU0fQ4TuJZPl8p4opXvJdZlpqtmTwVqVLIYViWohRGbzGN79HINAW)

A lo que va esto es que la gracia de este cifrado es la clave, sin ella no es posible adivinar nada del texto y no es posible analizarlo con criptoanálisis.

El Cifrado de Vernam es un tipo de “One-Time Pad” adecuado para ser utilizado en las computadoras.  


### Distribución de Claves en one time pad 

Dada la necesidad de comunicarse de forma segura, ¿Cómo hacen el remitente y el receptor para acordar una clave secreta que puedan usar en el algoritmo.  


• Si el emisor y el receptor ya tienen un canal seguro, ¿por qué necesitan la clave?

• Si no lo tienen, ¿cómo distribuyen la clave de forma segura?  


![](https://lh6.googleusercontent.com/6z_j-31zO0sQSs62e65AvoALkDbLuQn7JhaNBWzIdUwPgO7oP8o29xpjLm-VLHP_wHs6eeopz43snH6lzewwX-vqls8V1xsEyCqHuXPGQZ_OxJESa9HJMQoSD5VQRh2o_MaRyVmQ)

¿Cómo hacer este pasaje de clave?  
Opción de ejemplo:

• Aproxime el “One-Time Pad” con un generador de números aleatorios \(PRNG\) para generar la semilla que permitirá generar una clave.

• Otra computadora ejecutando el mismo generador de números aleatorios puede generar la clave a partir de la semilla.

• Esto funciona bien porque la secuencia pseudo aleatoria puede tener un período muy largo.

• Es susceptible de comprometerse por alguien que conoce el algoritmo y la semilla.  
  
Osea expones la seed de forma pública porque no es la clave. Ta peligroso igual el envio de eso si alguien conoce el algoritmo.

