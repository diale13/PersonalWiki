---
description: >-
  "Very clever" https://www.youtube.com/watch?v=FGhj3CGxl8I 
  https://github.com/mikepound/feistel
---

# Feistel Cipher

Sale en  los 70, por uno de los creadores de DES, el que seria substituido por AES.

Se siguen usando bastante, en todo lo que es menjo de obtencion de claves y paddings para certificados.

Es una estructura para crear cyphers, no es uno en si mismo. Es mas bien un framework.

![Estructura base](../.gitbook/assets/imagen%20%283%29%20%282%29%20%281%29.png)

**La gracia es que las funciones puedan caambiar, los + son XOR, al llegar al final podremos tomar L y R luego de todo el proceso y al ponerlos arriba, invertir las llaves llegar al resultado original!!.**

\*\*\*\*

![Proudcto final](../.gitbook/assets/imagen%20%2843%29.png)

![](../.gitbook/assets/imagen%20%2816%29.png)

**Ahi se desencripta, solamente cambiando el orden de claves y usando la cancelacion del XOR.**

