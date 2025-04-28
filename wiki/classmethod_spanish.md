<!--
Meta Description: # classmethod en Python: Guía Completa y Ejemplos Prácticos ## Sinopsis `classmethod` es un decorador en Python que permite definir un método que reci...
Meta Keywords: clase, que, classmethod, método, cls
-->

# classmethod en Python: Guía Completa y Ejemplos Prácticos

## Sinopsis
`classmethod` es un decorador en Python que permite definir un método que recibe la clase como primer argumento en lugar de una instancia de la misma. Esto facilita la creación de métodos que están relacionados con la clase y no con una instancia específica.

## Documentación
El decorador `classmethod` se utiliza para definir un método de clase en Python. A diferencia de los métodos de instancia que reciben `self` como primer argumento, los métodos de clase reciben `cls`, que representa la clase en sí misma. Esto es útil para crear métodos que pueden operar sobre las propiedades de la clase o que necesitan crear instancias de la clase.

### Propósito
- Proporcionar una forma de acceder a la clase dentro de un método.
- Permitir que un método opere sobre la clase y no sobre una instancia específica.
- Facilitar la creación de métodos que pueden ser utilizados para fabricar instancias de la clase.

### Uso
Para usar `classmethod`, simplemente se coloca el decorador antes de la definición del método. Aquí hay un ejemplo básico:

```python
class MiClase:
    contador = 0

    @classmethod
    def incrementar_contador(cls):
        cls.contador += 1
        return cls.contador
```

En este ejemplo, `incrementar_contador` es un método de clase que incrementa la variable de clase `contador`.

## Ejemplos

### Ejemplo 1: Uso Básico de classmethod
```python
class Persona:
    cantidad_personas = 0

    def __init__(self, nombre):
        self.nombre = nombre
        Persona.aumentar_cantidad()

    @classmethod
    def aumentar_cantidad(cls):
        cls.cantidad_personas += 1

# Creando instancias
persona1 = Persona("Juan")
persona2 = Persona("Ana")

print(Persona.cantidad_personas)  # Salida: 2
```

### Ejemplo 2: Método de Clase como Fábrica
```python
class Coche:
    def __init__(self, marca):
        self.marca = marca

    @classmethod
    def crear_coche_ford(cls):
        return cls("Ford")

# Creando un coche Ford usando el método de clase
mi_coche = Coche.crear_coche_ford()
print(mi_coche.marca)  # Salida: Ford
```

## Explicación
Al usar `classmethod`, es importante recordar que el primer argumento debe ser siempre `cls`. Esto puede ser confuso para quienes están acostumbrados a trabajar solo con métodos de instancia. Además, los métodos de clase pueden ser llamados tanto desde la clase como desde las instancias de la clase, aunque es buena práctica llamarlos desde la clase para mayor claridad.

### Errores Comunes
- Intentar usar `self` en lugar de `cls` dentro de un método de clase.
- No usar el decorador `@classmethod`, lo que resultará en un error cuando se intente acceder a la clase desde el método.

## Resumen en Una Línea
`classmethod` en Python permite definir métodos que operan con la clase en lugar de las instancias, facilitando así la manipulación de atributos de clase y la creación de instancias.