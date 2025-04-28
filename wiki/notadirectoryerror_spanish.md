<!--
Meta Description: # NotADirectoryError en Python: Comprendiendo el Error de No Directorio ## Sinopsis `NotADirectoryError` es una excepción en Python que se produce cua...
Meta Keywords: que, archivo, directorio, notadirectoryerror, error
-->

# NotADirectoryError en Python: Comprendiendo el Error de No Directorio

## Sinopsis
`NotADirectoryError` es una excepción en Python que se produce cuando se intenta acceder a una ruta de archivo que se espera que sea un directorio, pero en realidad se trata de un archivo. Este error es parte de la jerarquía de errores de OSError y se utiliza para identificar problemas específicos relacionados con el sistema de archivos.

## Documentación
### Propósito
El propósito de `NotADirectoryError` es proporcionar una forma clara y específica de manejar errores que surgen cuando una operación de directorio se realiza en un archivo. Por ejemplo, si intentas listar el contenido de un archivo en lugar de un directorio, Python levantará esta excepción.

### Uso
`NotADirectoryError` se utiliza generalmente en situaciones donde las funciones de manipulación de archivos y directorios están involucradas. Por ejemplo, al utilizar `os.listdir()` o `os.chdir()`, si se pasa un archivo en lugar de un directorio, se generará este error.

### Detalles
- **Tipo de error**: `NotADirectoryError` es una subclase de `OSError`.
- **Mensaje de error**: El mensaje de error típicamente indica que la operación esperaba un directorio, pero se encontró un archivo.

## Ejemplos
### Ejemplo 1: Uso básico de `NotADirectoryError`
```python
import os

# Supongamos que "archivo.txt" es un archivo, no un directorio
try:
    contenido = os.listdir('archivo.txt')
except NotADirectoryError as e:
    print(f"Error: {e}")
```

### Ejemplo 2: Cambio de directorio
```python
import os

# Supongamos que "documento.pdf" es un archivo
try:
    os.chdir('documento.pdf')
except NotADirectoryError as e:
    print(f"Error: {e}")
```

## Explicación
### Errores Comunes
- **Confusión entre archivos y directorios**: Uno de los errores más comunes es confundir un archivo con un directorio. Este error puede surgir al intentar acceder a rutas de archivos sin verificar su tipo.
- **Rutas incorrectas**: Asegúrate de que las rutas que proporcionas sean correctas y que realmente apunten a directorios.

### Notas Adicionales
- **Manejo de excepciones**: Siempre es recomendable manejar excepciones al trabajar con operaciones de archivos y directorios para prevenir que tu programa se detenga inesperadamente.
- **Compatibilidad**: `NotADirectoryError` está disponible en Python 3.3 y versiones posteriores, y no se encuentra en versiones anteriores.

## Resumen en una línea
`NotADirectoryError` es una excepción en Python que indica que se ha intentado realizar una operación de directorio en un archivo en lugar de en un directorio.