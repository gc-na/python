<!--
Meta Description: # NameError em Python: Compreendendo Erros de Nome em Programação ## Sinopse O `NameError` é uma exceção que ocorre em Python quando o interpretador t...
Meta Keywords: que, nameerror, variável, uma, não
-->

# NameError em Python: Compreendendo Erros de Nome em Programação

## Sinopse
O `NameError` é uma exceção que ocorre em Python quando o interpretador tenta acessar uma variável ou função que não foi definida. Este erro é comum entre iniciantes e pode ser facilmente evitado com boas práticas de codificação.

## Documentação
O `NameError` é levantado quando você tenta usar uma variável que não foi definida até o ponto em que está sendo referenciada. Isso pode ocorrer devido a erros de digitação, escopo de variáveis ou simplesmente por não ter atribuído um valor à variável antes de usá-la. É importante entender o contexto em que as variáveis são definidas e mantidas.

### Propósito
A principal função do `NameError` é alertar o desenvolvedor de que uma referência a uma variável ou função não pôde ser encontrada no escopo atual do código.

### Uso
Para evitar `NameErrors`, você deve sempre garantir que:
1. A variável ou função foi definida antes de ser utilizada.
2. O nome da variável ou função está escrito corretamente.
3. Você está acessando a variável dentro do escopo onde ela foi definida.

### Detalhes
- O `NameError` é um subtipo da classe de exceção `Exception`.
- A mensagem de erro geralmente inclui o nome da variável que não foi encontrada.
  
Exemplo de mensagem de erro:
```
NameError: name 'variavel_inexistente' is not defined
```

## Exemplos
### Exemplo 1: Variável não definida
```python
print(minha_variavel)  # Levanta NameError
```

### Exemplo 2: Erro de digitação
```python
numero = 10
print(numro)  # Levanta NameError devido a erro de digitação
```

### Exemplo 3: Escopo de variáveis
```python
def funcao():
    a = 5

funcao()
print(a)  # Levanta NameError, pois 'a' não está definido no escopo global
```

## Explicação
Um `NameError` é frequentemente encontrado por programadores que estão aprendendo Python, especialmente quando se trata de variáveis locais versus globais. É importante lembrar que variáveis definidas dentro de funções não são acessíveis fora delas, a menos que sejam declaradas como globais. 

Outros pontos a serem considerados:
- O uso de nomes muito semelhantes pode causar confusões e levar a erros.
- Sempre inicialize suas variáveis antes de usá-las para evitar `NameErrors`.

## Resumo em Uma Linha
O `NameError` em Python é uma exceção que indica que uma variável ou função foi referenciada antes de ser definida.