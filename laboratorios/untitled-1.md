# Lab 9 - Forensics \(cont\)

## Introduccion

![Analizar imagen](../.gitbook/assets/imagen%20%28465%29.png)



### ¿Que son los mnemonics \(instrucciones basicas\) de lenguaje ensamblador?

Son las instruccions mas simples en el lenguaje assembly.  Lo que hacen es agrupar diferentes **opcodes** que con el fin de ejecutar un proposito. Se reservan los mnemonic para clases de opcodes con mismas funciones.

### ¿Que es un opcode?

Es una instruccion para la maquina. Usualmente van acompañados de algun tipo de dato a procesar. Varian acorde a la arquitectura y al hardware junto a la CPU. 

### Mnemonics cont

#### Inc <a id="inc"></a>

*  Increment the memory variable COUNT

```text
INC COUNT
```

#### Mov <a id="mov"></a>

*  Transfer the value 48 in the memory variable TOTAL

```text
MOV TOTAL, 48
```

*  Transfer the value 10 to the AL register

```text
MOV AL, 10
```

#### Add <a id="add"></a>

*  Add the content of the BH register into the AH register

```text
ADD AH, BH
```

*  Add 10 to the variable MARKS

```text
ADD MARKS, 10
```

#### And <a id="and"></a>

*  Perform AND operation on the variable MASK1 and 128

```text
AND MASK1, 128
```

Al hacer un JMP por ejemplo realiza lo siguiente

![](../.gitbook/assets/imagen%20%28472%29.png)



### ¿A que refiere con el concepto de endianess?

### ¿Que es el registro de la cpu y cuales registros existen?

### ¿Que es una llamada a funcion y que tipos de llamada existen?

### ¿Que es el prologo y el epilogo en este contexto?

### ¿Que instrucciones existen en el ensamblador para hacer comparaciones y tomar desiciones?

### ¿Que instrucciones existen en un ensamblador para definir el flujo del codigo?

## Compila y desensambla los siguientes codigos

![](../.gitbook/assets/imagen%20%28463%29.png)



