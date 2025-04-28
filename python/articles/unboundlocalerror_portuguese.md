<!--
Meta Description: # UnboundLocalError em Python: Compreendendo o Erro de Variável Local Não Inicializada ## Sinopse O `UnboundLocalError` é um erro em Python que ocorre...
Meta Keywords: uma, variável, que, unboundlocalerror, antes
-->

# UnboundLocalError em Python: Compreendendo o Erro de Variável Local Não Inicializada

## Sinopse
O `UnboundLocalError` é um erro em Python que ocorre quando uma variável local é referenciada antes de ser atribuída um valor. Esse erro é comum em situações onde a lógica do código tenta acessar uma variável que ainda não foi inicializada dentro do escopo da função.

## Documentação
O `UnboundLocalError` é uma subclasse de `NameError`, e é levantado quando o interpretador Python encontra uma referência a uma variável local que não foi definida. Isso geralmente acontece em funções, onde a variável é declarada dentro de um escopo, mas é referenciada antes de receber um valor.

### Propósito
O propósito do `UnboundLocalError` é garantir que as variáveis sejam inicializadas antes de serem usadas, prevenindo comportamentos inesperados e falhas no programa.

### Uso
Para evitar o `UnboundLocalError`, certifique-se de que todas as variáveis locais sejam definidas antes de serem referenciadas. Caso uma variável global precise ser usada dentro de uma função, use a declaração `global` para indicar que você deseja acessar a variável global e não criar uma nova variável local.

### Detalhes
- O erro é específico para variáveis que são consideradas locais na função onde estão sendo referenciadas.
- Se uma variável é atribuída dentro de uma função, Python a considera local, mesmo que tenha sido definida globalmente.
- O `UnboundLocalError` pode ser resolvido através da inicialização da variável antes de seu uso ou pelo uso adequado da palavra-chave `global`.

## Exemplos

### Exemplo 1: Gerando um UnboundLocalError

```python
def exemplo_funcao():
    print(x)  # Tentativa de acessar 'x' antes de inicializá-la
    x = 10

exemplo_funcao()  # Isso levantará UnboundLocalError
```

### Exemplo 2: Corrigindo o Erro

```python
x = 10

def exemplo_funcao():
    global x  # Declarando que queremos usar a variável global
    print(x)  # Agora isso funciona corretamente
    x = 20

exemplo_funcao()  # Saída: 10
print(x)  # Saída: 20
```

### Exemplo 3: Inicializando a Variável

```python
def exemplo_funcao():
    x = 10  # Inicializando 'x' antes de usá-la
    print(x)

exemplo_funcao()  # Saída: 10
```

## Explicação
Um dos erros mais comuns que levam ao `UnboundLocalError` é a tentativa de modificar uma variável que foi definida fora do escopo da função sem usar a palavra-chave `global`. Quando o Python encontra uma atribuição a uma variável dentro de uma função, ele considera que a variável é local a essa função. Portanto, qualquer referência a essa variável antes de sua inicialização resultará em um `UnboundLocalError`.

**Dicas para evitar o erro:**
- Sempre inicialize suas variáveis antes de usá-las.
- Se você precisar modificar uma variável global dentro de uma função, utilize a palavra-chave `global`.
- Verifique se as variáveis precisam ser locais ou globais, e declare-as adequadamente.

## Resumo em Uma Linha
O `UnboundLocalError` é um erro em Python que ocorre quando uma variável local é referenciada antes de ser inicializada dentro de uma função.