<!--
Meta Description: # Função abs() em Python: Entenda o que é e como usá-la ## Sinopse A função `abs()` em Python é uma função embutida que retorna o valor absoluto de um...
Meta Keywords: abs, número, função, python, valor
-->

# Função abs() em Python: Entenda o que é e como usá-la

## Sinopse
A função `abs()` em Python é uma função embutida que retorna o valor absoluto de um número, ou seja, a sua magnitude sem considerar o seu sinal.

## Documentação
A função `abs()` é utilizada para obter o valor absoluto de um número. Ela pode receber um inteiro, um número de ponto flutuante ou um número complexo como argumento. O retorno será sempre um número não negativo.

### Sintaxe
```python
abs(x)
```

### Parâmetros
- **x**: Um número (int, float ou complex) do qual se deseja obter o valor absoluto.

### Retorno
A função retorna o valor absoluto do número fornecido. Para números complexos, ela retorna a magnitude do número complexo.

### Exemplos de Uso
Aqui estão alguns exemplos práticos de como utilizar a função `abs()` em Python:

```python
# Exemplo 1: Usando abs() com um número inteiro
numero_inteiro = -10
print(abs(numero_inteiro))  # Saída: 10

# Exemplo 2: Usando abs() com um número de ponto flutuante
numero_float = -15.75
print(abs(numero_float))  # Saída: 15.75

# Exemplo 3: Usando abs() com um número complexo
numero_complexo = 3 - 4j
print(abs(numero_complexo))  # Saída: 5.0
```

## Explicação
A função `abs()` é bastante direta, mas há algumas considerações a serem feitas:

- **Números Negativos**: Quando um número negativo é passado como argumento, a função simplesmente remove o sinal negativo.
- **Números Complexos**: Para números complexos (a + bj), o valor absoluto é calculado usando a fórmula √(a² + b²), que representa a distância do número até a origem no plano cartesiano.
- **Tipagem**: A função `abs()` é capaz de lidar com diferentes tipos de entrada (inteiros, floats, complexos), o que a torna bastante versátil.

### Armadilhas Comuns
- **Entradas Inválidas**: Se um tipo de dado não suportado for passado para a função `abs()`, como uma string ou uma lista, isso resultará em um erro de tipo (TypeError).
- **Uso com Números Complexos**: É importante lembrar que o retorno para números complexos é um float, representando a magnitude e não o número em si.

## Resumo em Uma Linha
A função `abs()` em Python retorna o valor absoluto de um número, eliminando qualquer sinal negativo.