<!--
Meta Description: # Función divmod en Python: División y Módulo en un Solo Paso ## Sinopsis La función `divmod` en Python es una herramienta útil que permite realizar l...
Meta Keywords: cociente, residuo, divmod, que, python
-->

# Función divmod en Python: División y Módulo en un Solo Paso

## Sinopsis
La función `divmod` en Python es una herramienta útil que permite realizar la división de dos números y obtener simultáneamente el cociente y el residuo. Esta función es especialmente práctica cuando se necesita tanto el resultado de la división como el resto, evitando así cálculos adicionales.

## Documentación
La función `divmod` se utiliza para calcular el cociente y el residuo de dos números. Su sintaxis es la siguiente:

```python
divmod(a, b)
```

### Parámetros
- **a**: Un número entero o flotante que representa el dividendo.
- **b**: Un número entero o flotante que representa el divisor. Debe ser diferente de cero.

### Valor de retorno
La función devuelve una tupla que contiene dos elementos:
1. El cociente de la división entre `a` y `b` (parte entera).
2. El residuo de la división entre `a` y `b`.

### Ejemplo de Uso
```python
resultado = divmod(9, 4)
print(resultado)  # Salida: (2, 1)
```

En este ejemplo, el cociente de `9` dividido por `4` es `2` y el residuo es `1`.

## Ejemplos
Aquí tienes algunos ejemplos adicionales para ilustrar el uso de `divmod`:

1. **Ejemplo con números enteros:**
   ```python
   cociente, residuo = divmod(15, 6)
   print(f"Cociente: {cociente}, Residuo: {residuo}")  # Salida: Cociente: 2, Residuo: 3
   ```

2. **Ejemplo con números negativos:**
   ```python
   cociente, residuo = divmod(-15, 6)
   print(f"Cociente: {cociente}, Residuo: {residuo}")  # Salida: Cociente: -3, Residuo: 3
   ```

3. **Ejemplo con números flotantes:**
   ```python
   cociente, residuo = divmod(10.5, 2)
   print(f"Cociente: {cociente}, Residuo: {residuo}")  # Salida: Cociente: 5.0, Residuo: 0.5
   ```

## Explicación
Al usar `divmod`, es importante recordar que el divisor (el segundo parámetro) no puede ser cero, ya que esto provocará un error de división por cero (`ZeroDivisionError`). Además, el resultado del cociente siempre es un número entero, lo que significa que cualquier valor decimal se descarta.

### Errores Comunes
- **División por cero**: Siempre asegúrate de que `b` no sea cero antes de llamar a `divmod`.
- **Confusión con tipos de datos**: `divmod` puede trabajar con enteros y flotantes, pero el resultado es distinto. Por ejemplo, el cociente siempre será un entero, mientras que el residuo puede ser un número con decimales si se trabaja con flotantes.

## Resumen en una línea
La función `divmod` en Python permite obtener simultáneamente el cociente y el residuo de una división, facilitando cálculos matemáticos eficientes.