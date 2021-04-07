# Lab 1 - Linux

## Usuarios

* Agregar dos usuarios
* Agregar uno de estos a los sudoers
* Cambiarse entre usuarios y usar sudo para utilizar wireshark
* Desde el usuario sudo hacerse root sin escribir contraseña de root \(usando contraseña del sudoer\)

## Comandos basicos

* Crear un nuevo directorio y dentro de este un archivo junto a tres directorios
* Copiar archivo a segundo directorio
* Mover archivo a tercer directorio
* Borrar el archivo del segundo directorio y el directorio tambien
* Agregar texto usando echo
* Poner al final del mismo algo al texto
* Visualizar el archivo sin usar editores de texto descargados

## Linux Filesystem

* Investigar sobre directorios linux 
* Investigar uso comando man

## Resultados 1

Agregar los dos usuarios

```text
sudo su -      //nos convertimos en root
adduser usr1
//Esto nos retorna para ingresar contraseña en conjunto a datos irrelevantes
adduser usr2
```

Agregar uno al grupo de sudoers

```text
groups usr1 //nos marca que el usuario no esta en el grupo de sudoers
sudo usermod usr1 -aG sudo 
groups usr1 //ahora esta en el grupo de sudo
```

Cambiarse entre usuarios para usar wireshark

```text
su usr1
sudo wireshark --fullscreen //abri wireshark en pantalla completa
```

Convertirse en root

```text
sudo -i
sudo su
```

## Resultados 2



* Crear un nuevo directorio y dentro de este un archivo junto a tres directorios

```text
mkdir temp
cd temp
mkdir d1
mkdir d2
mkdir d3
echo "hola" > texto.txt
```

* Copiar archivo a segundo directorio

```text
cp file.txt d2
```

* Mover archivo a tercer directorio

```text
mv file.txt d3
ls //verificamos que no esta
```

* Borrar el archivo del segundo directorio y el directorio tambien

```text
cd d2 
rm file.txt
cd ..
rm -d d2
```

* Agregar texto usando echo y poner al final del texto algo

```text
cd d3 
echo "mundo" >> file.txt
```

* Visualizar el archivo sin usar editores de texto descargados de tres formas

```text
more file.txt
less file.txt
cat file.txt

nano file.txt
vim file.txt

```

## Filesystem

Ver [curso linux](https://app.gitbook.com/@diegofranggi/s/personalwiki/~/drafts/-MXXaFLfEbVhZF9227yf/curso-ethical-hacking/kali-and-linux/filesystem) para no repetir dentro de wiki.

man lanza ayuda sobre cierto comando sin necesidad de entrar a internet.

