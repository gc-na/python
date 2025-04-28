<!--
Meta Description: # ExceptionGroup: Grupos de Exceções em Python ## Sinopse O `ExceptionGroup` é um novo recurso introduzido no Python 3.11 que permite agrupar múltipla...
Meta Keywords: exceptiongroup, exceções, python, que, uma
-->

# ExceptionGroup: Grupos de Exceções em Python

## Sinopse
O `ExceptionGroup` é um novo recurso introduzido no Python 3.11 que permite agrupar múltiplas exceções em uma única entidade, facilitando o tratamento de erros que podem ocorrer em operações paralelas ou concorrentes.

## Documentação
O `ExceptionGroup` é uma classe que herda de `BaseException` e é projetada para lidar com múltiplas exceções que podem ser levantadas simultaneamente em contextos assíncronos ou em threads. Isso é particularmente útil em situações onde várias tarefas podem falhar ao mesmo tempo, como ao usar bibliotecas de concorrência ou paralelismo.

### Propósito
O principal objetivo do `ExceptionGroup` é permitir que os desenvolvedores tratem múltiplas exceções de forma organizada e eficiente, evitando a necessidade de capturar e processar cada uma individualmente.

### Uso
Para criar um `ExceptionGroup`, você pode instanciar a classe passando uma lista de exceções. Ao capturar um `ExceptionGroup`, você pode iterar sobre suas exceções para tratá-las conforme necessário.

### Estrutura
```python
class ExceptionGroup(BaseException):
    def __init__(self, name, exceptions):
        self.name = name
        self.exceptions = exceptions
```

## Exemplos
### Exemplo Básico
```python
def funcao_com_erros():
    raise ExceptionGroup("Erros em tarefas", [ValueError("Erro de valor"), KeyError("Erro de chave")])

try:
    funcao_com_erros()
except ExceptionGroup as eg:
    print(f"Grupo de exceções: {eg.name}")
    for e in eg.exceptions:
        print(f" - {e}")
```

### Exemplo com Tarefas Assíncronas
```python
import asyncio

async def tarefa_1():
    raise ValueError("Erro na tarefa 1")

async def tarefa_2():
    raise KeyError("Erro na tarefa 2")

async def main():
    try:
        await asyncio.gather(tarefa_1(), tarefa_2())
    except ExceptionGroup as eg:
        print(f"Grupo de erros: {eg.name}")
        for e in eg.exceptions:
            print(f" - {e}")

asyncio.run(main())
```

## Explicação
Um dos principais desafios ao lidar com exceções em Python é que, em operações assíncronas ou multithread, várias exceções podem ser geradas simultaneamente. O `ExceptionGroup` ajuda a evitar a complexidade de capturar cada exceção individualmente. 

### Armadilhas Comuns
- **Captura de Exceções**: É importante lembrar que, ao capturar um `ExceptionGroup`, você deve iterar sobre as exceções para tratá-las adequadamente. Ignorar isso pode levar a erros não tratados.
- **Compatibilidade**: O `ExceptionGroup` está disponível apenas a partir do Python 3.11. Certifique-se de que seu ambiente esteja atualizado.

## Resumo em Uma Linha
O `ExceptionGroup` em Python permite o agrupamento e o tratamento eficiente de múltiplas exceções em operações concorrentes.