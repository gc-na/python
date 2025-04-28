<!--
Meta Description: # Exceções em Python: Entendendo e Manipulando Erros ## Sinopse As exceções em Python são eventos que ocorrem durante a execução de um programa e que ...
Meta Keywords: exceções, que, uma, python, exceção
-->

# Exceções em Python: Entendendo e Manipulando Erros

## Sinopse
As exceções em Python são eventos que ocorrem durante a execução de um programa e que interrompem o fluxo normal de instruções. Elas permitem que os programadores tratem erros de forma controlada, garantindo que o programa possa continuar rodando ou falhar graciosamente.

## Documentação
Em Python, uma exceção é um objeto que representa um erro ou condição anômala que ocorre durante a execução de um programa. Quando uma exceção é lançada, o fluxo normal do programa é interrompido e o Python começa a procurar um manipulador de exceções que possa tratar esse erro.

### Propósito
O principal propósito das exceções é permitir que os desenvolvedores capturem e tratem erros, evitando que o programa quebre de maneira abrupta. Isso é crucial em aplicações robustas, onde a experiência do usuário deve ser mantida mesmo em situações de erro.

### Uso
As exceções são manipuladas usando os blocos `try`, `except`, `else` e `finally`. Um bloco `try` contém o código que pode gerar uma exceção, e o bloco `except` contém o código que será executado se uma exceção ocorrer.

### Estrutura Básica
```python
try:
    # Código que pode gerar uma exceção
    resultado = 10 / 0
except ZeroDivisionError:
    # Código para lidar com a exceção
    print("Divisão por zero não é permitida.")
else:
    # Código que será executado se não ocorrer exceção
    print(f"O resultado é {resultado}.")
finally:
    # Código que sempre será executado
    print("Execução finalizada.")
```

## Exemplos

### Exemplo 1: Capturando uma Exceção Comum
```python
try:
    numero = int(input("Digite um número: "))
    print(f"O número digitado é {numero}.")
except ValueError:
    print("Isso não é um número válido.")
```

### Exemplo 2: Usando o Bloco `finally`
```python
try:
    arquivo = open('arquivo.txt', 'r')
    conteudo = arquivo.read()
except FileNotFoundError:
    print("Arquivo não encontrado.")
finally:
    if 'arquivo' in locals():
        arquivo.close()
        print("Arquivo fechado.")
```

### Exemplo 3: Capturando Múltiplas Exceções
```python
try:
    resultado = 10 / int(input("Digite um divisor: "))
except (ZeroDivisionError, ValueError) as e:
    print(f"Ocorreu um erro: {e}")
```

## Explicação
Ao trabalhar com exceções, é importante estar atento a alguns pontos:

- **Hierarquia de Exceções**: Python possui uma hierarquia de exceções. Você pode capturar exceções específicas ou uma exceção genérica, como `Exception`, mas é mais recomendado capturar exceções específicas sempre que possível.
  
- **Tratamento de Exceções Não Esperadas**: Se uma exceção não for capturada, o programa terminará abruptamente. É uma boa prática usar um bloco `except` genérico para capturar exceções inesperadas e registrar erros.

- **Uso Excessivo de Exceções**: Evite usar exceções para o controle de fluxo normal do programa, pois isso pode levar a códigos difíceis de entender e manter.

## Resumo em Uma Linha
As exceções em Python são mecanismos que permitem o tratamento controlado de erros durante a execução de programas, garantindo robustez e melhor experiência do usuário.