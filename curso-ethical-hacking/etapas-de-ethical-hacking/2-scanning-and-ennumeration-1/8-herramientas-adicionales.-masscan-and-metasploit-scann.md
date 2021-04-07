# 8 - Herramientas adicionales. Masscan & Metasploit scann

## Masscan

Inicialmente fue creada para escanear todo el internet. Es un muy buen portscaner.

{% embed url="https://github.com/robertdavidgraham/masscan" %}

Tira nmap y masscan a la vez para comparar sus velocidades y resultados

```text
nmap -T4 -p- 192.168.57.134
masscan -p1-655535 --rate 1000 192.168.57.134 
```

Sin el **rate** va SUMAMENTE LENTO. Asi que tenes que ponerlo.

Algo bueno es que lo encuentra y te lo muestra

## Scann con metasploit

![](../../../.gitbook/assets/imagen%20%28225%29.png)

![](../../../.gitbook/assets/imagen%20%28222%29.png)

