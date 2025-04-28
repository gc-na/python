<!--
Meta Description: # NotImplemented em Python: Entenda seu Uso e Aplicações ## Sinopse O `NotImplemented` é um objeto especial em Python que indica que uma operação ou m...
Meta Keywords: que, notimplemented, self, python, uma
-->

# NotImplemented em Python: Entenda seu Uso e Aplicações

## Sinopse
O `NotImplemented` é um objeto especial em Python que indica que uma operação ou método não foi implementado. É frequentemente utilizado em classes para sinalizar que uma funcionalidade deve ser definida em subclasses.

## Documentação
O `NotImplemented` é uma constante embutida em Python, que é do tipo `NotImplementedType`. Seu uso é essencial em métodos que esperam que subclasses implementem uma funcionalidade específica. Quando um método que retorna `NotImplemented` é chamado, ele informa ao Python que a operação não está disponível, permitindo que o interpretador trate a situação de maneira adequada.

### Propósito
O principal propósito do `NotImplemented` é auxiliar na implementação de métodos que são esperados para serem sobrescritos por subclasses, especialmente em operações binárias, como adição e subtração.

### Uso
Ao definir um método em uma classe base, você pode retornar `NotImplemented` para indicar que a operação não é suportada na classe base, mas pode ser implementada nas subclasses. Isso é especialmente útil em contextos de operações matemáticas ou comparações.

## Exemplos
### Exemplo 1: Uso Básico em Classes
```python
class Forma:
    def area(self):
        return NotImplemented

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

### Exemplo 2: Operações Binárias
```python
class Numero:
    def __init__(self, valor):
        self.valor = valor
    
    def __add__(self, outro):
        if isinstance(outro, Numero):
            return Numero(self.valor + outro.valor)
        return NotImplemented

# Uso
num1 = Numero(10)
num2 = Numero(20)
resultado = num1 + num2
print(resultado.valor)  # Saída: 30
```

## Explicação
Um dos erros comuns ao usar `NotImplemented` é esquecer de tratá-lo em operações que esperam um resultado concreto. Se uma operação binária retorna `NotImplemented`, o Python tentará usar a operação inversa (por exemplo, `__radd__` se `__add__` retornar `NotImplemented`). Isso pode levar a comportamentos inesperados se não for tratado corretamente.

Além disso, `NotImplemented` não deve ser confundido com `None`. Retornar `None` pode dar a impressão de que a operação foi realizada com sucesso, enquanto `NotImplemented` deixa claro que a operação não está disponível.

## Resumo em Uma Linha
`NotImplemented` é um objeto especial em Python que indica que uma operação ou método não foi implementado, facilitando a definição de interfaces em classes base.