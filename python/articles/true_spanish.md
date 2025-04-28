<!--
Meta Description: # True en Python: Comprendiendo el Valor Booleano Verdadero ## Sinopsis En Python, `True` es uno de los dos valores booleanos que representan la verda...
Meta Keywords: true, python, que, valor, para
-->

# True en Python: Comprendiendo el Valor Booleano Verdadero

## Sinopsis
En Python, `True` es uno de los dos valores booleanos que representan la verdad en expresiones condicionales y lógicas. Este valor es fundamental en la programación para controlar el flujo de ejecución de un programa.

## Documentación
El valor `True` es un tipo de dato booleano en Python, que se utiliza para indicar que una condición es verdadera. Python, como lenguaje de programación, utiliza valores booleanos para ejecutar declaraciones condicionales, bucles, y otras estructuras de control.

### Propósito
`True` es parte del tipo de dato `bool`, que también incluye su contraparte, `False`. Estos valores son cruciales para la toma de decisiones dentro de un programa.

### Uso
En Python, puedes asignar el valor `True` a una variable, utilizarlo en expresiones lógicas y condicionales, así como en estructuras de control como `if`, `while`, y `for`.

```python
# Asignación de True a una variable
es_verdadero = True

# Uso en una declaración if
if es_verdadero:
    print("La condición es verdadera.")
```

## Ejemplos
### Ejemplo 1: Uso básico de True
```python
a = True
b = False

print(a)  # Salida: True
print(b)  # Salida: False
```

### Ejemplo 2: Condicional con True
```python
edad = 20
mayor_de_edad = edad >= 18  # Esto devuelve True

if mayor_de_edad:
    print("Eres mayor de edad.")  # Salida: Eres mayor de edad.
```

### Ejemplo 3: Uso en bucles
```python
contador = 0
seguir = True

while seguir:
    print("Contador:", contador)
    contador += 1
    if contador >= 5:
        seguir = False  # Cambia seguir a False para salir del bucle
```

## Explicación
Un error común es confundir el valor `True` con otros tipos de datos o no utilizarlo correctamente en expresiones lógicas. Por ejemplo, es importante recordar que `if True:` siempre ejecutará su bloque de código, mientras que `if False:` nunca lo hará. 

Además, `True` puede ser utilizado en expresiones booleanas complejas, donde puede ser combinado con operadores como `and`, `or` y `not` para crear condiciones más sofisticadas.

### Notas Adicionales
- `True` es un valor reservado en Python y no debe ser utilizado como nombre de variable.
- Python es sensible a mayúsculas y minúsculas, por lo que `true` no es lo mismo que `True`.

## Resumen en una línea
`True` en Python es un valor booleano que representa la verdad, utilizado en estructuras de control y expresiones lógicas.