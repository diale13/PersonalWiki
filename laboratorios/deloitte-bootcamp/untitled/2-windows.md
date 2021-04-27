---
description: Linux >> Windows
---

# 2 - Windows

## Usuarios

### Agregar dos usuarios con cmd y despues con powershell

**Cmd:**

```text
net user user1 user1pass /add
net user user2 user2pass /add
```

**PowerShell**

```text
New-LocalUser -Name "U1" -Description "powershell" -NoPassword
New-LocalUser -Name "U2" -Description "powershell" -NoPassword
```

### **CMD add to admin**

```text
net localgroup Administrators user1 /add
```

### **Powershell add admin**

```text
Add-LocalGroupMember -Group 'Administrators' -Member user2 -Verbose
```

## Comandos basicos

### Crear directorio y ahi un archivo

4 formas

```text
new-item <path of directory suppose c:\dir1> -itemtype directory
New-Item -Path '\\Shared\TestFolder\testfile1.txt' - ItemType File
```

```text
$fso = new-object -ComObject scripting.filesystemobject
$fso.CreateFolder("path of directory suppose C:\test1")
```

```text
md <path of directory suppose c:\test5>
```

```text
[system.io.directory]::CreateDirectory("path of directory suppose c:\test5")
```

### Copoar archivo a otro directorio previamente creado

```text
Copy-Item "C:\Diego\Logfiles\diego.log.txt" -Destination "C:\temporal\"
```

### Mover a tercer directorio

```text
Move-Item -Path C:\test.txt -Destination E:\Temp\text.txt
```

### Borrar archivo y borrar segundo directorio

```text
Remove-Item –path c:\testfolder\ remove-item * -include *.mp4 –recurse
```

Borramos todo los mp4 por ejemplo

### Agregar texto con powershell

```text
Set-Content -Value "Hello, world!" -Path .\Potato.txt 
```

### Apend de texto con powershell

```text
Add-Content -Value "Potato apended" -Path .\Potato.txt 
```

### Ver contenido desde powershell

```text
Get-Content -Path .\Potato.txt 
```

### Limitar lineas de salida con powershell

```text
out-file -filepath C:\TestFolder3\Potato.txt -inputobject $a -encoding ASCII -width 100
```

## Windows filesystem

### Cuantos anillos tiene?

![](../../../.gitbook/assets/imagen%20%28284%29.png)

### API de windows

Es la interfaz de programacion de aplicaciones de Windows. Es usada por casi todos los programas.

### dll

Bibliotecas de binarios compilados. Permiten la ejecucion de codigo.

### Registro de windows

Base de datos que se sitúa en el disco duro, guarda ajustes de programas y de Windows, además de diversos drivers y también hardware del ordenador.

### Ayuda en powershell

get-help

