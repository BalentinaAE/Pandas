# Primera clase python
## Balentina  


```python
### A continuación tiene la primera muestra de código, declaramos una variable de cada uno de los diferentes tipos de datos que hemos descrito en la sección anterior:
{caracter = 'a'
estring = "Hello!"
enter =  123
decimal = 1.23
complexe = 1+23j
logic = False


#Este código no es relevante para nosotros, solamente el resultado
print(type(caracter))
print(type(estring))
print(type(enter))
print(type(decimal))
print(type(complexe))
print(type(logic))
<class 'str'>
<class 'str'>
<class 'int'>
<class 'float'>
<class 'complex'>
<class 'bool'>
```


```python
x = 5.3
y = 5.5
comparacion_1 = x < y
comparacion_1
```




    True




```python
letra_a = 'a'
letra_b = 'b'

comparacion_2 = letra_a != letra_b
comparacion_2
```




    True




```python

letra_a = 'a'
letra_b = 'b'

comparacion_3 = letra_a > letra_b
comparacion_3


```




    False



### Realizar un conjunto de expresiones en Python que nos calcule el índice de masa corporal (IMC) de una personaque mide 2 m y pesa 60 Kg. Se calcula dividiendo el peso entre la altura al cuadrado (en cm).




```python

altura = 200
peso= 60
IMC = (peso / altura)**2
IMC
```




    0.09



### Realizar un conjunto de expresiones en Python para resolver una ecuación de primer grado de la forma ax+b= 0. Los valores de a y b los pondremos directamente en el código y mostrar la solución por pantalla




```python
a=5
b=8
c=10

x = (-b/a)
x
```




    -1.6



### Crear una función que recibe un número entero que representa un año y nos devuelve un valor booleano que representa si es un año bisiesto o no. Comprueba la corrección de tu función usándola.


```python
# regla:
#Año divisible por 4: Bisiesto.
#Año divisible por 100 (pero no por 400): No bisiesto.
#Año divisible por 400: Bisiesto.


def es_bisiesto(anio):    
    if anio % 400 == 0:
        return True

    elif anio % 100 == 0:
        return False

    elif anio % 4 == 0:
        return True
 
    else:
        return False

# Prueba de varios años para verificar si son bisiestos
anios = [1900, 2000, 2023, 2024]  
resultados = [es_bisiesto(anio) for anio in anios] 
resultados
```




    [False, True, False, True]



### Realizar una función que recibe los parámetros (números enteros): a, b y c. resuelve una ecuación de segundo grado y devuelve sus soluciones. Ejemplo, la ecuación:  debe dar -0.1523201 ; -9.8476799. Para calcular la raíz cuadrada podéis usar la función sqrt. Comprueba la corrección de tu función usándola.


```python

import math  #  librería matemática para usar sqrt

def ecuacion(a, b, c):
    discriminante = b**2 - 4*a*c  # Calculamos el discriminante
    
    if discriminante < 0:
        print("La ecuación no tiene solución en los números reales")
    else:
        raiz1 = (-b + math.sqrt(discriminante)) / (2*a)  # Primera raíz
        raiz2 = (-b - math.sqrt(discriminante)) / (2*a)  # Segunda raíz
        
        print(f"Las raíces son: {raiz1} y {raiz2}")

#  función con los valores dados
ecuacion(1, 10, 1)
```

    Las raíces son: -0.10102051443364424 y -9.898979485566356
    

# TEMA 2 PAGINA Control del flujo del programa  
### Realizar un programa que imprima todos los números del 0 al 6 excepto el 3 y el 6.



```python

```


### Escribir un programa que dado un número, imprima todos los divisores de ese número.


```python
x= 0
def divisores(x):
    if x == 0:  
        print("No se puede dividir por cero")
    else:
        print(f"Los divisores de {x} son:")
        for i in range(1, x + 1):  # Recorre los números desde 1 hasta x
            if x % i == 0:  # Verifica si es divisor
                print(i)

# Ejemplo de uso:
divisores(30)
```

    Los divisores de 30 son:
    1
    2
    3
    5
    6
    10
    15
    30
    


```python
for numero in range(7):  
    if numero != 3 and numero != 6:  
        print(numero)
```

    0
    1
    2
    4
    5
    

# hacer python poner en marcha guardar el fichero y guardar para el examen- hasta listas




### Escribe una función que recibe tres valores de entrada que corresponden a horas, minutos y segundos. El programa debe indicar si se trata de un reloj con una hora válida.

#### Si recibimos los números 9, 56, 33 es correcto.
#### Si recibimos los números 9, 64, 22 no es correcto, ya que no existen los 64 minutos.
#### Si recibimos los números 25, 44, 22 no es correcto puesto que no existe la hora 25.


