<!--
Meta Description: # classmethod: Entendendo o Decorador de Método de Classe em Python ## Sinopse O `classmethod` é um decorador em Python que permite que um método seja...
Meta Keywords: classe, classmethod, método, que, cls
-->

# classmethod: Entendendo o Decorador de Método de Classe em Python

## Sinopse
O `classmethod` é um decorador em Python que permite que um método seja chamado na classe em vez de em uma instância específica. Isso é útil para definir métodos que operam sobre a classe como um todo e não sobre instâncias individuais.

## Documentação
O `classmethod` transforma um método normal em um método de classe, que recebe a própria classe como primeiro argumento em vez de uma instância. Isso é feito através do uso do decorador `@classmethod` antes da definição do método.

### Propósito
O principal objetivo do `classmethod` é permitir que métodos que precisam acessar a classe, e não apenas uma instância, sejam definidos de forma clara e concisa. Isso é especialmente útil em casos de herança e quando se deseja modificar o comportamento de uma classe sem instanciar objetos.

### Uso
Para usar o `classmethod`, siga a sintaxe abaixo:

```python
class NomeDaClasse:
    @classmethod
    def nome_do_metodo(cls, argumentos):
        # implementação do método
```

Aqui, `cls` é a referência à classe e não à instância. Você pode acessar atributos e métodos da classe usando `cls`.

## Exemplos

### Exemplo 1: Método de Classe Simples
```python
class Exemplo:
    contador = 0

    @classmethod
    def incrementar_contador(cls):
        cls.contador += 1
        return cls.contador

print(Exemplo.incrementar_contador())  # Saída: 1
print(Exemplo.incrementar_contador())  # Saída: 2
```

### Exemplo 2: Usando com Herança
```python
class Base:
    @classmethod
    def metodo_classe(cls):
        return f'Método da classe: {cls.__name__}'

class Derivada(Base):
    pass

print(Derivada.metodo_classe())  # Saída: Método da classe: Derivada
```

## Explicação
Um erro comum ao usar `classmethod` é esquecer de usar o decorador `@classmethod`, o que resultará em um TypeError, pois o primeiro argumento padrão de um método é a instância (`self`). Outro ponto importante é que os métodos de classe podem ser chamados tanto pela classe quanto por instâncias da classe, mas o primeiro argumento sempre será a classe, não a instância.

Além disso, o `classmethod` pode ser especialmente útil em padrões de projeto como o Singleton, onde o controle de instâncias é necessário.

## Resumo em Uma Linha
O `classmethod` é um decorador que permite a definição de métodos que operam na classe em vez de em instâncias, facilitando o acesso e a manipulação de atributos da classe.