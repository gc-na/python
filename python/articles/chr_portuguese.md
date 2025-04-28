<!--
Meta Description: # Função chr em Python: Entenda como Converter Códigos ASCII em Caracteres ## Sinopse A função `chr` em Python é utilizada para retornar o caractere c...
Meta Keywords: chr, função, que, código, unicode
-->

# Função chr em Python: Entenda como Converter Códigos ASCII em Caracteres

## Sinopse
A função `chr` em Python é utilizada para retornar o caractere correspondente a um valor inteiro que representa um código Unicode. É uma ferramenta essencial para manipulação de texto e conversão de valores numéricos em caracteres legíveis.

## Documentação
A função `chr` faz parte da biblioteca padrão do Python e é definida como:

```python
chr(i)
```

### Propósito
O principal objetivo da função `chr` é fornecer uma maneira de converter um valor inteiro, que deve estar dentro do intervalo de 0 a 1.114.111 (ou seja, 0x10FFFF em hexadecimal), em seu caractere Unicode correspondente. Essa função é particularmente útil em manipulação de strings, processamento de dados textuais e desenvolvimento de aplicações que exigem conversões de códigos.

### Uso
- **Parâmetro**: 
  - `i`: Um inteiro que representa um código Unicode.
  
- **Retorno**: 
  - Retorna uma string com um único caractere que corresponde ao código Unicode fornecido.

### Exceções
Caso o valor fornecido para `i` não esteja dentro do intervalo permitido, a função levantará um `ValueError`.

## Exemplos
Aqui estão alguns exemplos básicos do uso da função `chr`:

```python
# Exemplo 1: Convertendo o código ASCII para caractere
caractere_a = chr(97)  # Resultado: 'a'
print(caractere_a)

# Exemplo 2: Convertendo um código Unicode
caractere_Unicode = chr(9731)  # Resultado: '☃' (símbolo de boneco de neve)
print(caractere_Unicode)

# Exemplo 3: Usando um código fora do intervalo permitido
try:
    caractere_invalido = chr(1114112)  # Levantará ValueError
except ValueError as e:
    print(e)  # Saída: chr() arg not in range(0x110000)
```

## Explicação
### Armadilhas Comuns
- **Intervalo de Valores**: Um erro comum é tentar usar um valor fora do intervalo de 0 a 1.114.111. Sempre verifique se o valor fornecido está dentro desse intervalo.
- **Tipo do Parâmetro**: O argumento passado para `chr` deve ser do tipo inteiro. Passar um tipo diferente, como uma string ou float, resultará em um `TypeError`.

### Notas Adicionais
- A função `chr` é frequentemente usada em conjunto com a função `ord`, que retorna o código Unicode de um caractere. Essa relação pode ser explorada para conversões bidirecionais entre caracteres e seus códigos.
- A função `chr` pode ser útil em aplicações que precisam gerar caracteres dinamicamente, como na geração de senhas ou na manipulação de textos criptografados.

## Resumo em Uma Linha
A função `chr` em Python converte um valor inteiro que representa um código Unicode em seu caractere correspondente, facilitando a manipulação de strings e textos.