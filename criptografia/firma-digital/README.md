# Firma digital

La base de esto es verificar que quien firma es quien dice ser. Las firmas digitales no solo aparecen en documentos a cifrar sino que en algunos casos hasta en la misma capa de transporte para lo llamado TLS

Supongamos que S envía un mensaje M a R con la firma f\(S, M\). Nos gustaría que la firma tuviera ciertas propiedades: • Infalible: debe ser difícil para cualquier persona que no sea S producir f\(S, M\) • Auténtica: R puede verificar que S firmo el documento M • No Repudio: S no puede negar la producción de la firma • A Prueba de Manipulaciones: después de ser transmitido, M no puede ser modificado • No Reutilizable: la firma no se puede separar y reutilizar para otro mensaje

Las firmas digitales funcionan como firmas físicas. • Idealmente, una firma debería ser: inalterable, autentica, a prueba de manipulaciones, no reutilizable, y no permitir repudio. • Los sistemas criptográficos de clave pública facilitan la creación de firmas digitales.

Simplifcado las firmas digitales son esto:

![](../../.gitbook/assets/imagen%20%2838%29.png)

Ahora eso tiene varios problemas, primero lo que marca es que se verifica si el documento esta intacto sin modificar y eso puede ser super costoso en si mismo. Por ejemplo al mandar un video muy pesado.

![](../../.gitbook/assets/imagen%20%287%29.png)

Una mejora es agregar funciones de hash para verificar unicamente estas, sumado a las clave publica y privada de ambos.

![](../../.gitbook/assets/imagen%20%2826%29.png)

Ahora el siguiente paso es agregar un 3d party que sea la autoridad certificadora, en uruguay puede ser antel.





