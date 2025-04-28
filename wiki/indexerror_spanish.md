<!--
Meta Description: # Error de Índice (IndexError) en Python: Causas y Soluciones ## Sinopsis El `IndexError` en Python es una excepción que se levanta cuando se intenta ...
Meta Keywords: índice, indexerror, python, que, mi_lista
-->

# Error de Índice (IndexError) en Python: Causas y Soluciones

## Sinopsis
El `IndexError` en Python es una excepción que se levanta cuando se intenta acceder a un índice que está fuera del rango válido de una lista, tupla o cualquier otro tipo de secuencia. Este error es común en la manipulación de estructuras de datos y es fundamental entenderlo para evitar interrupciones en el flujo de un programa.

## Documentación
El `IndexError` es parte de las excepciones integradas en Python. Ocurre cuando se intenta acceder a un índice que no existe en la secuencia. Por ejemplo, si se tiene una lista de tres elementos y se intenta acceder al cuarto elemento, Python generará un `IndexError`.

### Propósito
El propósito de esta excepción es alertar al programador de que el índice utilizado para acceder a un elemento no es válido, lo que permite manejar el error de manera controlada.

### Uso
Para manejar un `IndexError`, se puede utilizar un bloque `try-except`. Esto permite que el programa continúe ejecutándose incluso si se produce este error. Aquí hay un ejemplo básico de cómo se puede utilizar:

```python
mi_lista = [1, 2, 3]

try:
    print(mi_lista[5])
except IndexError:
    print("Índice fuera de rango.")
```

### Detalles
- **Tipo de Excepción:** El `IndexError` es una subclase de la clase `LookupError`.
- **Mensajes de Error:** El mensaje de error generalmente indica que el índice está fuera de rango, proporcionando información sobre el índice solicitado y el tamaño de la secuencia.

## Ejemplos
### Ejemplo 1: Acceso a un Índice Válido
```python
mi_lista = [10, 20, 30]
print(mi_lista[1])  # Salida: 20
```

### Ejemplo 2: Provocando un IndexError
```python
mi_lista = [10, 20, 30]
print(mi_lista[3])  # Provocará un IndexError
```

### Ejemplo 3: Manejo del Error
```python
mi_lista = [10, 20, 30]

try:
    print(mi_lista[3])
except IndexError:
    print("Error: Índice fuera de rango.")
```
Salida: `Error: Índice fuera de rango.`

## Explicación
Un `IndexError` suele ocurrir por varias razones:
- **Acceso a índices negativos:** Aunque en Python se pueden usar índices negativos para acceder a elementos desde el final de la lista, si el índice negativo es menor que el tamaño negativo de la lista, se levantará un `IndexError`.
  
```python
mi_lista = [1, 2, 3]
print(mi_lista[-4])  # Provocará un IndexError
```

- **Modificación de la lista durante la iteración:** Si se modifica la lista (añadiendo o eliminando elementos) mientras se itera sobre ella, también se pueden producir errores de índice.

### Notas Adicionales
- Siempre se recomienda verificar la longitud de la lista antes de acceder a un índice específico para evitar errores.
- Utilizar funciones como `len()` puede ayudar a asegurarse de que el acceso a índices sea seguro.

## Resumen en una línea
El `IndexError` en Python se produce al intentar acceder a un índice que está fuera del rango de una lista o secuencia, y puede ser manejado con un bloque `try-except` para evitar que el programa se detenga.