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

**CMD add to admin**

```text
net localgroup Administrators user1 /add
```

**Powershell add to admin**

```text
Add-LocalGroupMember -Group 'Administrators' -Member user2 -Verbose
```

