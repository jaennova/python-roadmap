# **Guía de Sintaxis de Python**

## Índice
1. [Comentarios](#comentarios)
2. [Tipos de Datos Primitivos y Operadores](#tipos-de-datos-primitivos-y-operadores)
3. [Operadores Booleanos](#operadores-booleanos)
4. [Comparaciones](#comparaciones)
5. [Cadenas de Texto](#cadenas-de-texto)
6. [El objeto None](#el-objeto-none)

## Comentarios

```python
# Los comentarios de una línea comienzan con el símbolo numeral

""" Los comentarios multilínea se pueden escribir
    usando tres comillas dobles, y se usan
    frecuentemente como documentación.
"""
```

## Tipos de Datos Primitivos y Operadores

```python
# Números
3  # => 3

# Las matemáticas funcionan como esperarías
1 + 1   # => 2
8 - 1   # => 7
10 * 2  # => 20
35 / 5  # => 7.0

# La división entera redondea hacia el infinito negativo
5 // 3       # => 1
-5 // 3      # => -2
5.0 // 3.0   # => 1.0  # También funciona con decimales
-5.0 // 3.0  # => -2.0

# El resultado de una división siempre es un decimal (float)
10.0 / 3  # => 3.3333333333333335

# Operación módulo (resto de la división)
7 % 3   # => 1
# i % j tiene el mismo signo que j, a diferencia de C
-7 % 3  # => 2

# Potenciación (x**y, x elevado a y)
2**3  # => 8

# Forzar precedencia con paréntesis
1 + 3 * 2    # => 7
(1 + 3) * 2  # => 8
```

## Operadores Booleanos

```python
# Los valores booleanos son primitivos (nota la mayúscula inicial)
True   # => True
False  # => False

# Negar con not
not True   # => False
not False  # => True

# Operadores booleanos
# Nota: "and" y "or" son sensibles a mayúsculas y minúsculas
True and False  # => False
False or True   # => True

# True y False son realmente 1 y 0 pero con palabras clave diferentes
True + True  # => 2
True * 8     # => 8
False - 5    # => -5

# Los operadores booleanos con enteros los convierte a booleanos para evaluarlos
bool(0)   # => False
bool(2)   # => True
0 and 2   # => 0
bool(-5)  # => True
-5 or 0   # => -5
```

## Comparaciones

```python
# Igualdad es ==
1 == 1  # => True
2 == 1  # => False

# Desigualdad es !=
1 != 1  # => False
2 != 1  # => True

# Más comparaciones
1 < 10  # => True
1 > 10  # => False
2 <= 2  # => True
2 >= 2  # => True

# Verificar si un valor está en un rango
1 < 2 and 2 < 3  # => True
2 < 3 and 3 < 2  # => False
# Encadenar hace esto más elegante
1 < 2 < 3  # => True
2 < 3 < 2  # => False

# (is vs. ==) is verifica si dos variables se refieren al mismo objeto,
# mientras que == verifica si los objetos tienen los mismos valores
a = [1, 2, 3, 4]  # Apunta 'a' a una nueva lista
b = a             # Apunta 'b' a lo mismo que 'a'
b is a            # => True, 'a' y 'b' se refieren al mismo objeto
b == a            # => True, los objetos de 'a' y 'b' son iguales
b = [1, 2, 3, 4]  # Apunta 'b' a una nueva lista
b is a            # => False, 'a' y 'b' no se refieren al mismo objeto
b == a            # => True, los objetos de 'a' y 'b' son iguales
```

## Cadenas de Texto

```python
# Las cadenas se crean con " o '
"Esto es una cadena."
'Esto también es una cadena.'

# Las cadenas se pueden concatenar
"Hola " + "mundo!"  # => "Hola mundo!"
# Los literales de cadena (pero no las variables) se pueden concatenar sin usar '+'
"Hola " "mundo!"    # => "Hola mundo!"

# Una cadena puede tratarse como una lista de caracteres
"Hola mundo!"[0]  # => 'H'

# Puedes encontrar la longitud de una cadena
len("Esto es una cadena")  # => 16

# Desde Python 3.6, puedes usar f-strings o literales de cadena formateados
nombre = "Reiko"
f"Ella dijo que su nombre es {nombre}."  # => "Ella dijo que su nombre es Reiko"
# Cualquier expresión Python válida dentro de las llaves se evalúa y se incluye en la cadena
f"{nombre} tiene {len(nombre)} caracteres."  # => "Reiko tiene 5 caracteres."
```

## El objeto None

```python
# None es un objeto
None  # => None

# No uses el operador de igualdad "==" para comparar objetos con None
# Usa "is" en su lugar. Esto verifica la igualdad de identidad del objeto
"etc" is None  # => False
None is None   # => True
```
```py
True  # => Verdadero
False # => Falso

# Negar con "not"
not True  # => Falso
not False # => Verdadero

# Operadores booleanos
# Ten en cuenta que "and" y "or" distinguen mayúsculas de minúsculas
True and False # => Falso
False or True  # => Verdadero

# True y False son en realidad 1 y 0, pero con diferentes palabras clave
True + True  # => 2
True * 8  # => 8
False - 5 # => -5

# Operadores de comparación
# Estos operadores comparan el valor numérico de True y False
0 == False  # => Verdadero
2 > True  # => Verdadero
2 == True  # => Falso
-5 != False # => Verdadero

# None, 0 y cadenas vacías/listas/diccionarios/tuplas/conjuntos se evalúan como False
bool(0)      # => Falso
bool("")     # => Falso
bool([])     # => Falso
bool({})     # => Falso
bool(())     # => Falso
bool(set())  # => Falso
bool(4)      # => Verdadero
bool(-6)     # => Verdadero

# Al usar operadores lógicos booleanos en enteros, estos se convierten a booleanos para la evaluación,
# pero se devuelve su valor original sin convertir. No confundas esto con bool(enteros) y el operador AND bit a bit (&).
bool(0)   # => Falso
bool(2)   # => Verdadero
0 and 2   # => 0
bool(-5)  # => Verdadero
bool(2)   # => Verdadero
-5 or 0   # => -5
```

## Igualdad y desigualdad

```py
# La igualdad se comprueba con "=="
1 == 1  # => Verdadero
2 == 1  # => Falso

# La desigualdad se comprueba con "!="
1 != 1  # => Falso
2 != 1  # => Verdadero
```

## Más comparaciones

```py
1 < 10  # => Verdadero
1 > 10  # => Falso
2 <= 2  # => Verdadero
2 >= 2  # => Verdadero
```

## Verificando si un valor está en un rango

```py
1 < 2 y 2 < 3  # => Verdadero
2 < 3 y 3 < 2  # => Falso

# Encadenar las condiciones mejora la lectura
1 < 2 < 3  # => Verdadero
2 < 3 < 2  # => Falso
```

## (is vs. ==) - Identidad vs. Igualdad en Python

En Python, `is` y `==` son dos operadores distintos que se utilizan para comparar objetos. Es importante comprender la diferencia entre ambos para evitar confusiones en tu código.

**`is` - Comprobando la identidad del objeto:**

* El operador `is` verifica si dos variables **apuntan al mismo objeto** en la memoria.
* Si ambas variables referencian el mismo objeto en memoria, la comparación `is True`.
* Si las variables referencian objetos diferentes con el mismo valor, la comparación `is False`.

**Ejemplo:**

```python
a = [1, 2, 3, 4]  # a apunta a una nueva lista en memoria
b = a             # b también apunta a la misma lista en memoria

b is a            # True, a y b apuntan al mismo objeto
b == a            # True, las listas a las que apuntan a y b tienen el mismo valor
```

**`==` - Comprobando la igualdad del valor:**

* El operador `==` compara el **valor** de dos objetos.
* Si los valores de los objetos son iguales, sin importar si son el mismo objeto en memoria, la comparación `== True`.
* Si los valores son diferentes, `== False`.

**Ejemplo:**

```python
b = [1, 2, 3, 4]  # b ahora apunta a una nueva lista en memoria (diferente a la de a)

b is a            # False, a y b apuntan a objetos diferentes en memoria
b == a            # True, las listas a las que apuntan a y b tienen el mismo valor (ambas son [1, 2, 3, 4])
```


## Variables y Entrada/Salida

```python
# Python tiene una función print
print("¡Soy Python. Encantado de conocerte!")  # => ¡Soy Python. Encantado de conocerte!

# Por defecto, print añade un salto de línea al final.
# Usa el argumento opcional 'end' para cambiar el final.
print("¡Hola, Mundo", end="!")  # => ¡Hola, Mundo!

# Forma simple de obtener datos de la consola
texto_entrada = input("Ingresa algún dato: ")  # Devuelve los datos como string

# No hay declaraciones, solo asignaciones.
# La convención para nombrar variables es usar snake_case
alguna_var = 5
alguna_var  # => 5

# Acceder a una variable no asignada genera una excepción
alguna_var_desconocida  # Genera un NameError

# if puede usarse como expresión
# Equivalente al operador ternario '?:' de C
"¡sí!" if 0 > 1 else "¡no!"  # => "¡no!"
```

## Listas

```python
# Las listas almacenan secuencias
li = []
# Puedes comenzar con una lista prellenada
otra_li = [4, 5, 6]

# Agregar elementos al final con append
li.append(1)    # li es ahora [1]
li.append(2)    # li es ahora [1, 2]
li.append(4)    # li es ahora [1, 2, 4]
li.append(3)    # li es ahora [1, 2, 4, 3]

# Eliminar del final con pop
li.pop()        # => 3 y li es ahora [1, 2, 4]
# Volvamos a ponerlo
li.append(3)    # li es ahora [1, 2, 4, 3] de nuevo

# Acceder a una lista como lo harías con cualquier array
li[0]   # => 1
# Mirar el último elemento
li[-1]  # => 3

# Puedes ver rangos con la sintaxis de rebanado (slice)
li[1:3]   # Devuelve lista desde índice 1 hasta 3 => [2, 4]
li[2:]    # Devuelve lista desde índice 2 hasta el final => [4, 3]
li[:3]    # Devuelve lista desde el inicio hasta índice 3 => [1, 2, 4]
li[::2]   # Devuelve lista seleccionando elementos cada 2 pasos => [1, 4]
li[::-1]  # Devuelve lista en orden inverso => [3, 4, 2, 1]

# Hacer una copia superficial usando rebanado
li2 = li[:]  # => li2 = [1, 2, 4, 3] pero (li2 is li) dará False

# Eliminar elementos arbitrarios con "del"
del li[2]  # li es ahora [1, 2, 3]

# Eliminar primera ocurrencia de un valor
li.remove(2)  # li es ahora [1, 3]
li.remove(2)  # Genera ValueError ya que 2 no está en la lista

# Insertar elemento en un índice específico
li.insert(1, 2)  # li es ahora [1, 2, 3] de nuevo

# Obtener el índice del primer elemento que coincida
li.index(2)  # => 1
li.index(4)  # Genera ValueError ya que 4 no está en la lista
```

## Tuplas

```python
# Las tuplas son como listas pero son inmutables
tup = (1, 2, 3)
tup[0]      # => 1
tup[0] = 3  # Genera TypeError

# Una tupla de longitud uno debe tener una coma después del último elemento
type((1))   # => <class 'int'>
type((1,))  # => <class 'tuple'>
type(())    # => <class 'tuple'>

# Puedes desempaquetar tuplas (o listas) en variables
a, b, c = (1, 2, 3)  # a es 1, b es 2 y c es 3
# También puedes hacer desempaquetado extendido
a, *b, c = (1, 2, 3, 4)  # a es 1, b es [2, 3] y c es 4
```

## Diccionarios

```python
# Los diccionarios almacenan mapeos de claves a valores
diccionario_vacio = {}
# Aquí hay un diccionario prellenado
diccionario_lleno = {"uno": 1, "dos": 2, "tres": 3}

# Las claves deben ser de tipos inmutables
diccionario_invalido = {[1,2,3]: "123"}  # => Genera TypeError
diccionario_valido = {(1,2,3):[1,2,3]}   # Los valores pueden ser de cualquier tipo

# Buscar valores con []
diccionario_lleno["uno"]  # => 1

# Obtener todas las claves como iterable
list(diccionario_lleno.keys())  # => ["uno", "dos", "tres"]

# Obtener todos los valores como iterable
list(diccionario_lleno.values())  # => [1, 2, 3]

# Verificar existencia de claves con "in"
"uno" in diccionario_lleno  # => True
1 in diccionario_lleno      # => False

# Obtener valor con get() evita KeyError
diccionario_lleno.get("uno")      # => 1
diccionario_lleno.get("cuatro")   # => None
diccionario_lleno.get("cuatro", 4) # => 4  # valor por defecto si no existe
```

## Conjuntos (Sets)

```python
# Los conjuntos almacenan ... bueno, conjuntos
conjunto_vacio = set()
# Inicializar un conjunto con varios valores
algun_conjunto = {1, 1, 2, 2, 3, 4}  # algun_conjunto es ahora {1, 2, 3, 4}

# Agregar un elemento más al conjunto
conjunto_lleno = algun_conjunto
conjunto_lleno.add(5)  # conjunto_lleno es ahora {1, 2, 3, 4, 5}

# Operaciones de conjuntos
otro_conjunto = {3, 4, 5, 6}
# Intersección con &
conjunto_lleno & otro_conjunto  # => {3, 4, 5}
# Unión con |
conjunto_lleno | otro_conjunto  # => {1, 2, 3, 4, 5, 6}
# Diferencia con -
{1, 2, 3, 4} - {2, 3, 5}  # => {1, 4}
# Diferencia simétrica con ^
{1, 2, 3, 4} ^ {2, 3, 5}  # => {1, 4, 5}
```


