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

### Copoar archivo a otro directorio previamente creado

### Mover a tercer directorio

### Borrar archivo y borrar segundo directorio

### Agregar texto con powershell

### Apend de texto con powershell

### Ver contenido desde powershell

### Limitar lineas de salida con powershell



## Windows filesystem

![](../../.gitbook/assets/imagen%20%28280%29.png)







