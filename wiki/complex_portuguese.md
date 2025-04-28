<!--
Meta Description: # Números Complexos em Python: Entenda o Tipo `complex` ## Sinopse O tipo `complex` em Python permite a representação de números complexos, que são fo...
Meta Keywords: python, parte, números, complexos, complex
-->

# Números Complexos em Python: Entenda o Tipo `complex`

## Sinopse
O tipo `complex` em Python permite a representação de números complexos, que são formados por uma parte real e uma parte imaginária. Este tipo é fundamental para cálculos matemáticos avançados e aplicações em engenharia e ciência.

## Documentação
O tipo `complex` em Python é utilizado para criar números complexos, que têm a forma `a + bj`, onde `a` é a parte real e `b` é a parte imaginária. O `j` é o símbolo que representa a unidade imaginária. O Python oferece suporte nativo para operações com números complexos, incluindo adição, subtração, multiplicação e divisão.

### Uso
Para criar um número complexo em Python, você pode usar a função `complex()` ou simplesmente definir o número usando a notação `a + bj`. Aqui estão algumas maneiras de declarar números complexos:

```python
# Usando a função complex()
num1 = complex(2, 3)  # 2 + 3j

# Usando a notação direta
num2 = 4 + 5j  # 4 + 5j
```

### Métodos e Atributos
Os números complexos em Python possuem dois atributos principais:
- `.real`: Retorna a parte real do número complexo.
- `.imag`: Retorna a parte imaginária do número complexo.

Exemplo:
```python
num = 3 + 4j
print(num.real)  # Saída: 3.0
print(num.imag)  # Saída: 4.0
```

## Exemplos
### Exemplo 1: Operações Básicas
```python
a = 1 + 2j
b = 3 + 4j

# Adição
soma = a + b
print(soma)  # Saída: (4+6j)

# Multiplicação
produto = a * b
print(produto)  # Saída: (-5+10j)
```

### Exemplo 2: Trabalhando com Atributos
```python
num = 5 + 7j
print("Parte Real:", num.real)  # Saída: Parte Real: 5.0
print("Parte Imaginária:", num.imag)  # Saída: Parte Imaginária: 7.0
```

## Explicação
Embora o tipo `complex` seja poderoso, alguns pontos devem ser observados:
- **Conversão**: Ao converter um número complexo para um tipo inteiro ou float, você pode perder a parte imaginária, pois esses tipos não suportam essa funcionalidade.
- **Operações**: Algumas operações podem resultar em erros se não forem realizadas corretamente. Por exemplo, a divisão de um número complexo por zero causará uma exceção `ZeroDivisionError`.
- **Impressão**: A forma como os números complexos são impressos pode não ser intuitiva para todos os usuários. O Python usará sempre o formato `a + bj`.

## Resumo em Uma Linha
O tipo `complex` em Python permite a criação e manipulação de números complexos, facilitando cálculos matemáticos avançados.