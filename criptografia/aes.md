# AES

• La sustitución no solo se debe aplicar a los símbolos de un texto.

• El Advanced Encryption Standard \(AES\) contiene un paso de sustitución;

Cada byte en una matriz de 16 bytes se reemplaza por una entrada correspondiente desde una tabla fija de búsqueda de 8 bits.  


![](https://lh6.googleusercontent.com/sYX9VNKLpKykYuoLdxoJ594TvrQjL9l6vf-llKF0CbH3j9uiDRgXv1l971HOazUoT1jiKFZjKmJEmsdkA03CKnSj_17k65kqOCTctR4IuxaHzaOrnji4ZrbOTNLAF20qudnNkfmW)

AES es un cifrado simétrico de 128bits. Es decir que pasa de 128 bits sin cifrar a la misma cantidad cifrado. La clave puede ser de 128, 192, 256 bits lo cual en todos los casos es increíblemente segura.  
AES realiza varios grados de substitucion y de confusion. Bueno lo que hacemos primero es tomar nuestros bits, agruparlos y tenemos una matriz de bytes.  


![](https://lh4.googleusercontent.com/7QCXdWhqTxNd2ORWsqYRwcXFWUMfYvxZMwEQ3hrCzGDXZirNJ9hhpRE31qiMgqCpHi_apycSAEdgHS2iZjs-OwEA81j2L8zKVkRzJ-KBZ8-d0oi5oJREbXN9oCk_9tRdm2ZbKWuq)

El primer paso puede ser desde hacer un xor con la clave a operaciones mas complicadas \(no es tan necesario porque ya es bastante fuerte\)  


![](https://lh4.googleusercontent.com/rHGxdw3lBfADrIx_jEDPhaHQQq3_psWUZZW-HMLVvkeGiGPHuVio58cfISNRz7myLT7e62hChhkp2OcSXfXqWT4LBZluYLLF4xIUx3Me5UA8PaZRp2O259gomshh_Gy3pSzWERET)

La clave también varía de 10 rondas, 12 o 16 para los tamaños mencionados antes y las rondas refieren a iteraciones en la sección roja.

![](https://lh5.googleusercontent.com/S-EjKljQCouORlwA_iieiUo_asWYH7O2X4Jj0LnwU0X62fGRFTiOXeKNx6qN9ImUTecwgwm6pu74fITnUG_Fg0Hp8pDSMi0M0sRW4bK1cgwQHq48jNO7S8gtU5C9-ayx2ZgDUjcB)

El shift es confuso moviendo acorde a las matrices.

Luego para las columnas hacemos un producto de matrices con la key. Eso mueve dentro de la misma columna nuestro byte. Y luego volves a agregar una clave haciendo alguna operacion \(como xor\) y repetis acorde.

Es completamente simetrico es decir que a partir de lo final podes obtener lo primero.  


Esto es lo que se usa para encriptar archivos pues es tan estandarizado que los cpu tienen instrucciones directas para esto. Lo vulnerable es si alguien lo implementa mal pero eso es posible para todo.

## Seguridad del AES

 • AES se incorpora en una gran cantidad de productos de cifrado comercial. El algoritmo es bastante nuevo, pero ha sido sometido a extenso análisis.

 • No se han descubierto fallas, pero eso no significa que ninguna exista.

 • AES es modular y la longitud de la clave puede ampliarse si es necesario. 

• Del mismo modo, se puede aumentar el número de rondas.

