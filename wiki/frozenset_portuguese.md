<!--
Meta Description: # frozenset: Entenda a Estrutura de Dados Imutável do Python ## Sinopse O `frozenset` é uma estrutura de dados embutida no Python que representa um co...
Meta Keywords: frozenset, que, como, python, não
-->

# frozenset: Entenda a Estrutura de Dados Imutável do Python

## Sinopse
O `frozenset` é uma estrutura de dados embutida no Python que representa um conjunto imutável. Ele permite armazenar elementos únicos e não ordenados, garantindo que os dados não possam ser alterados após sua criação.

## Documentação
O `frozenset` é uma variante do `set` que não permite a modificação de seus elementos. Isso significa que, após sua criação, você não pode adicionar, remover ou alterar os itens do `frozenset`. Essa característica torna o `frozenset` útil em situações onde é necessário garantir a imutabilidade dos dados, como em chaves de dicionário ou em outras operações que requerem conjuntos imutáveis.

### Uso
A sintaxe básica para criar um `frozenset` é a seguinte:

```python
frozenset(iterable)
```

- **iterable**: Um objeto que pode ser iterado, como uma lista, tupla ou string.

### Características
1. **Imutabilidade**: Após a criação, não é possível modificar o `frozenset`.
2. **Elementos Únicos**: Assim como os conjuntos, os `frozensets` não podem conter elementos duplicados.
3. **Suporte a Operações de Conjunto**: O `frozenset` suporta operações como união, interseção e diferença.

## Exemplos

### Exemplo 1: Criando um frozenset
```python
# Criando um frozenset a partir de uma lista
meu_frozenset = frozenset([1, 2, 3, 4, 5])
print(meu_frozenset)  # Saída: frozenset({1, 2, 3, 4, 5})
```

### Exemplo 2: Tentativa de modificação
```python
# Criando um frozenset
meu_frozenset = frozenset([1, 2, 3])

# Tentativa de adicionar um elemento (causará um erro)
try:
    meu_frozenset.add(4)
except AttributeError as e:
    print(e)  # Saída: 'frozenset' object has no attribute 'add'
```

### Exemplo 3: Operações de conjunto
```python
frozenset_a = frozenset([1, 2, 3])
frozenset_b = frozenset([3, 4, 5])

# União
uniao = frozenset_a | frozenset_b
print(uniao)  # Saída: frozenset({1, 2, 3, 4, 5})

# Interseção
interseccao = frozenset_a & frozenset_b
print(interseccao)  # Saída: frozenset({3})

# Diferença
diferenca = frozenset_a - frozenset_b
print(diferenca)  # Saída: frozenset({1, 2})
```

## Explicação
Um dos principais pontos a se considerar ao trabalhar com `frozensets` é a imutabilidade. Isso pode ser confuso para iniciantes que estão acostumados a modificar conjuntos. Além disso, como `frozensets` são imutáveis, eles podem ser usados como chaves em dicionários, ao contrário dos conjuntos mutáveis. É importante lembrar que os elementos dentro de um `frozenset` devem ser hashable, ou seja, devem ser de tipos que podem ser usados como chaves, como números, strings ou tuplas.

## Resumo em Uma Linha
O `frozenset` é uma estrutura de dados imutável em Python que armazena elementos únicos e não ordenados, ideal para garantir a integridade dos dados.