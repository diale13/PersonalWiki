# Windows

## Variables de ambiente

### Generar script que permita identificar puertos de la maquina virtual metasploitable

```python
nmap -sS 192.168.100.135
```

### Agrega ese script a tus variables de ambiente

```text
C:\Users\Diego> $env:Path += "C:\Users\Diego\Documents\Det-Res\scripts;"
```

### Ejecutalo desde un path diferente

```text
C:\Users\Diego> scriptScann.ps1
```

![](../../.gitbook/assets/imagen%20%28360%29.png)

