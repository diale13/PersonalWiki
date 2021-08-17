# Reflected XSS

##  Intro

Se trata del tippo de xss que ocurre cuando una aplicacion recibe una peticion HTTP que incluye informacion que la hace actuar de forma insegura:

 `https://insecure-website.com/search?term=gift`

Puede ocurrir en un parametro, en un campo a ingresar texto que se refleja como un buscador: 

 `<p>You searched for: gift</p>`

 `https://insecure-website.com/search?term=<script>/*+Bad+stuff+here...+*/</script>`

  `<p>You searched for: <script>/* Bad stuff here... */</script></p>`

 De enviarse un link asi una victima puede ser llevada a ejecutar acciones maliciiosas sin saberlo

## Lab1- Reflected XSS into HTML context with nothing encoded

En este lab se nos presenta un buscador al que inyectamos el siguiente codigo JS

![](../../.gitbook/assets/imagen%20%28601%29.png)

## Impacto de XSS Reflejado

De ejecutar un script en el navegador de una victima un atacante puede:

* Hacer acciones maliciosas
* Ver informacion que el usuario no necesariamente ve
* Modificar informacion que el usuario puede modificar
* Iniciar interacciiones con otras aplicaciones de forma tal  que parecen oriiginar de la victima