```python
def es_hora_valida(horas, minutos, segundos):
    # Comprobar si las horas están en el rango válido (0-23)
    if horas < 0 or horas > 23:
        return "No es correcto, las horas deben estar entre 0 y 23."
    
    # Comprobar si los minutos están en el rango válido (0-59)
    if minutos < 0 or minutos > 59:
        return "No es correcto, los minutos deben estar entre 0 y 59."
    
    # Comprobar si los segundos están en el rango válido (0-59)
    if segundos < 0 or segundos > 59:
        return "No es correcto, los segundos deben estar entre 0 y 59."
    
    return "Es correcto, la hora es válida."

# Ejemplos de uso
print(es_hora_valida(9, 56, 33))  # Salida: Es correcto, la hora es válida.
print(es_hora_valida(9, 64, 22))  # Salida: No es correcto, los minutos deben estar entre 0 y 59.
print(es_hora_valida(25, 44, 22))  # Salida: No es correcto, las horas deben estar entre 0 y 23.
print(es_hora_valida(12, 30, 45))  # Salida: Es correcto, la hora es válida.
print(es_hora_valida(23, 59, 59))  # Salida: Es correcto, la hora es válida.
        
```

    Es correcto, la hora es válida.
    No es correcto, los minutos deben estar entre 0 y 59.
    No es correcto, las horas deben estar entre 0 y 23.
    Es correcto, la hora es válida.
    Es correcto, la hora es válida.
    

### Realizar un programa que imprima todos los números del 0 al 6 excepto el 3 y el 6. 


```python

for num in range(7):  # Recorremos los números del 0 al 6
    if num == 3 or num == 6:
        continue  # Saltamos el número si es 3 o 6
    print(num) 
```

    0
    1
    2
    4
    5
    

### Dado un número entero . Si la suma de sus divisores (sin contar el mismo número) es igual a , se dice que ese número es perfecto. Si esa suma es inferior, se dice que es deficiente. Si es superior se dice que es abundante. Realiza un programa que dado un número entero nos diga si es perfecto, deficiente o abundante.


```python
def sum_divisors(n): 
    suma = 0
    # Encontrar los divisores de n (sin incluir el mismo n)
    for i in range(1, n):
        if n % i == 0:
            suma += i
    return suma

def clasificar_numero(n):
    suma = sum_divisors(n)
    
    if suma == n:
        return "Número perfecto"
    elif suma < n:
        return "Número deficiente"
    else:
        return "Número abundante"

# Entrada del usuario
n = int(input("Introduce un número entero: "))
resultado = clasificar_numero(n)
print(f"El número {n} es {resultado}.")
```

###  Escriba un programa para construir el siguiente patrón:

### 1
### 1 1
### 1 1 1
### 1 1 1 1
### 1 1 1 1 1
### 1 1 1 1
### 1 1 1
### 1 1
### 1



```python
# Parte superior del patrón
for i in range(1, 6):  # Desde 1 hasta 5
    print("1 " * i)  # Imprime '1 ' i veces

# Parte inferior del patrón
for i in range(4, 0, -1):  # Desde 4 hasta 1
    print("1 " * i)  # Imprime '1 ' i veces

#Explicación del Código
#Bucle para la Parte Superior:

#for i in range(1, 6): Este bucle va de 1 a 5 (incluyendo 1 y 5). Cada valor de i determina cuántas veces se imprimirá 1.
#print("1 " * i): Imprime la cadena "1 " repetida i veces. Por ejemplo, cuando i es 3, imprime 1 1 1 .
#Bucle para la Parte Inferior:

#for i in range(4, 0, -1): Este bucle va de 4 a 1 (decrementando). Por cada iteración, imprime una línea con 1s, comenzando desde 4 y disminuyendo hasta 1.
#print("1 " * i): Imprime 1 tantas veces como el valor actual de i.

#range(start, stop, step)
#start: El número inicial de la secuencia (incluido).
#stop: El número donde se detiene la secuencia (excluido).
#step: La cantidad en la que se incrementa (o decrementa) el número en cada iteración.
#Desglosando range(4, 0, -1)
# start: 4 Esto indica que la secuencia comenzará en 4.
#stop: 0 Esto significa que la secuencia se detendrá justo antes de llegar a 0, es decir, el 0 no se incluirá.
#step: -1 Un paso negativo indica que estamos contando hacia atrás (decrementando) en lugar de hacia adelante. Así, en cada iteración, i disminuirá en 1.
```

    1 
    1 1 
    1 1 1 
    1 1 1 1 
    1 1 1 1 1 
    1 1 1 1 
    1 1 1 
    1 1 
    1 
    

