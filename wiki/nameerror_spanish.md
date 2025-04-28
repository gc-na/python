<!--
Meta Description: # NameError en Python: Comprendiendo el Error de Nombre ## Sinopsis El `NameError` en Python es una excepción que se genera cuando se intenta utilizar...
Meta Keywords: nameerror, que, python, error, variables
-->

# NameError en Python: Comprendiendo el Error de Nombre

## Sinopsis
El `NameError` en Python es una excepción que se genera cuando se intenta utilizar una variable o función que no ha sido definida en el ámbito actual del código. Este error es común entre los programadores principiantes y puede ser un indicador de errores tipográficos o de omisiones en la declaración de variables.

## Documentación
El `NameError` se produce cuando Python no encuentra un nombre en el espacio de nombres actual. Esto puede ocurrir por varias razones, que incluyen:

- Uso de variables sin haberlas definido previamente.
- Errores tipográficos en los nombres de las variables.
- Intentar acceder a funciones o clases que no han sido importadas o definidas.

### Propósito
El propósito del `NameError` es alertar a los desarrolladores sobre problemas en el código que necesitan ser corregidos antes de que el programa pueda ejecutarse correctamente.

### Uso
El `NameError` es un tipo de excepción que puede ser manejada mediante un bloque `try-except`. Esto permite a los desarrolladores capturar el error y tomar medidas, como proporcionar un mensaje de error más amigable.

### Detalles
- La excepción `NameError` es una subclase de `Exception`.
- Se puede producir en cualquier parte del código, incluyendo dentro de funciones y métodos.

## Ejemplos

### Ejemplo 1: Variable no definida
```python
print(x)
```
**Salida:**
```
NameError: name 'x' is not defined
```
En este ejemplo, se intenta imprimir la variable `x` sin haberla definido previamente.

### Ejemplo 2: Error tipográfico
```python
name = "Python"
print(nam)
```
**Salida:**
```
NameError: name 'nam' is not defined
```
Aquí, se produce un `NameError` debido a un error tipográfico en el nombre de la variable.

### Ejemplo 3: Función no definida
```python
def my_function():
    return "Hola, mundo"

print(my_funtion())
```
**Salida:**
```
NameError: name 'my_funtion' is not defined
```
El error ocurre porque se llamó a la función con un nombre incorrecto.

## Explicación
Los `NameError` son comunes entre los nuevos programadores que aún no están familiarizados con el ámbito de las variables y la definición de funciones. Aquí hay algunas notas adicionales:

- **Ámbito de las Variables:** Asegúrate de que las variables estén definidas en el mismo ámbito donde intentas acceder a ellas. Las variables definidas dentro de una función no son accesibles fuera de ella, a menos que se retornen o se declaren como globales.
  
- **Importaciones:** Si estás utilizando funciones o clases de módulos externos, asegúrate de haberlos importado correctamente. Un `NameError` puede surgir si olvidas importar un módulo.

- **Errores Tipográficos:** Siempre verifica la ortografía de tus variables y funciones. Un simple error tipográfico puede resultar en un `NameError`.

## Resumen en Una Línea
El `NameError` en Python se produce cuando se intenta acceder a una variable o función que no ha sido definida en el ámbito actual del código.