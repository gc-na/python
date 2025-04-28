<!--
Meta Description: # exec: Executando Código Python Dinamicamente ## Sinopse O comando `exec` em Python permite a execução de código Python que é passado como uma string...
Meta Keywords: exec, python, código, que, execução
-->

# exec: Executando Código Python Dinamicamente

## Sinopse
O comando `exec` em Python permite a execução de código Python que é passado como uma string. Isso é útil para a execução dinâmica de scripts, onde o código pode ser gerado ou modificado em tempo de execução.

## Documentação
O `exec` é uma função embutida em Python que aceita uma string representando um código Python e o executa no contexto do ambiente atual, podendo modificar variáveis locais e globais.

### Sintaxe
```python
exec(object[, globals[, locals]])
```

#### Parâmetros
- **object**: Uma string ou objeto de código a ser executado.
- **globals** (opcional): Um dicionário que define o espaço de nomes globais.
- **locals** (opcional): Um dicionário que define o espaço de nomes locais. Se não for fornecido, o dicionário `globals` é usado como `locals`.

### Propósito
O `exec` é utilizado para executar código Python que é gerado dinamicamente em tempo de execução, permitindo maior flexibilidade em aplicações que requerem execução de scripts ou avaliação de expressões.

## Exemplos

### Exemplo Básico
```python
codigo = "print('Olá, Mundo!')"
exec(codigo)
```
Saída:
```
Olá, Mundo!
```

### Uso com Variáveis
```python
variavel = 10
codigo = "variavel += 5"
exec(codigo)
print(variavel)  # Saída: 15
```

### Definindo Funções Dinamicamente
```python
exec("def funcao(): return 'Função executada'")
print(funcao())  # Saída: Função executada
```

## Explicação
Embora o `exec` seja uma ferramenta poderosa, deve ser usado com cautela. Aqui estão alguns pontos importantes:

- **Segurança**: Executar código arbitrário pode levar a vulnerabilidades de segurança, especialmente se o código a ser executado provém de fontes não confiáveis.
- **Desempenho**: O uso de `exec` pode impactar negativamente o desempenho, pois a execução de código dinâmico é mais lenta do que a execução de código estático.
- **Escopo**: O `exec` modifica o escopo das variáveis locais e globais, o que pode levar a comportamentos inesperados se não for bem compreendido.

## Resumo em Uma Linha
O `exec` em Python é uma função que permite a execução de código Python dinâmico a partir de uma string, oferecendo flexibilidade, mas requerendo cautela em seu uso.