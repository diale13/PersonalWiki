# Cifrado de Vigenère

• El cifrado de Vigenère es un ejemplo de un cifrado polialfabético, a veces llamado cifrado de clave en ejecución porque la clave es otro texto.

• Comienza con un texto clave: “monitors to go to the bathroom” y un texto plano para ser

encriptado: “four score and seven years ago”. Alinear los dos textos, posiblemente quitando los espacios:  


![](https://lh6.googleusercontent.com/Ipa--5s9prUSpXUTdfMxJYAmZze7hE3nQzV2o3PFV-4iNMUrsIyEEjMnZqhvJaLlNlodHb3Ah_ZIM-UATW5ZyaTerhHiSlFni4aIFDXkrcXh6PunvTqpEgfuPEbSUZrsiUKk9Hav)

Luego use los pares de letras para buscar el cifrado en una tabla \(llamada Tabla de Vigenère o tabla recta\).  


![](https://lh6.googleusercontent.com/aNYYh6s71mrcC6gzBPig_s7kYVs8ZNZE3mAjbJhI-kn8kQ8lyhvqnfAkxAHxMaffg88GCz2bMFcVa6RoS6pI0sXLBAaRJtdDtYeqdoDPz9WLPL3uZbRE-Jd_J_g7ClL5tifuXrL7)

Bajandolo a tierra:   


Si tu clave es MECA y queres codificar “criptogramas resueltos” los intercalas asi 

![](https://lh4.googleusercontent.com/Go8uxM9GLA6yyiZ9Mugjvrxt4q_Wa19jewuypgJNuG3acull_gsOrMDA1UAxeYFcimge1FC64TFzsYFjm2RGDPV2fll4R1uFQW4KC6st-ql0y9SRxLnQZam-F_by5mm4zAFsrD8m)

![](https://lh4.googleusercontent.com/u-IfdX0SQZAeTVHfxj3btD8aqCBV1KDRaEsFMbwPGhQTHnRv0t0AZuAGfXP2gtDCe0CEVtCmSgu3UtopenSfMxGASDGf51nKqewKk_VOi3Yljr0920kmvfDPbxPW8OoazCGxcrS0)

Luego cifras asi:

![](https://lh5.googleusercontent.com/Sey62-6s1agC_lYc7YsCIKS_Hd3UtDT1p7XwSpK8p5X2WC4yyl85_aMdnehh_zw1VDMU3kZDRvW31Ht-inZbtWFgO3lDFmG3hEnLbBtwgGID46xc812I4WtVY5bzwHtVxxd0fogm)

Y luego es tan sencillo como ir en la tabla haciendo el proceso inverso. Obviamente requeris la clave.  


Analizando las debilidades:  


• El Cifrado de Vigenère selecciona uno de los veintiséis diferentes cifrados de

César, dependiendo de la letra correspondiente a la clave.

• La ejecución de cifrados de claves es susceptible de análisis estadístico. Tanto la clave como el texto plano son flujos en Inglés y también tiene las características de la entropía del Inglés.

• En particular, las letras A, E, O, T, N, I, componen casi el 50% del texto en Inglés.

Por lo tanto, en aproximadamente el 25% de los índices, se puede esperar que coincidan.

• Este es un ejemplo de una regularidad en el texto cifrado que no se esperaría simplemente por casualidad.  
  


