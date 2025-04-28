<!--
Meta Description: # UnboundLocalError en Python: Comprendiendo el Error de Variable Local No Asignada ## Sinopsis El `UnboundLocalError` es un error en Python que se pr...
Meta Keywords: variable, una, local, python, que
-->

# UnboundLocalError en Python: Comprendiendo el Error de Variable Local No Asignada

## Sinopsis
El `UnboundLocalError` es un error en Python que se produce cuando se intenta acceder a una variable local antes de haber sido asignada. Este error es común en el contexto de funciones y puede causar que el programa se detenga inesperadamente.

## Documentación
### Propósito
El propósito del `UnboundLocalError` es indicar que se ha intentado utilizar una variable local dentro de una función antes de que se le haya asignado un valor. Este error ayuda a los desarrolladores a identificar problemas en el alcance y la asignación de variables en su código.

### Uso
El `UnboundLocalError` se manifiesta cuando se define una variable dentro de una función, pero no se le asigna un valor antes de ser utilizada. A diferencia de una variable global, que puede ser utilizada sin asignación en una función si no se ha declarado como local, una variable local debe ser inicializada antes de su uso.

### Detalles
- **Alcance de las Variables**: En Python, las variables tienen un alcance que determina dónde pueden ser accesibles. Las variables definidas dentro de una función son locales a esa función.
- **Declaración de Variables**: Si una variable se asigna dentro de una función, Python la considera local por defecto. Si se intenta acceder a esa variable antes de su asignación, se produce un `UnboundLocalError`.
- **Errores Comunes**: Este error es frecuente en funciones donde se intenta utilizar una variable que se ha declarado pero no se ha inicializado todavía.

## Ejemplos

### Ejemplo 1: Acceso a una Variable Local No Asignada
```python
def mi_funcion():
    print(x)  # Intento de acceder a la variable local 'x' antes de asignarle un valor
    x = 10

mi_funcion()  # Esto generará UnboundLocalError: local variable 'x' referenced before assignment
```

### Ejemplo 2: Asignación Correcta
```python
def mi_funcion():
    x = 10  # Asignación de la variable 'x'
    print(x)  # Ahora se puede acceder a 'x' sin problemas

mi_funcion()  # Esto imprimirá 10
```

### Ejemplo 3: Uso de Variables Globales
```python
x = 5  # Variable global

def mi_funcion():
    global x  # Declarar 'x' como variable global
    print(x)  # Ahora se puede acceder a la variable global 'x'
    x = 10  # Esto cambiará la variable global 'x'

mi_funcion()  # Esto imprimirá 5 y luego cambiará 'x' a 10
```

## Explicación
Los errores de tipo `UnboundLocalError` son comunes en Python, especialmente para aquellos que son nuevos en el lenguaje. Un fallo típico es asumir que una variable global puede ser utilizada sin declarar su alcance local. Es crucial entender el concepto de alcance de las variables y cómo Python maneja las asignaciones. Para evitar este error, asegúrate de inicializar todas las variables locales antes de su uso y considera la necesidad de declarar variables globales si es necesario.

## Resumen en Una Línea
El `UnboundLocalError` en Python ocurre cuando se intenta acceder a una variable local antes de haberle asignado un valor.