# Lab 9 - Forensics \(cont\)

## Introduccion

![Analizar imagen](../.gitbook/assets/imagen%20%28465%29.png)



### ¿Que son los mnemonics \(instrucciones basicas\) de lenguaje ensamblador?

Son las instruccions mas simples en el lenguaje assembly.  Lo que hacen es agrupar diferentes **opcodes** que con el fin de ejecutar un proposito. Se reservan los mnemonic para clases de opcodes con mismas funciones.

### ¿Que es un opcode?

Es una instruccion para la maquina. Usualmente van acompañados de algun tipo de dato a procesar. Varian acorde a la arquitectura y al hardware junto a la CPU. 

Estan determinados segun la siguiente tabla, cada combinacion de assembler corresponde a un opcode, parametros y ciclos de la cpu:

| \_ | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | 00 | 01 | 02 | 03 | 04 | 05 | 06 | 07 | 08 | 09 | 0A | 0B | 0C | 0D | 0E | 0F |
| 1 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 1A | 1B | 1C | 1D | 1E | 1F |
| 2 | 20 | 21 | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 2A | 2B | 2C | 2D | 2E | 2F |
| 3 | 30 | 31 | 32 | 33 | 34 | 35 | 36 | 37 | 38 | 39 | 3A | 3B | 3C | 3D | 3E | 3F |
| 4 | 40 | 41 | 42 | 43 | 44 | 45 | 46 | 47 | 48 | 49 | 4A | 4B | 4C | 4D | 4E | 4F |
| 5 | 50 | 51 | 52 | 53 | 54 | 55 | 56 | 57 | 58 | 59 | 5A | 5B | 5C | 5D | 5E | 5F |
| 6 | 60 | 61 | 62 | 63 | 64 | 65 | 66 | 67 | 68 | 69 | 6A | 6B | 6C | 6D | 6E | 6F |
| 7 | 70 | 71 | 72 | 73 | 74 | 75 | 76 | 77 | 78 | 79 | 7A | 7B | 7C | 7D | 7E | 7F |
| 8 | 80 | 81 | 82 | 83 | 84 | 85 | 86 | 87 | 88 | 89 | 8A | 8B | 8C | 8D | 8E | 8F |
| 9 | 90 | 91 | 92 | 93 | 94 | 95 | 96 | 97 | 98 | 99 | 9A | 9B | 9C | 9D | 9E | 9F |
| A | A0 | A1 | A2 | A3 | A4 | A5 | A6 | A7 | A8 | A9 | AA | AB | AC | AD | AE | AF |
| B | B0 | B1 | B2 | B3 | B4 | B5 | B6 | B7 | B8 | B9 | BA | BB | BC | BD | BE | BF |
| C | C0 | C1 | C2 | C3 | C4 | C5 | C6 | C7 | C8 | C9 | CA | CB | CC | CD | CE | CF |
| D | D0 | D1 | D2 | D3 | D4 | D5 | D6 | D7 | D8 | D9 | DA | DB | DC | DD | DE | DF |
| E | E0 | E1 | E2 | E3 | E4 | E5 | E6 | E7 | E8 | E9 | EA | EB | EC | ED | EE | EF |
| F | F0 | F1 | F2 | F3 | F4 | F5 | F6 | F7 | F8 | F9 | FA | FB | FC | FD | FE | FF |

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

![](../.gitbook/assets/imagen%20%28473%29.png)

### Illegal opcode

Son aquellos opcodes no documentados que representan operaciones combinadas de la CPU que no son mencionadas en ningun sitio por el desarrollador. Suelen tener efectos que varian desde los inutiles a los no deseados como crashear el sistema.

Suelen ser accidentales pero algunos pueden tener funcionalidades medianamente utiles. Entre los 70s y los 80s algunos juegos de computadora aceleraban los procesadores con opcodes no documentados y otras veces se esquivaba normas de proteccion de datos mediante estos opcodes.

### ¿A que refiere con el concepto de endianess?

Es el orden de la secuencia de bytes \(o la palabra del procesador\). Solemos referirnos como **big-endian** \(**BE**\) o **little-endian** \(**LE**\). Un BE guarda el byte mas significativo de una palabra en el lugar mas pequeño de la memoria y el menos significativo en el mas grande. Por contrario un LE hace el opuesto.

En otros contextos podemos referirnos a como se trasmite informacion en un canal de comunicacion.

El concepto de endianess no comienza a ser relevante hasta la hora de mover archivos de una computadora a la otra ya que han de mantener una consitencia en como se lee. Tambien los [dumps de memoria](https://en.wikipedia.org/wiki/Core_dump) pueden tener complicaciones si no se los lee apropiadamente. Hoy muchas arquitecturas soportan **Bi-endianness** .

Los protocolos de red suelen manejar el BE y los file formats varian.

![](../.gitbook/assets/imagen%20%28472%29.png)

### ¿Que es el registro de la cpu y cuales registros existen?

Registros en la cpu refieren a una memoria de alta velocidad y poca capacidad que es integrada en el microprocesador, guaran transitoriamente y acceden a valores muy reusados sobretodo para operaciones matematicas.

Aparecen en lo mas aalto de la [jerarquía de memoria](https://es.wikipedia.org/wiki/Jerarqu%C3%ADa_de_memoria), y son la manera más rápida que tiene el sistema de almacenar datos.Los registros se miden generalmente por el número de [bits](https://es.wikipedia.org/wiki/Bit) que almacenan; por ejemplo, un "registro de 8 bits" o un "registro de 32 bits". 

El término es usado generalmente para referirse al grupo de registros que pueden ser directamente indexados como operandos de una instrucción, como está definido en el [conjunto de instrucciones](https://es.wikipedia.org/wiki/Complex_instruction_set_computing). 

![](../.gitbook/assets/imagen%20%28475%29.png)

### Tipos de registros

* Los **registros de datos** se usan para guardar números enteros. En algunas computadoras antiguas, existía un único registro donde se guardaba toda la información, llamado acumulador.
* Los **registros de memoria** se usan para guardar exclusivamente direcciones de memoria. Eran muy usados en la arquitectura Harvard, ya que muchas veces las direcciones tenían un tamaño de palabra distinto que los datos.
* Los **registros de propósito general** \(GPRs o General Purpose Registers\) pueden guardar tanto datos como direcciones. Son fundamentales en la arquitectura de von Neumann. La mayor parte de las computadoras modernas usa GPR.
* Los **registros de coma flotante** se usan para guardar datos en formato de coma flotante.
* Los **registros constantes** tienen valores creados por hardware de sólo lectura. Por ejemplo, en MIPS el registro cero siempre vale 0.
* Los **registros de propósito específico** guardan información específica del estado del sistema, como el puntero de pila o el registro de estado.

También existen los registros bandera y de base.

### ¿Que es una llamada a funcion y que tipos de llamada existen?

### ¿Que es el prologo y el epilogo en este contexto?

### ¿Que instrucciones existen en el ensamblador para hacer comparaciones y tomar desiciones?

### ¿Que instrucciones existen en un ensamblador para definir el flujo del codigo?

## Compila y desensambla los siguientes codigos

![](../.gitbook/assets/imagen%20%28463%29.png)



