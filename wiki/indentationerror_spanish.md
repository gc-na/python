<!--
Meta Description: # IndentationError en Python: Causas y Soluciones ## Sinopsis El **IndentationError** en Python es un error de sintaxis que ocurre cuando la indentaci...
Meta Keywords: indentación, que, python, código, indentationerror
-->

# IndentationError en Python: Causas y Soluciones

## Sinopsis
El **IndentationError** en Python es un error de sintaxis que ocurre cuando la indentación del código no es correcta. Python utiliza la indentación para definir bloques de código, por lo que un manejo incorrecto puede llevar a este tipo de error.

## Documentación
### Propósito
El propósito del **IndentationError** es asegurar que el código esté correctamente estructurado. A diferencia de otros lenguajes de programación que utilizan llaves o palabras clave para definir bloques, Python depende de la indentación para determinar la jerarquía del código.

### Uso
Cuando un programa Python tiene una indentación incorrecta (por ejemplo, mezclar espacios y tabulaciones o no seguir un esquema de indentación consistente), se genera un **IndentationError**. Este error se muestra en la consola junto con la línea de código que causó el problema, lo que facilita la identificación del error.

### Detalles
El **IndentationError** puede manifestarse de varias maneras:
- **Error de indentación inesperada**: Ocurre cuando hay un nivel de indentación que no se espera en un determinado contexto.
- **Falta de indentación**: Cuando se espera un bloque de código indentado (por ejemplo, después de una declaración `if`, `for` o `def`), pero no se proporciona.

## Ejemplos
### Ejemplo 1: Indentación Incorrecta
```python
def saludar():
print("Hola, mundo!")  # Indentación incorrecta
```
**Salida:**
```
IndentationError: expected an indented block
```

### Ejemplo 2: Mezcla de Espacios y Tabulaciones
```python
def sumar(a, b):
    return a + b
	return a + b  # Mezcla de espacios y tabulaciones
```
**Salida:**
```
IndentationError: unindent does not match any outer indentation level
```

### Ejemplo 3: Indentación Correcta
```python
def saludar():
    print("Hola, mundo!")  # Indentación correcta
```
**Salida:**
```
Hola, mundo!
```

## Explicación
El **IndentationError** es uno de los errores más comunes que enfrentan los programadores, especialmente aquellos que son nuevos en Python. Algunos puntos a tener en cuenta para evitar este error son:

- **Consistencia**: Es importante ser consistente en el uso de espacios o tabulaciones. Se recomienda elegir uno y stick con él a lo largo del código.
- **Configuración del Editor**: Muchos editores de texto permiten configurar la inserción automática de espacios en lugar de tabulaciones, lo que puede ayudar a evitar este problema.
- **Revisar el Contexto**: Al agregar nuevas líneas de código, asegúrate de que la indentación corresponde al bloque de código al que pertenece.

## Resumen en Una Línea
El **IndentationError** en Python indica problemas de indentación en el código, lo que interfiere con la correcta interpretación de la estructura del programa.