# Algoritmos Simétricos vs Asimétricos

Hay dos tipos básicos de cifrados:

• **Algoritmos simétricos**: \(también llamado de “clave secreta”\) utilizan la misma clave para cifrado y descifrado.

• **Algoritmos asimétricos**: \(también llamado de “clave pública”\) utilizan diferentes claves para cifrado y descifrado.  
  
Para cualquier enfoque de cifrado, existen dos desafíos principales:

• Distribución de claves: cómo transmitimos las llaves a quienes las necesitan para establecer una comunicación segura

• Gestión de claves: ¿Cómo podemos preservar su seguridad y hacer que estén disponibles cuando sea necesario?  


### Cifrado Asimétrica

En el cifrado asimétrico o de clave pública, se utilizan diferentes claves para el cifrado y el descifrado. Cada sujeto S tiene una clave Ks públicamente divulgada \(“clave pública de S”\) que cualquiera puede usar para cifrar o descifrar, y una clave privada Ks¯¹ \(“clave privada de S”\). La relación es:  


![](https://lh3.googleusercontent.com/m9NkQ8dPwUrcB_OrQiZppX3sibS1fkTJt_Y0Wym4WIrwlU-Dxp6iHrM00Rc0GiDMOBMhs2ofwE0oD2woOJwzosFIDLpdhOGqqsS2iFHgm-9yL_Jw_fAesiGbCqq6kw_Y9wUXCOx1)

Cualquier persona que desee enviar un mensaje M confidencialmente a S envía {M} Ks. Solo el titular de Ks¯¹ puede descifrar este mensaje. El cifrado asimétrico resuelve en gran medida el problema de distribución de claves.

### Cuantas Claves: Cifrado Simétrico

Dado un sistema simétrico con n usuarios, ¿cuántas claves se necesitan para unacomunicación segura entre pares?

 

![](https://lh6.googleusercontent.com/FB-DB9BGtpw93KKKhOuLQvMGJp7hBZGo67CvOZNGtA0MMlg81DcrIU6GEtblHD2LxqBwbSp_iJSmlVjRxFrBIcCvNdNkMiFGOGJmoZNeSqes3gluJh7JOSrxRb5rjkZkE50kzc2g)



Interacciones entre sujetos es la misma cantidad de claves que necesitamos para cifrado simetrico  
Cada vez que se agrega un nuevo usuario al sistema, necesita compartir una nueva clave con cada usuario anterior. Por lo tanto, para n usuarios, tenemos 1 + 2 + . . . + \(n – 1\) = n \(n – 1\) / 2 claves.  
Esto es claves de orden O\(n²\).  


### Cuantas claves: Cifrado Asimétrico

Dado un sistema asimétrico de n usuarios, ¿cuántas claves se necesitan para la comunicación segura entre pares?

• Cada vez que se agrega un nuevo usuario al sistema, sólo se necesita una clave pública y una clave privada.

• Por lo tanto, para n usuarios, tenemos 2n claves, que es O\(n\).

• Dependiendo del algoritmo, cada usuario puede necesitar pares separados

Para la confidencialidad y la firma, es decir, 4n claves, que todavía es de orden O\(n\).

## Características de las claves

Normalmente, en un sistema de cifrado simétrico las claves son:

• \(1\) – texto de K-bits generada al azar

• \(2\) – fácil de generar

• \(3\) – no tienen propiedades especiales  


En un sistema de clave pública, las claves:

• \(1\) – tienen una estructura especial \(por ejemplo, son números primos grandes\), y

• \(2\) – son caros de generar.

• Los tamaños de las claves no son comparables entre los dos enfoques.

• Una clave simétrica de 128 bits puede ser equivalente en fortaleza a una clave

pública de 3000-bits  


### Resumen

• Con el cifrado simétrico, la seguridad requiere que cada par de usuarios compartan una clave secreta.

• En un sistema asimétrico, cada usuario tiene un par de claves pública / privada.

• Las claves en los dos enfoques tienen características muy diferentes y no son directamente comparables.

