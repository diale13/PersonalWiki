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

## Manejo de procesos

### Ver procesos ejecutando en mi equipo, asignar a una tabla de prioridad

```text
C:\Users\Diego> Get-Process

Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
    373      21    18180      29108       0,11   1172   1 ApplicationFrameHost
    147       9     1848       6552              3732   0 armsvc
    152      11     7288       8248              3692   0 atkexComSvc
    560      15    18272      21880      33,09  10796   0 audiodg
    580      30    67464       1740       0,28  11096   1 Calculator
    160       7     1560       7812       0,03  12708   1 CompPkgSrv
    122       8     6512        996       0,00   2164   1 conhost
    134       9     6600      10752              3024   0 conhost
    270      15     4596      15956       0,09   4636   1 conhost
    123       9     6580      10556              6384   0 conhost
     88       9     1416       5224              6652   0 crashpad_handler
```

### Ejecutar porcesshacker

```text
C:\Program Files\Process Hacker > ProcessHacker
```

### Filtrar proceso de processhacker ¿Que PID tiene?

```text
C:\Program Files\Process Hacker > Get-Process processhacker

Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
   1197      20    22300      33912       2.61  21720   9 ProcessHacker
```

### Cambiar prioridad al proceso

Before:

```text
PriorityClass: High

ProcessName                  Id   HandleCount WorkingSet64
-----------                  --   ----------- ------------
ProcessHacker             21720          1198     37769216
Registry                    148             0     79958016
RtkAudUService64           4212           329     10080256
```

Cambiando:

```text
C:\Program Files\Process Hacker>  Get-Process processhacker | ForEach-Object{ $_.PriorityClass = 'BelowNormal'}           
```



```text
C:\Program Files\Process Hacker> gps | where {$_.priorityclass -eq 'BelowNormal'} | select PriorityClass, ProcessName, Id
```

### Cual es el consumo de cpu del proceso?

```text
gps | where {$_.priorityclass -eq 'High'} | select PriorityClass, ProcessName, Id, CPU

PriorityClass ProcessName      Id      CPU
------------- -----------      --      ---
         High ProcessHacker 13924 4.484375
```

Mata al proceso y ejecuta notepad

```text
C:\Program Files\Process Hacker> taskkill.exe /f /pid 13924
SUCCESS: The process with PID 13924 has been terminated.
notepad
```

### Sigue los pasos realizados con pawershell pero haciedno uso de processhacker y toma notepada como proceso para trabajar.

TODO





![](../../.gitbook/assets/imagen%20%28367%29.png)

