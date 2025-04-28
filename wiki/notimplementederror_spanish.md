<!--
Meta Description: # NotImplementedError en Python: Entendiendo su Uso y Aplicaciones ## Sinopsis El `NotImplementedError` es una excepción en Python que se utiliza para...
Meta Keywords: que, método, notimplementederror, implementado, ser
-->

# NotImplementedError en Python: Entendiendo su Uso y Aplicaciones

## Sinopsis
El `NotImplementedError` es una excepción en Python que se utiliza para indicar que un método o función aún no ha sido implementado. Es comúnmente utilizada como un marcador en clases abstractas o métodos que deben ser sobrescritos en clases derivadas.

## Documentación
El `NotImplementedError` es una subclase de la clase `RuntimeError`. Su propósito principal es señalar que un método o función ha sido definido, pero no se ha proporcionado una implementación concreta. Es especialmente útil en el contexto de la programación orientada a objetos, donde se espera que las subclases implementen ciertos métodos que son esenciales para su funcionamiento.

### Propósito
- Indicar que un método no ha sido implementado.
- Facilitar la identificación de métodos que deben ser completados.
- Mejorar la legibilidad del código al documentar claramente las intenciones del desarrollador.

### Uso
El `NotImplementedError` se lanza típicamente en métodos de clases base o abstractas. Al definir un método, el desarrollador puede usar esta excepción para indicar que la implementación debe ser proporcionada por las subclases. 

#### Ejemplo de definición de un método:
```python
class MiClaseBase:
    def mi_metodo(self):
        raise NotImplementedError("Este método debe ser implementado por la subclase.")
```

## Ejemplos
### Ejemplo 1: Uso básico de NotImplementedError
```python
class Animal:
    def hacer_sonido(self):
        raise NotImplementedError("Este método debe ser implementado por la subclase.")

class Perro(Animal):
    def hacer_sonido(self):
        return "Guau!"

class Gato(Animal):
    def hacer_sonido(self):
        return "Miau!"

# Uso
mi_perro = Perro()
print(mi_perro.hacer_sonido())  # Salida: Guau!

mi_gato = Gato()
print(mi_gato.hacer_sonido())    # Salida: Miau!
```

### Ejemplo 2: Intento de llamar a un método no implementado
```python
class Vehiculo:
    def conducir(self):
        raise NotImplementedError("Este método debe ser implementado por la subclase.")

class Bicicleta(Vehiculo):
    def conducir(self):
        return "Montando la bicicleta."

# Intentar llamar al método
mi_bicicleta = Bicicleta()
print(mi_bicicleta.conducir())  # Salida: Montando la bicicleta.
# mi_vehiculo = Vehiculo()
# print(mi_vehiculo.conducir())  # Esto lanzará NotImplementedError
```

## Explicación
Al usar `NotImplementedError`, los desarrolladores deben tener en cuenta que esta excepción es útil para definir interfaces y garantizar que las subclases proporcionen implementaciones específicas. Sin embargo, es importante recordar que si se intenta llamar a un método que lanza `NotImplementedError` sin haberlo implementado en una subclase, se generará un error en tiempo de ejecución.

### Errores Comunes
- Olvidar implementar el método en la subclase, lo que resultará en un `NotImplementedError` al intentar llamar al método.
- No proporcionar un mensaje claro en la excepción, lo que puede dificultar la identificación del problema.

## Resumen en una línea
`NotImplementedError` es una excepción en Python que indica que un método no ha sido implementado y debe ser completado por las subclases.