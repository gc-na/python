<!--
Meta Description: # Función chr en Python: Cómo convertir números en caracteres ## Sinopsis La función `chr` en Python es utilizada para convertir un número entero que ...
Meta Keywords: chr, que, python, carácter, función
-->

# Función chr en Python: Cómo convertir números en caracteres

## Sinopsis
La función `chr` en Python es utilizada para convertir un número entero que representa el código Unicode de un carácter en su correspondiente carácter. Esta función es útil en la manipulación de cadenas y en la creación de caracteres a partir de sus valores numéricos.

## Documentación
La función `chr` toma un único argumento, que debe ser un entero que representa un valor Unicode válido (en el rango de 0 a 1114111, es decir, de 0x0000 a 0x10FFFF). Devuelve una cadena de un solo carácter correspondiente a ese valor.

### Uso
```python
chr(i)
```

#### Parámetros
- `i`: Un entero que se encuentra dentro del rango de códigos Unicode.

#### Valor de retorno
Devuelve el carácter correspondiente al código Unicode proporcionado.

### Ejemplo de uso
```python
# Convertir el número 65 en su carácter correspondiente
caracter = chr(65)
print(caracter)  # Salida: A
```

## Ejemplos
### Ejemplo básico
```python
# Ejemplo de uso de chr con diferentes códigos Unicode
print(chr(97))   # Salida: a
print(chr(122))  # Salida: z
print(chr(8364)) # Salida: €
```

### Ejemplo con un rango
```python
# Generar una lista de caracteres del alfabeto en minúsculas
alfabeto_minusculas = [chr(i) for i in range(97, 123)]
print(alfabeto_minusculas)  # Salida: ['a', 'b', 'c', 'd', ... , 'z']
```

## Explicación
Un error común al utilizar la función `chr` es pasar un número que está fuera del rango permitido. Si se intenta usar un número menor que 0 o mayor que 1114111, Python lanzará un `ValueError`.

### Consideraciones
- Recuerda que `chr` devuelve un único carácter. Para cadenas de múltiplos caracteres, se deben utilizar técnicas adicionales como la concatenación.
- La función `ord` es el complemento de `chr`, ya que convierte un carácter en su valor Unicode.

## Resumen en una línea
La función `chr` en Python convierte un número entero, representando un código Unicode, en su carácter correspondiente.