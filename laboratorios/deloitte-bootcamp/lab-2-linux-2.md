# Lab 2 - Linux 2

Extra mile de 1: necesitas un adaptador inalambrico si usas VM como yo.

## Redes

* Identificar IP, Mascara de red y Gateway
* Cambiar IP de manera provisional, reiniciar equipo. ¿Se mantiene la ip asignada?
* Cambiar estatica con un editor de texto
* Identificar puertos abiertos en mi equipo
* Asignar una IP por DHCP
* Identificar puertos nuevamente
* Habilitar ssh en maquina y validar que puertos tengo abiertos
* Cambiar dns con echo

### **Identificar IP, Mascara de red y Gateway**

```text
ifconfig 
ip route // para gateway
```

### **Cambiar IP de manera provisional, reiniciar equipo. ¿Se mantiene la ip asignada?**

```text
ip addr add 192.168.4.244/23 dev eth0 valid_lft 10 preferred_lft 10
```

> 192.168.4.244 will be used for 10 seconds. The IP address will be removed from the server after 10 seconds.
>
> _valid\_lft = Valid lifetime_
>
> _preferred\_lft = Preferred lifetime_

### Otra forma de cambiarla de forma provisional \(creo\)

```text
sudo ifconfig “Interfaz” “Nueva dirección IP” netmask 255.255.255.0
ifconfig add default gateway iprouter
```

En el primer ifconfig vemos la interfaz

### **Cambiar estatica con un editor de texto**

```text
sudo nano /etc/network/interfaces
```

Aqui vemos lo siguiente

```text
auto eth0
iface eth0 inet dhcp
```

y lo cambiamos a esto

```text
auto eth0
iface eth0 inet static 
  address 192.168.0.100
  netmask 255.255.255.0
  gateway 192.168.0.1
  dns-nameservers 4.4.4.4
  dns-nameservers 8.8.8.8
```

Seguido de eso 

```text
nano /etc/resolv.conf
nameserver 8.8.8.8 # Replace with your nameserver ip
nameserver 4.4.4.4 # Replace with your nameserver ip

clave hacer lo de abajo

# /etc/init.d/network restart  [On SysVinit]
# systemctl restart network    [On SystemD]
```

### **Identificar puertos abiertos en mi equipo**

```text
netstat 
netstat -tulpn //forma filtrada

ss //otra forma
nmap a mi mismo es otra forma
```

### **Asignar una IP por DHCP**

{% embed url="https://www.youtube.com/watch?v=2H-QVA8a-Fk" %}

Siguiendo el video vamos a 

```text
sudo nano /etc/dhcp/dhcp/dhcp.conf
//alteramos segun foto con ip del dchp y con mac
service isc-dchp-server stop
service isc-dchp-server start
service isc-dchp-server status
```

![](../../.gitbook/assets/imagen%20%28262%29.png)

### **Habilitar ssh en maquina y validar que puertos tengo abiertos**

```text
apt-get install ssh
service ssh start
```

**Se abre el puerto 22 de ssh**

### **Cambiar dns con echo**

```text
cat /etc/resolv.conf //asi vemos el dns actual
vi resolv.conf //lo podemos editar y poner el dns que querramos, como open dns por ejemplo
echo "nameserver 208.69.38.205" > resolv.conf 
```

## Manejo de paquetes

```text
sudo apt update && apt upgrade -y 
sudo apt autoremove
```

### Instalar snort 

```text
sudo apt-get install snort
```

{% embed url="https://youtu.be/LUCnqEw-QiA" %}

### Desinstalar snort y desinstalar completamente snort

```text
sudo apt-get --purge remove <ProgramaDesinstalar>
```

### Instalar desde fuente masscan \(no con pkgmanager\)

{% embed url="https://github.com/robertdavidgraham/masscan" %}

```text
sudo apt-get --assume-yes install git make gcc
git clone https://github.com/robertdavidgraham/masscan
cd masscan
make
make install
make -j4
```

## Manejo de permisos

### Crear nuevo grupo de usuarios

```text
sudo groupadd test1
```

### Crear nuevo usuario y agregarlo a grupo

```text
adduser usr1
sudo usermod -a -G test1 usr1
```

### Crear archivo en /tmp

```text
desde temp
mkdir tempdir
ls -a vemos privilegios
```

### Dar privilegios de escritura en especifico y usuario \(los previamente creados\)

```text
sudo setfacl -m g:Test1:rwx -R /temp/tempdir
```

## Process management

### Visualizar los procesos que se ejecutan en mi equipo

```text
$ ps



PID        TTY     STAT   TIME          CMD

41230    pts/4    Ss        00:00:00     bash

51224    pts/4    R+        00:00:00     ps
```

Muestra snapshot rapida de procesos corriendo

* PID: Process ID
* TTY: Controlling terminal associated with the process \(we'll go in detail about this later\)
* STAT: Process status code
* TIME: Total CPU usage time
* CMD: Name of executable/command

Luego si usamos aux vemos todos los procesos

```text
ps aux
```

### Ejecutar msfconsole

```text
msfconsole
```

### filtrar el proceso msfconsole ¿que PID tiene?

```text
ps aux | grep -i msfconsole
```

### Cambia prioridad del proceso

La prioridad es llamada nice

```text
renice -n 5 -p 31043
31043: old priority 8, new priority 5
```

### Cuanta memoria consume msfconsole?

```text
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
kali        1290 19.1  8.4 941052 171992 pts/0   Sl+  15:13   0:15 ruby /usr/bin/msfconsole
```

### Mata el proceso

```text
kill -9 13829
```



