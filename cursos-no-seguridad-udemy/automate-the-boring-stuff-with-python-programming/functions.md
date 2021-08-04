# Functions

## Python's Built-In Functions

* print\(\)
* input\(\)
* len\(\)

Ademas python viene con varios modulos internos como lo hace java por ejemplo. Math trae cosas de matematica. Antes de usar debemos importarlos con **import**

```text
import random
random.randint(1,10) -> Numero random entre 1 y 10
```

Podes hacer multiples imports &gt;&gt; import random, sys, os, math

Podemos cortar la ejecucion del programa usando sys.exit\(\) si este fue importado.

Para instalar modulos de terceros utilizamos la herramienta **pip** que viene con python

Script para ejecutar en caso de que no corra el pip en windows:

![](../../.gitbook/assets/imagen%20%28927%29.png)

Luego ejecutando esto

```text
import pyperclip
pyperclip.copy("hello world")
pyperclipp.paste()
```

Copia helloworld en tu clipboard y lo pega.

## Writing Your Own Functions

```python
def hello()
    print("Hi")
    print("Hello there")
    
hello()

def plusOne(number):
    return number + 1
```

Cambio en separadores: 

print\( "cat", "dog", "mouse" \) -&gt; cat dog mouse

 print\( "cat", "dog", "mouse", sep="AAA" \) -&gt; catAAAdogAAAmouse

* Every function has a return value. If your function doesn't have a return statement, the default return value is None. \(Like True and False, None is written with a capital first letter.\)
* Keyword arguments to functions are usually for optional arguments. The print\(\) function has keyword arguments "end" and "sep".



