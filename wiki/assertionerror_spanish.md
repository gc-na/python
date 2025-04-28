<!--
Meta Description: # AssertionError en Python: Comprendiendo Errores de Aserción ## Sinopsis AssertionError es una excepción en Python que se lanza cuando una afirmación...
Meta Keywords: las, python, que, para, aserciones
-->

# AssertionError en Python: Comprendiendo Errores de Aserción

## Sinopsis
AssertionError es una excepción en Python que se lanza cuando una afirmación (assert) falla. Se utiliza principalmente en la depuración de código para garantizar que ciertas condiciones se cumplan durante la ejecución del programa.

## Documentación
La declaración `assert` en Python se utiliza para realizar pruebas de aserción. Cuando se evalúa una condición y esta resulta ser falsa, Python genera un AssertionError. Esto es útil para detectar errores en código durante el desarrollo y las pruebas.

### Propósito
El propósito de la aserción es validar que las condiciones esperadas se cumplen. Si no, se lanza un AssertionError, lo que ayuda a los desarrolladores a identificar problemas en el código.

### Uso
La sintaxis básica de una afirmación es:
```python
assert condición, "Mensaje de error opcional"
```
- **condición**: Una expresión que se espera que sea verdadera.
- **mensaje de error opcional**: Un mensaje que se mostrará si la condición es falsa.

### Detalles
- Las aserciones son herramientas de depuración y no deben ser utilizadas para manejar errores en producción.
- Las afirmaciones se pueden desactivar en el momento de ejecutar el script de Python, utilizando la opción `-O` (optimize). En este caso, todas las aserciones se omiten.

## Ejemplos
### Ejemplo Básico
```python
def dividir(a, b):
    assert b != 0, "El divisor no puede ser cero."
    return a / b

print(dividir(10, 2))  # Salida: 5.0
print(dividir(10, 0))  # Lanza AssertionError
```

### Ejemplo con Mensaje Personalizado
```python
def comprobar_edad(edad):
    assert edad >= 18, "Debes ser mayor de 18 años para continuar."
    return "Acceso permitido."

print(comprobar_edad(20))  # Salida: "Acceso permitido."
print(comprobar_edad(16))  # Lanza AssertionError con mensaje "Debes ser mayor de 18 años para continuar."
```

## Explicación
### Problemas Comunes
- **Desactivación de Aserciones**: Si se ejecuta el código con la opción `-O`, todas las aserciones serán ignoradas, lo que puede llevar a comportamientos inesperados si se confía en ellas para validar la lógica del programa.
- **Confusión entre Aserciones y Excepciones**: Las aserciones no deben ser utilizadas para manejar errores de entrada o condiciones de error esperadas. Son para condiciones que nunca deberían ocurrir si el código es correcto.

### Notas Adicionales
- Las aserciones son más efectivas durante la fase de desarrollo y prueba, y no deben ser parte del manejo normal de errores en aplicaciones finales.
- Usar mensajes claros y descriptivos en las aserciones puede facilitar la depuración.

## Resumen en Una Línea
AssertionError en Python se lanza cuando una afirmación falla, ayudando a identificar errores durante el desarrollo y las pruebas.