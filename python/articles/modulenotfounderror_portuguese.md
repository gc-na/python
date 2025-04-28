<!--
Meta Description: # ModuleNotFoundError: Entendendo o Erro de Módulo Não Encontrado no Python ## Sinopse O `ModuleNotFoundError` é uma exceção lançada pelo interpretado...
Meta Keywords: módulo, não, python, modulenotfounderror, que
-->

# ModuleNotFoundError: Entendendo o Erro de Módulo Não Encontrado no Python

## Sinopse
O `ModuleNotFoundError` é uma exceção lançada pelo interpretador Python quando um módulo que está sendo importado não pode ser encontrado. Este erro é comum entre desenvolvedores, especialmente aqueles que estão começando com a linguagem.

## Documentação
O `ModuleNotFoundError` faz parte da hierarquia de exceções do Python e é uma subclasse da exceção `ImportError`. Essa exceção é levantada quando o Python não consegue localizar um módulo especificado no comando de importação.

### Propósito
O propósito do `ModuleNotFoundError` é informar ao desenvolvedor que o módulo que está tentando ser importado não está disponível no ambiente atual, seja porque o módulo não está instalado, não está acessível no caminho de módulo ou o nome do módulo foi digitado incorretamente.

### Uso
Para gerar um `ModuleNotFoundError`, basta tentar importar um módulo que não existe ou não está acessível. O Python irá interromper a execução do programa e exibir uma mensagem de erro informando que o módulo não foi encontrado.

### Detalhes
- O erro pode ocorrer em qualquer versão do Python que suporte o comando de importação.
- É importante verificar se o nome do módulo foi escrito corretamente e se o módulo está instalado no ambiente Python em uso.

## Exemplos
### Exemplo 1: Módulo não instalado
```python
import modulo_inexistente
```
**Saída:**
```
ModuleNotFoundError: No module named 'modulo_inexistente'
```

### Exemplo 2: Nome do módulo escrito incorretamente
```python
import numpyy  # Erro de digitação no nome do módulo
```
**Saída:**
```
ModuleNotFoundError: No module named 'numpyy'
```

### Exemplo 3: Módulo não acessível
```python
import my_custom_module  # Supondo que o módulo não esteja no PYTHONPATH
```
**Saída:**
```
ModuleNotFoundError: No module named 'my_custom_module'
```

## Explicação
### Armadilhas Comuns
1. **Erro de Digitação**: Um dos erros mais comuns é digitar incorretamente o nome do módulo. Verifique sempre a grafia.
2. **Ambiente Virtual**: Se você estiver usando ambientes virtuais, certifique-se de que o módulo está instalado no ambiente correto.
3. **Caminho do Módulo**: O Python procura módulos em diretórios especificados na variável `sys.path`. Se o módulo não estiver em um dos diretórios listados, o erro ocorrerá.
4. **Instalação de Pacotes**: Se um módulo não estiver instalado, você pode instalá-lo usando o gerenciador de pacotes `pip`. Por exemplo:
   ```
   pip install nome_do_pacote
   ```

## Resumo em Uma Linha
`ModuleNotFoundError` é uma exceção levantada em Python quando um módulo não pode ser encontrado durante a importação.