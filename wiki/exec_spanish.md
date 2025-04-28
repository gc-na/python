<!--
Meta Description: # Uso de `exec` en Python: Ejecución Dinámica de Código ## Sinopsis El comando `exec` en Python permite la ejecución dinámica de código Python conteni...
Meta Keywords: código, exec, que, python, ejecución
-->

# Uso de `exec` en Python: Ejecución Dinámica de Código

## Sinopsis
El comando `exec` en Python permite la ejecución dinámica de código Python contenido en cadenas de texto. Es una herramienta poderosa que ejecuta código en el contexto actual, lo que puede ser útil en diversas aplicaciones, aunque también puede presentar riesgos de seguridad.

## Documentación
### Propósito
El objetivo de `exec` es permitir que los desarrolladores ejecuten código Python de manera dinámica. Esto significa que se puede construir y ejecutar código en tiempo de ejecución, lo que proporciona flexibilidad en situaciones donde el código no se puede determinar hasta que se ejecute el programa.

### Uso
La sintaxis básica de `exec` es la siguiente:

```python
exec(codigo, globals=None, locals=None)
```

- **codigo**: Una cadena que contiene el código Python que se desea ejecutar.
- **globals**: (Opcional) Un diccionario que define el espacio de nombres global en el que se ejecutará el código.
- **locals**: (Opcional) Un diccionario que define el espacio de nombres local en el que se ejecutará el código.

Si no se proporcionan `globals` y `locals`, `exec` utilizará el espacio de nombres actual.

### Detalles
- `exec` puede ejecutar múltiples líneas de código.
- Puede acceder y modificar variables en el contexto donde se ejecuta.
- Dado que `exec` ejecuta el código de manera dinámica, es importante manejarlo con cuidado para evitar la ejecución de código malicioso.

## Ejemplos

### Ejemplo 1: Ejecución de una sola línea de código
```python
codigo = "print('Hola, Mundo!')"
exec(codigo)
```

### Ejemplo 2: Ejecución de múltiples líneas de código
```python
codigo = """
def saludo(nombre):
    return f'Hola, {nombre}'

print(saludo('Juan'))
"""
exec(codigo)
```

### Ejemplo 3: Uso de espacios de nombres personalizados
```python
codigo = "a = 5; b = 10; resultado = a + b"
espacio_global = {}
espacio_local = {}
exec(codigo, espacio_global, espacio_local)
print(espacio_local['resultado'])  # Salida: 15
```

## Explicación
### Puntos Comunes y Precauciones
- **Seguridad**: Utilizar `exec` con código no confiable puede llevar a vulnerabilidades de seguridad, como la ejecución de código malicioso. Se recomienda evitar su uso en situaciones donde el código proviene de entradas del usuario.
- **Depuración**: El uso de `exec` puede dificultar la depuración del código, ya que el flujo de ejecución no es tan claro como en el código estático.
- **Alternativas**: En muchos casos, existen alternativas más seguras y claras, como funciones o clases, que logran resultados similares sin los riesgos asociados a `exec`.

## Resumen en una Línea
El comando `exec` en Python permite ejecutar dinámicamente código Python contenido en cadenas, ofreciendo gran flexibilidad pero presentando riesgos de seguridad.