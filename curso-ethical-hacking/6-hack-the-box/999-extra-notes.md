# 999 - Extra notes

## Scanning

* Podemos no usar el -A o sin el -p- que escanea todos los puertos. Entonces escaneas primero sin eso Y DESPUES recien usar el -A y p.
* Podes usar masscan primero y luego nmap despues.

## Meterpreter

Hay veces que es recomendado utilizar un migrate para pasarnos entre procesos

### migrate

Using the **migrate** post module, you can migrate to another process on the victim.

```text
meterpreter > run post/windows/manage/migrate 

[*] Running module against V-MAC-XP
[*] Current server process: svchost.exe (1076)
[*] Migrating to explorer.exe...
[*] Migrating into process ID 816
[*] New server process: Explorer.EXE (816)
meterpreter >
```

