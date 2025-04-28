<!--
Meta Description: # KeyboardInterrupt em Python: Como Lidar com Interrupções de Teclado ## Sinopse O `KeyboardInterrupt` é uma exceção em Python que é levantada quando ...
Meta Keywords: que, keyboardinterrupt, programa, para, python
-->

# KeyboardInterrupt em Python: Como Lidar com Interrupções de Teclado

## Sinopse
O `KeyboardInterrupt` é uma exceção em Python que é levantada quando o usuário interrompe a execução de um programa, geralmente pressionando `Ctrl+C` no terminal. Esta funcionalidade é essencial para permitir que os desenvolvedores criem aplicativos que possam ser interrompidos de maneira controlada.

## Documentação
O `KeyboardInterrupt` é uma exceção que faz parte do módulo `builtins` em Python. Quando um programa está em execução e o usuário deseja interrompê-lo, o Python levanta essa exceção para permitir que o programa trate a interrupção de forma adequada.

### Propósito
O propósito principal do `KeyboardInterrupt` é permitir que os desenvolvedores capturem e tratem interrupções do usuário, garantindo que o programa possa finalizar suas operações de forma ordenada.

### Uso
Para utilizar o `KeyboardInterrupt`, você pode encapsular o código que pode ser interrompido dentro de um bloco `try` e capturar a exceção em um bloco `except`. Isso permite que você execute um código específico quando a interrupção ocorrer.

```python
try:
    while True:
        print("Executando... Pressione Ctrl+C para interromper.")
except KeyboardInterrupt:
    print("Execução interrompida pelo usuário.")
```

## Exemplos
### Exemplo Básico
O exemplo abaixo demonstra como lidar com a interrupção de um loop infinito:

```python
try:
    while True:
        print("Rodando... Pressione Ctrl+C para sair.")
except KeyboardInterrupt:
    print("Programa encerrado pelo usuário.")
```

### Exemplo com Limpeza
Este exemplo mostra como realizar tarefas de limpeza antes de encerrar o programa:

```python
def limpar_recursos():
    print("Liberando recursos antes de sair.")

try:
    while True:
        print("Executando... Pressione Ctrl+C para sair.")
except KeyboardInterrupt:
    limpar_recursos()
    print("Programa encerrado pelo usuário.")
```

## Explicação
### Armadilhas Comuns
1. **Não Capturar a Exceção**: Se você não capturar o `KeyboardInterrupt`, o programa será encerrado abruptamente, o que pode resultar em perda de dados ou recursos não liberados.
  
2. **Ambientes Interativos**: Em alguns ambientes interativos, como alguns IDEs ou notebooks Jupyter, a captura de `KeyboardInterrupt` pode não funcionar como esperado. É importante testar o comportamento em diferentes ambientes.

3. **Execução de Threads**: Se o seu programa utiliza múltiplas threads, o `KeyboardInterrupt` pode não se propagar para todas as threads, a menos que você implemente um mecanismo específico para gerenciar as interrupções em cada thread.

### Notas Adicionais
- O `KeyboardInterrupt` é uma maneira amigável de permitir que o usuário tenha controle sobre o fluxo de execução do programa, evitando encerramentos inesperados e potencialmente danosos.
- Sempre que possível, implemente tratamento de exceções para melhorar a experiência do usuário e a robustez do seu aplicativo.

## Resumo em Uma Linha
O `KeyboardInterrupt` em Python permite que desenvolvedores capturem interrupções de teclado, proporcionando um controle adequado sobre a finalização de programas.