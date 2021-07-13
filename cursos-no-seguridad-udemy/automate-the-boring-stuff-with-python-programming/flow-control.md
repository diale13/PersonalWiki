# Flow Control

* True, False ambos empiezan con mayuscula

| **Operator** | **Meaning** |
| :--- | :--- |
| == | Equal to |
| != | Not equal to |
| &lt; | Less than |
| &gt; | Greater than |
| &lt;= | Less than or equal to |
| &gt;= | Greater than or equal to |

\*\*\*\*

* The Boolean data type has only two values: True and False \(both beginning with capital letters\).
* Comparison operators compare two values and evaluate to a Boolean value: ==, !=, &lt;, &gt;, &lt;=, &gt;=
* == is a comparison operator, while = is the assignment operator for variables.
* Boolean operators \(and, or, not\) also evaluate to Boolean values.

Para trabajar con los operadores condicionales \(como if\) vamos a necesitar poner un tab entre las ejecuciones

```python
name = "Alice"
if name == "Alice":
    print("Hi Alice")
print("Done)
```

Con un else

```python
name = "Alice"
if name == "Alice":
    print("Hi Alice")
else: 
    print("I hate you bob")
```

luego tambien tenemos el **elif** que es el else if

### Tambien tiene checkeo de nulls

```python
name = input()
if name:
    print("Nice name")
else: 
    print("Why would you not enter a name :(")
```

### While loop

```python
spam = 0
while spam < 5
    print(spam)
    spam = spam + 1
```

* Con break salimos del loop y con **continue** volvemos al inicio

```python
spam = 0
while spam < 5
      spam = spam + 1
      if spam == 3:
            continue
      print(str(spam))
```

