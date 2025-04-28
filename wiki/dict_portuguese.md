<!--
Meta Description: # Dicionário em Python: Compreendendo a Estrutura de Dados "dict" ## Sinopse O `dict` em Python é uma estrutura de dados que armazena pares de chave-v...
Meta Keywords: python, chave, dict, valor, dicionário
-->

# Dicionário em Python: Compreendendo a Estrutura de Dados "dict"

## Sinopse
O `dict` em Python é uma estrutura de dados que armazena pares de chave-valor, permitindo acesso rápido e eficiente aos dados. É amplamente utilizado para manipulação e organização de dados em aplicações Python.

## Documentação
O `dict`, ou dicionário, é uma das estruturas de dados embutidas mais importantes do Python. Ele permite armazenar dados em um formato de chave-valor, onde cada chave única é associada a um valor. A principal vantagem do `dict` é a sua capacidade de permitir buscas e inserções rápidas, com complexidade média de O(1).

### Propósito
O `dict` é utilizado para representar coleções de dados não ordenadas, onde a busca por uma chave específica é mais eficiente do que em listas ou tuplas.

### Uso
Para criar um dicionário em Python, você pode usar chaves `{}` ou a função `dict()`. 

#### Sintaxe:
```python
# Criação de um dicionário vazio
meu_dicionario = {}

# Criação de um dicionário com pares chave-valor
meu_dicionario = {'nome': 'João', 'idade': 30}
```

### Detalhes
- As chaves em um dicionário devem ser de um tipo imutável (como strings, números ou tuplas).
- Os valores podem ser de qualquer tipo, incluindo listas, outros dicionários ou até mesmo funções.
- A ordem dos itens em um dicionário é garantida a partir do Python 3.7, o que significa que os itens são retornados na ordem em que foram inseridos.

## Exemplos
Aqui estão alguns exemplos de uso do `dict` em Python:

### Exemplo 1: Criação e Acesso
```python
# Criação de um dicionário
estudante = {'nome': 'Maria', 'idade': 25, 'curso': 'Engenharia'}

# Acesso aos valores
print(estudante['nome'])  # Saída: Maria
```

### Exemplo 2: Adição e Remoção de Elementos
```python
# Adicionando um novo par chave-valor
estudante['ano'] = 2023

# Removendo um par chave-valor
del estudante['idade']

print(estudante)  # Saída: {'nome': 'Maria', 'curso': 'Engenharia', 'ano': 2023}
```

### Exemplo 3: Iteração
```python
# Iterando sobre um dicionário
for chave, valor in estudante.items():
    print(f'{chave}: {valor}')
```

## Explicação
Embora o `dict` seja uma ferramenta poderosa, existem algumas pegadinhas a serem observadas:

- **Chaves Duplicadas**: Se você tentar adicionar uma chave que já existe, o valor antigo será substituído pelo novo.
- **Tipos de Chaves**: Apenas tipos imutáveis podem ser usados como chaves. Usar listas ou outros dicionários resultará em um erro.
- **Performance**: O desempenho do `dict` é geralmente muito bom, mas em casos de dicionários muito grandes, é importante avaliar o impacto na memória e na velocidade.

## Resumo em Uma Linha
O `dict` em Python é uma estrutura de dados eficiente para armazenar e acessar pares de chave-valor, facilitando a manipulação de dados.