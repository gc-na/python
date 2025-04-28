<!--
Meta Description: # ASCII en Python: Guía Completa para Manejo de Cadenas ## Sinopsis ASCII (American Standard Code for Information Interchange) es un estándar de codif...
Meta Keywords: ascii, python, ord, caracteres, chr
-->

# ASCII en Python: Guía Completa para Manejo de Cadenas

## Sinopsis
ASCII (American Standard Code for Information Interchange) es un estándar de codificación de caracteres utilizado en programación. En Python, se utiliza para convertir caracteres a sus representaciones numéricas y viceversa, permitiendo manipular textos de manera eficiente.

## Documentación
En Python, la codificación ASCII se utiliza principalmente a través de las funciones `ord()` y `chr()`. 

- **`ord()`**: Esta función toma un carácter (una cadena de longitud 1) y devuelve su valor entero correspondiente en la tabla ASCII.
  
  **Uso**: 
  ```python
  valor_ascii = ord('A')  # Devuelve 65
  ```

- **`chr()`**: Esta función hace la operación inversa; toma un entero y devuelve el carácter correspondiente en la tabla ASCII.
  
  **Uso**: 
  ```python
  caracter = chr(65)  # Devuelve 'A'
  ```

### Propósito
El propósito de estas funciones es facilitar la interacción con caracteres y su representación numérica, lo que es común en diversas aplicaciones, desde el procesamiento de texto hasta la codificación y decodificación de datos.

## Ejemplos

### Ejemplo de `ord()`
```python
# Obtener el valor ASCII de un carácter
caracter = 'B'
valor_ascii = ord(caracter)
print(f"El valor ASCII de '{caracter}' es: {valor_ascii}")  # Salida: 66
```

### Ejemplo de `chr()`
```python
# Convertir un valor ASCII a un carácter
valor_ascii = 90
caracter = chr(valor_ascii)
print(f"El carácter correspondiente al valor ASCII {valor_ascii} es: '{caracter}'")  # Salida: 'Z'
```

### Ejemplo combinado
```python
# Convertir una cadena a sus valores ASCII
cadena = "Hola"
valores_ascii = [ord(c) for c in cadena]
print(f"Los valores ASCII de '{cadena}' son: {valores_ascii}")  # Salida: [72, 111, 108, 97]
```

## Explicación
Al trabajar con ASCII en Python, es importante tener en cuenta que:

1. **Rango de ASCII**: Solo puedes utilizar `ord()` y `chr()` con caracteres que estén en el rango de 0 a 127, ya que el ASCII estándar solo cubre estos valores. Para caracteres extendidos o Unicode, debes utilizar otras codificaciones.

2. **Errores comunes**: Un error común es intentar usar `ord()` con cadenas de más de un carácter, lo cual generará un `TypeError`. Asegúrate de que la cadena tenga longitud 1.

3. **Compatibilidad**: Python maneja automáticamente la codificación y decodificación de cadenas. Sin embargo, al trabajar con datos de archivos o redes, debes ser consciente del formato de codificación para evitar problemas de interpretación.

## Resumen en una línea
ASCII en Python permite convertir caracteres a valores numéricos y viceversa, facilitando la manipulación de cadenas de texto.