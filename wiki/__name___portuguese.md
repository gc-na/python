<!--
Meta Description: # O Que é __name__ em Python: Entenda Seu Funcionamento e Importância ## Sinopse O `__name__` é uma variável especial em Python que desempenha um pape...
Meta Keywords: módulo, executado, __name__, diretamente, python
-->

# O Que é __name__ em Python: Entenda Seu Funcionamento e Importância

## Sinopse
O `__name__` é uma variável especial em Python que desempenha um papel fundamental na identificação do escopo de execução de um módulo. Ele ajuda a entender se um módulo está sendo executado diretamente ou importado em outro módulo.

## Documentação
### Propósito
A variável `__name__` é automaticamente definida pelo interpretador Python e é utilizada para determinar o contexto em que um módulo está sendo executado. Essa verificação é essencial para permitir que um módulo forneça funcionalidades tanto quando é executado diretamente quanto quando é importado por outros módulos.

### Uso
Quando um módulo é executado diretamente, `__name__` é atribuído o valor `"__main__"`. Se o módulo é importado em outro módulo, o valor de `__name__` será igual ao nome do módulo.

Essa característica é amplamente utilizada para incluir código que deve ser executado apenas quando o módulo é executado diretamente, como testes ou exemplos de uso.

### Detalhes
- **Execução Direta**: Ao rodar um arquivo Python diretamente (por exemplo, `python arquivo.py`), o interpretador define `__name__` como `"__main__"`.
- **Importação**: Quando um módulo é importado (por exemplo, `import arquivo`), `__name__` é definido como o nome do módulo (`arquivo`).

## Exemplos
### Exemplo 1: Execução Direta
```python
# arquivo.py
if __name__ == "__main__":
    print("Este módulo está sendo executado diretamente.")
```
**Saída:**
```
Este módulo está sendo executado diretamente.
```

### Exemplo 2: Importação de Módulo
```python
# arquivo.py
def funcao():
    print("Função do módulo.")

if __name__ == "__main__":
    print("Este módulo está sendo executado diretamente.")
```
```python
# main.py
import arquivo

arquivo.funcao()
```
**Saída do main.py:**
```
Função do módulo.
```

## Explicação
Um erro comum ao usar `__name__` é esquecer de incluir a verificação correta ao escrever módulos. Sem essa verificação, o código que deveria ser executado apenas quando o módulo é executado diretamente pode ser executado indesejadamente ao ser importado.

Outro ponto importante é a clareza na estrutura do código. Usar `__name__` ajuda a modularizar o código, facilitando a reutilização e mantendo a lógica de execução organizada.

## Resumo em Uma Linha
A variável especial `__name__` em Python permite identificar se um módulo está sendo executado diretamente ou importado, facilitando a execução condicional de código.