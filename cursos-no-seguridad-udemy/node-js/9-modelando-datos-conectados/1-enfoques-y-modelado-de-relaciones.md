# 1 - Enfoques y modelado de relaciones

## Enfoques

Hay dos enfoques posibles para el modelado de relaciones 

### Referencias \(normalizacion\)

Es un poco el manejo tradicional, por ejemplo un curso tiene un autor entonces le pongo la id del mismo como una asociada.

### Documentos embebidos \(de normalization\)

```text
let course = {
author: {
    name: 'Mosh';
    }
}
```

Vineiendo del enfoque tradicional quizas parece que este enfoque no es tan practico pero al trabajar con una base de datos de documentos es mas eficiente de lo que parece.

Si necesitamos velocidad real usamos esta forma.

### Enfoque Hibrido

Es un poco lo mejor de dos mundos

![](../../../.gitbook/assets/imagen%20%28551%29.png)

## 





