<!--
Meta Description: # ExceptionGroup en Python: Manejo de Excepciones Múltiples ## Sinopsis `ExceptionGroup` es una nueva característica introducida en Python 3.11 que pe...
Meta Keywords: exceptiongroup, excepciones, una, múltiples, que
-->

# ExceptionGroup en Python: Manejo de Excepciones Múltiples

## Sinopsis
`ExceptionGroup` es una nueva característica introducida en Python 3.11 que permite el manejo de múltiples excepciones en un solo bloque de código. Proporciona una manera eficiente y organizada de tratar errores que pueden surgir de diferentes contextos en la ejecución de un programa.

## Documentación
### Propósito
`ExceptionGroup` es diseñado para gestionar múltiples excepciones que pueden ser lanzadas simultáneamente. Esta característica es especialmente útil en aplicaciones concurrentes o asincrónicas donde varias operaciones pueden fallar al mismo tiempo.

### Uso
Para utilizar `ExceptionGroup`, primero debes importar la clase desde el módulo `exceptions`. Puedes crear una instancia de `ExceptionGroup` pasando una lista de excepciones. Luego, puedes manejar estas excepciones como un único grupo.

**Sintaxis básica:**
```python
from exceptions import ExceptionGroup

# Ejemplo de creación de un ExceptionGroup
grupo = ExceptionGroup("Errores de operaciones", [excepcion1, excepcion2])
```

### Detalles
- `ExceptionGroup` permite agrupar excepciones relacionadas, lo que facilita su manejo como una sola entidad.
- Puedes acceder a las excepciones individuales a través del atributo `exceptions` de la instancia de `ExceptionGroup`.
- La función `__str__` se puede utilizar para obtener una representación en cadena del grupo de excepciones, mostrando cada excepción de manera clara.

## Ejemplos
### Ejemplo básico de uso
```python
from exceptions import ExceptionGroup

def funcion_con_fallas():
    raise ValueError("Error de valor")
    
def otra_funcion_con_fallas():
    raise TypeError("Error de tipo")

try:
    funcion_con_fallas()
    otra_funcion_con_fallas()
except ExceptionGroup as eg:
    print(f"Se han producido múltiples excepciones: {eg}")
    for e in eg.exceptions:
        print(e)
```

### Ejemplo en un contexto asincrónico
```python
import asyncio
from exceptions import ExceptionGroup

async def tarea_1():
    raise ValueError("Error en tarea 1")

async def tarea_2():
    raise TypeError("Error en tarea 2")

async def main():
    try:
        await asyncio.gather(tarea_1(), tarea_2())
    except ExceptionGroup as eg:
        print(f"Se han producido múltiples excepciones: {eg}")

asyncio.run(main())
```

## Explicación
### Errores Comunes
- **No manejo de excepciones**: Es común olvidar manejar el `ExceptionGroup`, lo que puede llevar a que las excepciones pasen desapercibidas.
- **Confusión con excepciones individuales**: Al agrupar excepciones, puede ser fácil perder de vista la naturaleza de cada excepción. Asegúrate de revisar cada excepción en el grupo.

### Notas Adicionales
- `ExceptionGroup` es especialmente útil en el contexto de programación concurrente, donde múltiples tareas pueden generar errores simultáneamente.
- La implementación de `ExceptionGroup` es una mejora significativa en comparación con el manejo de excepciones tradicionales, ya que permite un enfoque más estructurado y claro.

## Resumen en Una Línea
`ExceptionGroup` en Python permite manejar múltiples excepciones simultáneamente, facilitando el control de errores en entornos concurrentes y asincrónicos.