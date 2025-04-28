<!--
Meta Description: # Filtro en Python: Cómo usar la función filter para manipular listas ## Sinopsis La función `filter` en Python permite filtrar elementos de una itera...
Meta Keywords: función, filter, una, que, iterable
-->

# Filtro en Python: Cómo usar la función filter para manipular listas

## Sinopsis
La función `filter` en Python permite filtrar elementos de una iterable (como listas o tuplas) utilizando una función que evalúa cada elemento y determina si debe incluirse en el resultado.

## Documentación
La función `filter` se utiliza para construir un iterador a partir de aquellos elementos de una iterable para los cuales la función especificada retorna `True`. Su sintaxis es la siguiente:

```python
filter(función, iterable)
```

### Parámetros
- **función**: Una función que toma un solo argumento y devuelve `True` o `False`. Si es `None`, se utiliza la identidad, es decir, se filtran los elementos que son falsy (0, `None`, `False`, etc.).
- **iterable**: Cualquier objeto que sea iterable, como listas, tuplas, conjuntos, etc.

### Retorno
Devuelve un iterador que contiene los elementos de la iterable que pasaron la prueba de la función.

## Ejemplos
### Ejemplo 1: Filtrar números pares de una lista
```python
numeros = [1, 2, 3, 4, 5, 6]
pares = filter(lambda x: x % 2 == 0, numeros)
print(list(pares))  # Salida: [2, 4, 6]
```

### Ejemplo 2: Filtrar cadenas no vacías de una lista
```python
cadenas = ["hola", "", "mundo", " ", "python"]
no_vacias = filter(lambda x: x.strip() != "", cadenas)
print(list(no_vacias))  # Salida: ['hola', 'mundo', ' ']
```

### Ejemplo 3: Filtrar números positivos
```python
numeros = [-10, 15, 0, 20, -5]
positivos = filter(lambda x: x > 0, numeros)
print(list(positivos))  # Salida: [15, 20]
```

## Explicación
Algunos errores comunes al usar `filter` incluyen:

1. **Olvidar convertir el resultado a una lista**: `filter` devuelve un objeto iterable. Si intentas imprimirlo directamente sin convertirlo a una lista, obtendrás un objeto en lugar de los elementos filtrados.
   
2. **Usar una función que no devuelve booleanos**: Asegúrate de que la función usada con `filter` retorne `True` o `False` para evitar comportamientos inesperados.

3. **Confundir `filter` con `map`**: `filter` se utiliza para seleccionar elementos, mientras que `map` transforma cada elemento de la iterable. Es importante no mezclarlos al programar.

## Resumen en una línea
La función `filter` en Python permite seleccionar elementos de una iterable basándose en una función que evalúa cada elemento como verdadero o falso.