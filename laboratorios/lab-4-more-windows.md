# Lab 4 - More Windows

## Redes

### Identificar ip del equipo, mascara y gateway \(ps y cmd\)

```text
ipconfig
```

### Cambiar ip del equipo \(ps\)

```text
New-NetIPAddress –InterfaceAlias “Wired Ethernet Connection” –IPv4Address “192.168.0.1” –PrefixLength 24 -DefaultGateway 192.168.0.254
```

### No lo pide pero aca esta el dns

```text
Set-DnsClientServerAddress -InterfaceAlias “Wired Ethernet Connection” -ServerAddresses 192.168.0.1, 192.168.0.2
```

### Identificar puertos abiertos del equipo \(cmd y ps\)

```text
netstat -a
```

#### Powershell

```text
Get-NetTCPConnection | ? {$_.State -eq "Listen"}
```

### Powershell remoting para enviar comandos a computadora remota \(?\)

{% embed url="https://docs.microsoft.com/en-us/powershell/scripting/learn/ps101/08-powershell-remoting?view=powershell-7.1" %}

## Manejo de paquetes

### Listar paquetes \(nuggets\) disponibles mediante manejador de paquetes en ps

```text
Get-Package
```

### Instalar nugget de preferencia usando manejador de paquetes

```text
Install−PackageProvider −Name Nuget −Force
```

### Que es chocolatey?

Es un manejador de paquetes como yum o apt, pero para windows.

### Instalar chocolatey

```text
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

### Instalar processhacker con chocolatey

Aca la lista de disponibles a instalar

{% embed url="https://community.chocolatey.org/packages" %}

```text
choco install processhacker 
```

## Manejo de permisos

Crear nuevo grupo de usuarios \(cmd y ps\)

Nuevo usuario y agregarlo al grupo

Crear archivo en temp \(cmd y ps\)

Dar privilegios de escritura en un grupo especifico y usuario 

Validar que no se pueda escribir al archivo con otro usuario 

