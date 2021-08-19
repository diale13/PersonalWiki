# Stored XSS

## Introduccion

Similares a los otros estos ataques persisten. Se colocan en los comentarios o foros donde todo el que entra es victima de esto.

Un comentario que se veria asi:

`<p>This post was extremely helpful.</p>`

Se convertiria en esto de no llevar ningun control:

`<script>/* Bad stuff here... */</script>`

## Lab: Stored XSS into HTML context with nothing encoded

Basta con colocar `<script> alert (1) </script>` en la seccion de comentarios.







