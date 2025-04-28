<!--
Meta Description: # FileNotFoundError en Python: Manejo de Errores al Trabajar con Archivos ## Sinopsis El `FileNotFoundError` es una excepción en Python que se lanza c...
Meta Keywords: archivo, que, filenotfounderror, python, error
-->

# FileNotFoundError en Python: Manejo de Errores al Trabajar con Archivos

## Sinopsis
El `FileNotFoundError` es una excepción en Python que se lanza cuando se intenta acceder a un archivo o directorio que no existe. Este error es fundamental para el manejo adecuado de archivos y asegura que los desarrolladores puedan manejar situaciones donde los recursos no están disponibles.

## Documentación
### Propósito
El propósito del `FileNotFoundError` es alertar al desarrollador sobre la ausencia de un archivo o directorio que se intenta abrir, leer, o modificar. Esta excepción es parte de la jerarquía de excepciones de Python y es una subclase de `OSError`.

### Uso
`FileNotFoundError` se genera automáticamente cuando se utilizan funciones de manejo de archivos, como `open()`, y el archivo especificado no se encuentra en la ruta dada. Para manejar este error, se utiliza un bloque `try`/`except`.

### Detalles
- **Tipo de Excepción**: `FileNotFoundError` es lanzado específicamente para indicar la falta de un archivo.
- **Código de Error**: Normalmente, este error se presenta con el código de error `Errno 2`, indicando que el archivo no fue encontrado.
- **Manejo**: Es recomendable usar bloques `try`/`except` para capturar esta excepción y proporcionar mensajes de error claros a los usuarios o realizar acciones alternativas.

## Ejemplos

### Ejemplo 1: Captura de `FileNotFoundError`
```python
try:
    with open('archivo_inexistente.txt', 'r') as archivo:
        contenido = archivo.read()
except FileNotFoundError:
    print("El archivo no fue encontrado. Por favor verifica la ruta.")
```

### Ejemplo 2: Verificación de la existencia del archivo
```python
import os

ruta_archivo = 'archivo_inexistente.txt'
if not os.path.exists(ruta_archivo):
    print("El archivo no existe.")
else:
    with open(ruta_archivo, 'r') as archivo:
        contenido = archivo.read()
```

## Explicación
### Errores Comunes
- **Ruta Incorrecta**: Uno de los errores más frecuentes es proporcionar una ruta incorrecta al archivo. Asegúrate de que la ruta sea correcta y que el archivo esté en la ubicación esperada.
- **Extensiones de Archivo**: A veces, el archivo puede existir, pero con una extensión diferente. Verifica que el nombre y la extensión del archivo sean correctos.
- **Permisos**: Aunque `FileNotFoundError` no se refiere directamente a problemas de permisos, es importante tener en cuenta que un archivo puede no ser accesible debido a restricciones de permisos.

### Notas Adicionales
- Este error es parte de las buenas prácticas de programación en Python, ya que fomenta el uso de manejo de excepciones y la validación de la existencia de archivos antes de realizar operaciones.

## Resumen en una Línea
El `FileNotFoundError` en Python se lanza cuando se intenta acceder a un archivo o directorio que no existe, y su manejo es esencial para evitar fallos en el programa.