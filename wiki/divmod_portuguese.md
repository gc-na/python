<!--
Meta Description: # Função divmod no Python: Entenda e Aprenda a Usar ## Sinopse A função `divmod` em Python é uma ferramenta útil que combina a divisão inteira e o res...
Meta Keywords: divmod, divisão, função, uma, que
-->

# Função divmod no Python: Entenda e Aprenda a Usar

## Sinopse
A função `divmod` em Python é uma ferramenta útil que combina a divisão inteira e o resto da divisão em uma única operação, facilitando cálculos matemáticos de forma eficiente.

## Documentação
A função `divmod` é uma função embutida em Python que recebe dois números (dividendo e divisor) e retorna uma tupla contendo o quociente e o resto da divisão. A sintaxe da função é:

```python
divmod(a, b)
```

### Parâmetros
- **a**: O dividendo (número a ser dividido).
- **b**: O divisor (número pelo qual você está dividindo).

### Retorno
`divmod` retorna uma tupla `(quociente, resto)` onde:
- **quociente** é o resultado da divisão inteira de `a` por `b`.
- **resto** é o que sobra da divisão.

### Exceções
Se `b` for zero, a função lançará uma exceção `ZeroDivisionError`, já que a divisão por zero não é definida.

## Exemplos
Aqui estão alguns exemplos simples que demonstram o uso da função `divmod`:

```python
# Exemplo 1: Divisão simples
resultado = divmod(10, 3)
print(resultado)  # Saída: (3, 1)

# Exemplo 2: Divisão com números negativos
resultado_negativo = divmod(-10, 3)
print(resultado_negativo)  # Saída: (-4, 2)

# Exemplo 3: Divisão com divisor negativo
resultado_divisor_negativo = divmod(10, -3)
print(resultado_divisor_negativo)  # Saída: (-4, -2)
```

## Explicação
A função `divmod` é particularmente útil quando você precisa tanto do quociente quanto do resto em uma operação. Usá-la evita a necessidade de realizar duas operações separadas e, portanto, pode tornar o código mais limpo e eficiente. 

Um ponto a ser observado é que a função `divmod` segue as regras de arredondamento da divisão inteira, onde o quociente é arredondado para o menor número inteiro mais próximo. Isso pode levar a resultados que podem não ser intuitivos, especialmente quando lidamos com números negativos.

### Armadilhas Comuns
- **Divisão por zero**: Tentar usar `divmod(a, 0)` resultará em um `ZeroDivisionError`. Sempre verifique se o divisor não é zero antes de chamar a função.
- **Interpretando os resultados**: Lembre-se de que o quociente é sempre arredondado para baixo. Isso pode surpreender os novos programadores.

## Resumo em Uma Linha
A função `divmod` em Python fornece uma maneira eficiente de obter simultaneamente o quociente e o resto de uma divisão inteira.