<!--
Meta Description: # Diccionarios en Python: Uso y Ejemplos ## Sinopsis El tipo de dato `dict`, o diccionario, en Python es una colección no ordenada de elementos, donde...
Meta Keywords: python, los, diccionario, una, clave
-->

# Diccionarios en Python: Uso y Ejemplos

## Sinopsis
El tipo de dato `dict`, o diccionario, en Python es una colección no ordenada de elementos, donde cada elemento es un par clave-valor. Es ampliamente utilizado para almacenar datos en un formato estructurado y accesible.

## Documentación
El diccionario en Python es una estructura de datos mutable que permite almacenar un conjunto de elementos en forma de pares clave-valor. Cada clave debe ser única y es utilizada para acceder a su valor correspondiente. Los diccionarios son ideales para situaciones donde se necesita un acceso rápido a los datos.

### Creación de un Diccionario
Los diccionarios pueden ser creados utilizando llaves `{}` o la función `dict()`. Aquí hay un ejemplo de ambas formas:

```python
# Usando llaves
mi_diccionario = {'nombre': 'Juan', 'edad': 30, 'ciudad': 'Madrid'}

# Usando la función dict()
mi_diccionario2 = dict(nombre='Ana', edad=25, ciudad='Barcelona')
```

### Acceso a Elementos
Puedes acceder a los valores en un diccionario utilizando su clave:

```python
print(mi_diccionario['nombre'])  # Salida: Juan
```

### Modificación de Elementos
Los elementos dentro de un diccionario pueden ser modificados:

```python
mi_diccionario['edad'] = 31
print(mi_diccionario['edad'])  # Salida: 31
```

### Métodos Comunes
- `keys()`: Devuelve una vista de las claves en el diccionario.
- `values()`: Devuelve una vista de los valores en el diccionario.
- `items()`: Devuelve una vista de los pares clave-valor.

## Ejemplos
### Ejemplo 1: Creación y Acceso

```python
frutas = {'manzana': 3, 'naranja': 5, 'plátano': 2}
print(frutas['naranja'])  # Salida: 5
```

### Ejemplo 2: Modificación y Adición

```python
frutas['manzana'] = 4  # Modificar valor
frutas['pera'] = 6     # Añadir nueva clave-valor
print(frutas)  # Salida: {'manzana': 4, 'naranja': 5, 'plátano': 2, 'pera': 6}
```

### Ejemplo 3: Iteración

```python
for fruta, cantidad in frutas.items():
    print(f'Hay {cantidad} {fruta}(s)')
```

## Explicación
Al trabajar con diccionarios, es importante recordar que las claves deben ser inmutables (como cadenas, números o tuplas), mientras que los valores pueden ser de cualquier tipo. Un error común es intentar usar listas como claves, lo cual generará un `TypeError`. Además, aunque los diccionarios en versiones recientes de Python mantienen el orden de inserción, no debes confiar en esto como una característica oficial en versiones anteriores.

## Resumen en Una Línea
El tipo de dato `dict` en Python permite almacenar datos en pares clave-valor de manera eficiente y accesible.