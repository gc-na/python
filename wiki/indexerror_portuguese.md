<!--
Meta Description: # IndexError em Python: Compreendendo e Lidando com Erros de Índice ## Sinopse O `IndexError` em Python ocorre quando um código tenta acessar um índic...
Meta Keywords: índice, indexerror, que, python, uma
-->

# IndexError em Python: Compreendendo e Lidando com Erros de Índice

## Sinopse
O `IndexError` em Python ocorre quando um código tenta acessar um índice que está fora do intervalo de uma sequência, como listas ou strings. Esse erro é fundamental para entender a manipulação de estruturas de dados em Python.

## Documentação
O `IndexError` é uma exceção interna do Python que é levantada quando se tenta acessar um item de uma lista, tupla ou string utilizando um índice que não existe. O Python conta os índices começando do zero, o que significa que o primeiro elemento de uma sequência está no índice 0, o segundo no índice 1, e assim por diante. Quando um índice negativo é utilizado, ele conta a partir do final da sequência, com -1 referindo-se ao último elemento.

### Propósito
O propósito do `IndexError` é indicar que uma operação de indexação falhou devido a um índice inválido, ajudando os desenvolvedores a identificar e corrigir erros no código.

### Uso
Quando um `IndexError` é levantado, a execução do programa é interrompida, a menos que o erro seja tratado por meio de um bloco `try/except`. É importante entender como evitar esse erro e como lidar com ele quando ocorrer.

## Exemplos
Aqui estão alguns exemplos básicos que demonstram como o `IndexError` pode ocorrer:

### Exemplo 1: Acesso a um índice fora do intervalo
```python
lista = [1, 2, 3]
print(lista[3])  # Levanta IndexError: list index out of range
```

### Exemplo 2: Uso de índices negativos
```python
string = "Python"
print(string[-7])  # Levanta IndexError: string index out of range
```

### Exemplo 3: Tratando o erro com try/except
```python
lista = [1, 2, 3]

try:
    print(lista[5])
except IndexError:
    print("Índice fora do intervalo!")
```

## Explicação
Um `IndexError` pode ocorrer por várias razões, incluindo:

- **Tentativa de acessar um índice que não existe**: Isso é comum em listas e strings. Por exemplo, se você tem uma lista com 3 elementos, tentar acessar o índice 3 resultará em um erro, pois os índices válidos são 0, 1 e 2.
  
- **Uso incorreto de índices negativos**: Embora índices negativos sejam válidos, se o valor absoluto de um índice negativo exceder o comprimento da sequência, um `IndexError` será levantado.

### Dicas para Evitar o IndexError
- Sempre verifique o tamanho da sequência usando a função `len()` antes de acessar um índice.
- Utilize estruturas de controle, como `if` ou `try/except`, para garantir que o índice seja válido antes da operação.

## Resumo em uma Linha
O `IndexError` em Python é uma exceção que ocorre quando se tenta acessar um índice fora do intervalo de uma sequência, como listas ou strings.