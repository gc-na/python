<!--
Meta Description: # __name__ en Python: Comprendiendo el Contexto de Ejecución ## Sinopsis El atributo especial `__name__` en Python es fundamental para determinar el c...
Meta Keywords: módulo, __name__, python, que, código
-->

# __name__ en Python: Comprendiendo el Contexto de Ejecución

## Sinopsis
El atributo especial `__name__` en Python es fundamental para determinar el contexto en el que se está ejecutando un módulo, permitiendo que el código se comporte de manera diferente si se ejecuta directamente o se importa en otro módulo.

## Documentación
### Propósito
El atributo `__name__` es una variable especial que se define en cada módulo de Python. Su valor varía dependiendo de cómo se ejecute el código. Si un módulo se ejecuta directamente, `__name__` toma el valor `'__main__'`. Si el módulo es importado desde otro, `__name__` toma el nombre del módulo.

### Uso
El uso más común de `__name__` es para incluir bloques de código que solo deben ejecutarse si el archivo se corre directamente, permitiendo que el mismo archivo funcione tanto como un módulo importable como un script ejecutable.

### Detalles
- Cuando ejecutas un archivo de Python, el intérprete asigna a `__name__` el valor `'__main__'`.
- Al importar un módulo, Python asigna a `__name__` el nombre del archivo, sin la extensión `.py`.

Este comportamiento permite organizar el código de manera que ciertas partes se ejecuten solo en el contexto adecuado, lo que es crucial para pruebas y reutilización de código.

## Ejemplos
1. **Ejemplo básico de uso de `__name__`:**

```python
# archivo: mi_modulo.py

def funcion_importante():
    print("Esta función es importante.")

if __name__ == '__main__':
    print("Este módulo se está ejecutando directamente.")
    funcion_importante()
else:
    print("Este módulo ha sido importado.")
```

- Si ejecutas `mi_modulo.py`, verás:
```
Este módulo se está ejecutando directamente.
Esta función es importante.
```

- Si importas `mi_modulo` en otro archivo:
```python
import mi_modulo
```
Verás:
```
Este módulo ha sido importado.
```

2. **Ejemplo con importaciones:**

```python
# archivo: otro_modulo.py

import mi_modulo
```
Este código solo imprimirá "Este módulo ha sido importado." al importar `mi_modulo`.

## Explicación
Un error común es olvidar utilizar `__name__` cuando se desarrolla un módulo que podría ser ejecutado o importado. Esto puede llevar a la ejecución accidental de código no deseado al importar el módulo en otros scripts.

También es importante recordar que `__name__` solo se evalúa al momento de la ejecución; por lo tanto, si cambias la estructura de tu código y no verificas `__name__`, podrías encontrar comportamientos inesperados.

## Resumen en una línea
El atributo `__name__` en Python permite determinar si un módulo se está ejecutando directamente o como parte de otro módulo, facilitando un control adecuado del flujo de ejecución.