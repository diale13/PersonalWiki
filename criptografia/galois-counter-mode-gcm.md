# Galois/Counter Mode \(GCM\)

![](../.gitbook/assets/imagen%20%284%29.png)

Es la mejora al cipher block chainign, es mas parecido al ECB igual. La gracia es poner una base "nunce" obviamente tendra que ser mas compleja, y incrementar la misma por uno para cada bloque. De igual forma se requerie la clave k para cada funcion y al obtener un resultado se hace XOR con el bloque. Basicamente se convierte un block cipher a un stream cypher \(ver cifrados de flujo y de bloque\). Ahora este modo tiene las ventajas de ECB y ninguna de sus desventajas. Ademas de que es summente facil de descifrar \(conociendo todo\).

Para eso se hace denuevo el cifrado, pero se hace XOR con Ci. Con eso se obtiene Mi por propiedades del XOR.