### Escribe una función que recibe un número y devuelve True si este es primo y Falseen caso contrario.
#### int es un tipo de dato en Python que representa números enteros.
#### La función int() se utiliza para convertir otros tipos de datos, como cadenas y números de punto flotante, a enteros.
#### Al recibir entradas del usuario, es común usar int() para asegurarse de que los datos sean del tipo adecuado para operaciones matemáticas.


```python
def es_primo(n):
    if n <= 1:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

# Entrada del usuario
numero = int(input("Introduce un número entero: "))  # Convierte la entrada a entero
if es_primo(numero):
    print(f"{numero} es primo.")
else:
    print(f"{numero} no es primo.")
```

    Introduce un número entero:  4558
    

    4558 no es primo.
    

### Dada la siguiente lista, realiza las operaciones que siguen y verifica su corrección después de la ejecución mi_lista = [1,2,3,4,5,6,7]

### ista[inicio:final:incremento]
## inicio: Es el índice donde comienza el slicing. Este índice se incluye en el resultado.
## final: Es el índice donde se detiene el slicing. Este índice no se incluye en el resultado. Solo se toman los elementos hasta, pero sin incluir, este índice.
## incremento: Es la cantidad de pasos que se toman en la selección de elementos. Puede ser positivo (para avanzar) o negativo (para retroceder). 


```python
#mi_lista = [1,2,3,4,5,6,7] 
#1. Cambia el primer valor por 33.
#2. Muestra su longitud por pantalla.
#3. Muestra los 3 últimos valores.
#4. Cambia el valor central por el valor -5.
#5. Añade la lista [8, 9, 10] a mi lista.
#6. Elimina el valor 3.
#7. Verifica que ya no existe el valor 4.
#8. Inserta el valor 10 después del valor 2.

# 1. Crea la lista inicial
mi_lista = [1, 2, 3, 4, 5, 6, 7]

# 1. Cambia el primer valor por 33
mi_lista[0] = 33
print("Después de cambiar el primer valor:", mi_lista)

# 2. Muestra su longitud por pantalla
longitud = len(mi_lista)
print("La longitud de la lista es:", longitud)

# 3. Muestra los 3 últimos valores
ultimos_tres = mi_lista[-3:]  # Tomamos los últimos 3 elementos
print("Los 3 últimos valores son:", ultimos_tres)

# 4. Cambia el valor central por el valor -5
# La longitud de la lista es 7, el índice central es 3 (7 // 2)
mi_lista[len(mi_lista) // 2] = -5
print("Después de cambiar el valor central por -5:", mi_lista)

# 5. Añade la lista [8, 9, 10] a mi lista
mi_lista.extend([8, 9, 10])  # Añadimos los elementos al final de la lista
print("Después de añadir [8, 9, 10]:", mi_lista)

# 6. Elimina el valor 3
mi_lista.remove(3)  # Elimina la primera aparición del valor 3
print("Después de eliminar el valor 3:", mi_lista)

# 7. Verifica que ya no existe el valor 4
valor_existe = 4 in mi_lista
print("¿El valor 4 existe en la lista?", valor_existe)  # Debería ser False

# 8. Inserta el valor 10 después del valor 2
# Encontramos la posición del valor 2
indice_dos = mi_lista.index(2)
mi_lista.insert(indice_dos + 1, 10)  # Insertamos 10 después de 2
print("Después de insertar el valor 10 después del 2:", mi_lista)


```

    Después de cambiar el primer valor: [33, 2, 3, 4, 5, 6, 7]
    La longitud de la lista es: 7
    Los 3 últimos valores son: [5, 6, 7]
    Después de cambiar el valor central por -5: [33, 2, 3, -5, 5, 6, 7]
    Después de añadir [8, 9, 10]: [33, 2, 3, -5, 5, 6, 7, 8, 9, 10]
    Después de eliminar el valor 3: [33, 2, -5, 5, 6, 7, 8, 9, 10]
    ¿El valor 4 existe en la lista? False
    Después de insertar el valor 10 después del 2: [33, 2, 10, -5, 5, 6, 7, 8, 9, 10]
    

### A partir de la lista siguiente a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89] escribe un programa que imprima todos los elementos  de la lista que son menores de 5.


```python
a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]

# Recorremos cada elemento de la lista
for num in a:
    if num < 5:  # Si el número es menor que 5
        print(num)
#Explicación:
#La lista a contiene una serie de números.
#Usamos un bucle for para recorrer cada número de la lista.
#La condición if num < 5 verifica si el número es menor de 5. Si es así, se imprime el número.
```

    1
    1
    2
    3
    

### Escribir un programa que dado un número añada todos los divisores de ese número en una lista y luego la muestre por pantalla.


