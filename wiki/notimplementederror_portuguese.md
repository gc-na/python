<!--
Meta Description: # NotImplementedError em Python: Entenda e Aprenda a Utilizá-lo ## Sinopse O `NotImplementedError` é uma exceção em Python que indica que um método ou...
Meta Keywords: que, notimplementederror, self, uma, método
-->

# NotImplementedError em Python: Entenda e Aprenda a Utilizá-lo

## Sinopse
O `NotImplementedError` é uma exceção em Python que indica que um método ou operação não foi implementado. É frequentemente utilizado em classes base para sinalizar que uma função deve ser implementada em subclasses.

## Documentação
O `NotImplementedError` é uma subclasse da exceção `RuntimeError`. Ele é utilizado para indicar que um recurso, método ou função que foi declarado ainda não possui uma implementação. Essa exceção é particularmente útil em cenários de programação orientada a objetos, onde você pode definir métodos em uma classe base que devem ser implementados pelas subclasses.

### Propósito
O principal propósito do `NotImplementedError` é servir como um aviso para os desenvolvedores de que uma funcionalidade ainda não foi concluída. Isso é especialmente benéfico em projetos em desenvolvimento, onde a estrutura já está montada, mas a implementação de certas funções ainda está pendente.

### Uso
Para usar o `NotImplementedError`, você simplesmente levanta a exceção dentro de um método que não foi implementado. Veja o exemplo abaixo:

```python
class MinhaClasseBase:
    def meu_metodo(self):
        raise NotImplementedError("Este método deve ser implementado em uma subclasse.")
```

## Exemplos
Aqui estão alguns exemplos práticos de como utilizar o `NotImplementedError`:

### Exemplo 1: Classe Base
```python
class Forma:
    def area(self):
        raise NotImplementedError("Método 'area' deve ser implementado por subclasses.")

class Retangulo(Forma):
    def __init__(self, largura, altura):
        self.largura = largura
        self.altura = altura

    def area(self):
        return self.largura * self.altura

# Uso
retangulo = Retangulo(5, 10)
print(retangulo.area())  # Saída: 50
```

### Exemplo 2: Implementação em Subclasse
```python
class Animal:
    def som(self):
        raise NotImplementedError("Método 'som' deve ser implementado por subclasses.")

class Cachorro(Animal):
    def som(self):
        return "Au Au"

# Uso
cachorro = Cachorro()
print(cachorro.som())  # Saída: Au Au
```

## Explicação
Um dos principais cuidados ao utilizar `NotImplementedError` é garantir que ele seja levantado apenas em métodos que você realmente espera que sejam implementados em subclasses. Se a exceção for levantada em um contexto onde o método deveria estar implementado e não estiver, o código falhará em tempo de execução.

Outra armadilha comum é esquecer de documentar o que cada método que levanta `NotImplementedError` deve realizar. É essencial fornecer uma mensagem clara para que outros desenvolvedores saibam o que esperar.

## Resumo em Uma Linha
O `NotImplementedError` em Python sinaliza que um método não foi implementado, servindo como um guia para a implementação em subclasses.