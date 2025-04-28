<!--
Meta Description: # __import__: Cómo Funciona la Importación Dinámica en Python ## Sinopsis El comando `__import__` en Python permite la importación dinámica de módulos...
Meta Keywords: que, __import__, importación, python, módulos
-->

# __import__: Cómo Funciona la Importación Dinámica en Python

## Sinopsis
El comando `__import__` en Python permite la importación dinámica de módulos en tiempo de ejecución, ofreciendo una forma flexible de cargar módulos según sea necesario.

## Documentación
La función `__import__` es una función interna en Python que proporciona la capacidad de importar módulos de manera programática. Se utiliza principalmente cuando el nombre del módulo a importar no se conoce hasta el momento de la ejecución. Aunque su uso directo es poco común en la mayoría de los scripts, es fundamental para ciertos casos de metaprogramación o para construir aplicaciones que requieren cargar módulos de forma dinámica.

### Propósito
- Permitir la importación de módulos cuando su nombre no es conocido en el momento de la escritura del código.
- Facilitar la creación de bibliotecas o herramientas que requieran cargar diferentes módulos a partir de condiciones específicas.

### Uso
La sintaxis básica de `__import__` es la siguiente:

```python
module = __import__('nombre_del_modulo', fromlist=[], level=0)
```

- `nombre_del_modulo`: El nombre del módulo a importar como una cadena.
- `fromlist`: Una lista de submódulos o atributos que se deben importar. Si se omite o está vacía, solo se importará el módulo principal.
- `level`: Un entero que indica el nivel de la importación relativa. Un valor de 0 importa el módulo de manera absoluta, mientras que un valor mayor a 0 permite importaciones relativas.

## Ejemplos
### Ejemplo básico de importación
```python
# Importar el módulo 'math'
math_module = __import__('math')
print(math_module.sqrt(16))  # Salida: 4.0
```

### Importación con fromlist
```python
# Importar solo la función 'sqrt' del módulo 'math'
math_sqrt = __import__('math', fromlist=['sqrt'])
print(math_sqrt.sqrt(25))  # Salida: 5.0
```

### Importación relativa
```python
# Supongamos que estamos en un paquete y queremos importar un submódulo
# __import__('mi_paquete.mi_modulo', level=1)
```

## Explicación
Aunque `__import__` es una función poderosa, su uso puede llevar a confusiones y errores si no se entiende completamente su funcionamiento. Algunos puntos a considerar son:

- **Uso inusual**: En la mayoría de los casos, se prefiere usar la declaración `import` estándar, ya que es más legible y más clara.
- **Importación de submódulos**: Es necesario usar `fromlist` para acceder a funciones o clases específicas de un submódulo.
- **Importaciones relativas**: La utilización del parámetro `level` puede ser confusa. Si se establece un nivel mayor que 0, se requiere que la estructura del paquete esté bien definida.

## Resumen en una línea
`__import__` es una función interna de Python que permite la importación dinámica de módulos en tiempo de ejecución.