```python
# Solicitar al usuario un número entero
n = int(input("Introduce un número entero: "))

# Inicializamos una lista vacía para almacenar los divisores
divisores = []

# Recorremos desde 1 hasta n (excluyendo el propio n) para encontrar los divisores
for i in range(1, n + 1):
    if n % i == 0:  # Si i es divisor de n
        divisores.append(i)  # Lo añadimos a la lista de divisores

# Mostramos la lista de divisores por pantalla
print(f"Los divisores de {n} son: {divisores}")
#Explicación:
#El programa solicita al usuario que introduzca un número entero.
#Si lo es, se añade a la lista divisores.
#Finalmente, se imprime la lista con todos los divisores del número.
```

    Introduce un número entero:  62
    

    Los divisores de 62 son: [1, 2, 31, 62]
    

#### Dadas dos listas, digamos por ejemplo estas dos: a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89] y b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13] y escribe una función que devuelva una lista que contenga solo los elementos que son comunes entre las listas (sin duplicados). Las listas no tienen por qué tener el mismo tamaño.


```python

# Definimos una función que toma dos listas como argumentos
def elementos_comunes(lista1, lista2):
    # Usamos un conjunto (set) para eliminar duplicados y buscar los elementos comunes
    return list(set(lista1) & set(lista2))

# Listas 
a = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]

# Llamamos a la función y mostramos los elementos comunes
resultado = elementos_comunes(a, b)
print(f"Elementos comunes: {resultado}")
#Explicación:
#set(lista1) & set(lista2): Convertimos las listas en conjuntos (sets) para eliminar duplicados automáticamente y usamos la operación & (intersección) para obtener solo los elementos comunes.
#list(): Convertimos el conjunto resultante nuevamente en una lista, ya que la intersección devuelve un conjunto y queremos obtener una lista como resultado.
#Función: La función recibe dos listas como parámetros y devuelve una lista con los elementos comunes sin duplicados.
```

    Elementos comunes: [1, 2, 3, 5, 8, 13]
    

### Escribir una función para contar el número de strings con longitud 2 o más y el primer y último carácter son los mismos muestras = ['abc', 'xyz', 'aba', '1221'] Resultado esperado: 2


```python
def contar_strings(lista):
    contador = 0  # Inicializamos un contador para contar los strings que cumplen las condiciones.
    
    for string in lista:  # Recorremos cada string en la lista.
        # Comprobamos si la longitud del string es mayor o igual a 2 y si el primer y último carácter son iguales.
        if len(string) >= 2 and string[0] == string[-1]:
            contador += 1  # Si ambas condiciones se cumplen, incrementamos el contador.
    
    return contador  # Al final, devolvemos el valor del contador.

# Lista de ejemplo
muestras = ['abc', 'xyz', 'aba', '1221']

# Llamamos a la función contar_strings con la lista 'muestras' y guardamos el resultado.
resultado = contar_strings(muestras)

# Imprimimos el resultado.
print(f"Resultado esperado: {resultado}")
```

    Resultado esperado: 2
    

### Dada la lista b del ejercicio 3, elimina todos los números impares.


```python
b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]

# Filtrar los números pares
b = [num for num in b if num % 2 == 0]

print(b)  
#Explicación:
#Comprensión de listas: La línea [num for num in b if num % 2 == 0] crea una nueva lista que contiene solo los números de b que son divisibles entre 2, es decir, los números pares.
#num % 2 == 0: Verifica si el número es par (si el residuo de la división entre 2 es cero).
```

    [2, 4, 6, 8, 10, 12]
    

### Escribir una función que recibe dos listas por parámetro y devuelva True si tienen al menos un miembro común.
#### Explicación: Definición de la función tienen_miembro_comun(lista1, lista2):

#### La función recibe dos listas como parámetros (lista1 y lista2).
#### Bucle for:

#### El bucle recorre cada elemento de la primera lista (lista1).
#### Para cada elemento, se verifica si ese elemento está presente en la segunda lista (lista2) usando el operador in.
#### Condición:

#### Si encuentra un elemento que está en ambas listas, la función inmediatamente devuelve True.
#### Final del bucle:

#### Si el bucle termina sin encontrar elementos comunes, la función devuelve False, indicando que no comparten ningún elemento.


```python
def tienen_miembro_comun(lista1, lista2):
    # Recorremos cada elemento de la primera lista
    for elemento in lista1:
        # Verificamos si ese elemento está en la segunda lista
        if elemento in lista2:
            return True  # Si encontramos un elemento común, devolvemos True
    return False  # Si terminamos de recorrer las listas sin encontrar un elemento común, devolvemos False

# Ejemplo de uso:
a = [1, 2, 3, 4, 5]
b = [5, 6, 7, 8, 9]

resultado = tienen_miembro_comun(a, b)
print(resultado) 
```

    True
    
