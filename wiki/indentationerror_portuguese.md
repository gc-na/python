<!--
Meta Description: # IndentationError em Python: Compreendendo e Resolvendo Erros de Indentação ## Sinopse O IndentationError é uma exceção em Python que ocorre quando o...
Meta Keywords: que, indentação, código, python, uma
-->

# IndentationError em Python: Compreendendo e Resolvendo Erros de Indentação

## Sinopse
O IndentationError é uma exceção em Python que ocorre quando o interpretador encontra um erro de indentação no código, o que impede a correta interpretação da estrutura de blocos de código.

## Documentação
O IndentationError é uma das exceções mais comuns que os programadores Python enfrentam, especialmente aqueles que estão começando a aprender a linguagem. A indentação é fundamental em Python, pois ela define a hierarquia e a estrutura de controle do fluxo de execução. Ao contrário de outras linguagens que utilizam chaves ou palavras-chave para definir blocos de código, o Python depende da indentação correta para identificar quais instruções pertencem a quais blocos.

### Propósito
O propósito do IndentationError é alertar o programador sobre inconsistências na indentação do código, que resultam em uma incapacidade do interpretador de entender a estrutura lógica do programa.

### Uso
Esse erro geralmente acontece nas seguintes situações:
- Quando linhas de código que deveriam estar no mesmo bloco têm níveis de indentação diferentes.
- Quando um bloco de código não está devidamente indentado após uma declaração que requer um bloco, como `if`, `for`, `while`, entre outros.

### Detalhes
O IndentationError é uma subclasse da classe `SyntaxError`, o que significa que ele é um erro de sintaxe. Isso implica que o código não pode ser executado até que o problema de indentação seja resolvido. Quando o interpretador encontra esse erro, ele geralmente fornece uma mensagem que indica a linha onde o problema ocorreu.

## Exemplos

### Exemplo 1: Indentação Correta
```python
def saudacao():
    print("Olá, Mundo!")

saudacao()
```

### Exemplo 2: Indentação Incorreta
```python
def saudacao():
print("Olá, Mundo!")  # Este código gerará um IndentationError

saudacao()
```

### Exemplo 3: Misturando Espaços e Tabulações
```python
def saudacao():
    print("Olá, Mundo!")  # Usando espaços
	print("Como você está?")  # Usando uma tabulação (gerará um IndentationError)

saudacao()
```

## Explicação
Um dos erros mais comuns que levam ao IndentationError é a mistura de espaços e tabulações. Python é sensível a esses caracteres, e a utilização inconsistente pode resultar em erros de indentação. Além disso, é importante garantir que todos os blocos de código estejam corretamente alinhados. 

Para evitar esses erros, recomenda-se:
- Utilizar apenas espaços ou apenas tabulações, nunca os dois.
- Configurar o editor de código para converter tabulações em espaços.
- Manter uma convenção de indentação consistente em todo o código (geralmente, 4 espaços por nível de indentação é uma prática comum em Python).

## Resumo em Uma Linha
O IndentationError em Python é um erro de sintaxe que ocorre quando há problemas na indentação do código, resultando na incapacidade do interpretador de entender a estrutura do programa.