# Desafio de código python

Resolução dos exercícios conforme as devidas solicitações, os códigos foram inclusos em funções para facilitar os testes para comparação com os exemplos.

# Desafio 1

### Entrada

Seu programa deve solicitar ao usuário a entrada de um número inteiro positivo, representando a quantidade de passos que o explorador deve dar na floresta.

### Saída

- O programa deve imprimir uma mensagem indicando o progresso do explorador na floresta. Utilize um laço de repetição para simular os passos do explorador. 

- A cada passo, imprima uma mensagem informando a distância percorrida até o momento.




```python
from prettytable import PrettyTable

# Criar a tabela
table = PrettyTable()
# Adicionar as linhas à tabela
table.field_names = ["Exemplos de Entrada", "Exemplos de Saída"]
table.add_row([2, "Explorador: 1 passo"])
table.add_row(["", "Explorador: 2 passos"])
table.add_row(["", ""])
table.add_row(["", "Explorador: 1 passo"])
table.add_row([3, "Explorador: 2 passos"])
table.add_row(["", "Explorador: 3 passos"])
table.add_row(["", "Explorador: 2 passos"])
table.add_row(["", ""])
table.add_row([0, "Nenhum passo dado na floresta"])
# Exibir a tabela
print(table)

```

    +---------------------+-------------------------------+
    | Exemplos de Entrada |       Exemplos de Saída       |
    +---------------------+-------------------------------+
    |          2          |      Explorador: 1 passo      |
    |                     |      Explorador: 2 passos     |
    |                     |                               |
    |                     |      Explorador: 1 passo      |
    |          3          |      Explorador: 2 passos     |
    |                     |      Explorador: 3 passos     |
    |                     |      Explorador: 2 passos     |
    |                     |                               |
    |          0          | Nenhum passo dado na floresta |
    +---------------------+-------------------------------+
    

# Resolução


```python
# Desafio: A Aventura do Explorador
# Entrada
quantidade_passos = [2,3,0]

def aventura_do_explorador(qtde_passos):
    """
    Simula a aventura do explorador na floresta, conforme o número de passos fornecido pelo usuário.
    """

    # Verifica se a quantidade de passos é positiva
    if qtde_passos > 0:
        # Realiza um loop do tamanho da quantidade de passos
        for n in range(1, qtde_passos + 1):
            if n == 1:
                print(f"Explorador: {n} passo")
            else:
                print(f"Explorador: {n} passos")

    # Se a quantidade de passos for zero, imprime uma mensagem específica
    elif qtde_passos == 0:
        print("Nenhum passo dado na floresta.")

    # Se a quantidade de passos for negativa, informa ao usuário que a entrada é inválida
    else:
        print("Quantidade de passos não pode ser negativa.")

# Chamada da função principal para iniciar a aventura do explorador
for i in quantidade_passos:
    aventura_do_explorador(i)
    print('\n')

```

    Explorador: 1 passo
    Explorador: 2 passos
    
    
    Explorador: 1 passo
    Explorador: 2 passos
    Explorador: 3 passos
    
    
    Nenhum passo dado na floresta.
    
    
    

# Desafio 2
- Em um jogo de RPG, os personagens geralmente possuem uma lista de itens que podem ser utilizados durante o jogo. Esses itens podem ser armas, armaduras, poções de cura, entre outros. É importante que o jogador tenha um controle desses itens para poder utilizá-los no momento adequado.

- Crie um programa que permita cadastrar uma lista de itens que o personagem possui. A lista deve conter o valor fixo de 3 itens e deve ser exibida na tela.


### Entrada

- O programa deve solicitar ao usuário o nome dos 3 itens que o personagem possui. 

- Cada item deve ser cadastrado separadamente.

### Saída

- Após receber os itens cadastrados pelo usuário, o programa deve exibir na tela a lista de itens que o personagem possui. 
- A saída deve ter o seguinte formato:

```
Lista de itens:
- [item1]
- [item2]
- [item3]
```


### Exemplos


```python
from prettytable import PrettyTable

# Criar a tabela
table = PrettyTable()
# Adicionar as linhas à tabela
table.field_names = ["Exemplos de Entrada", "Exemplos de Saída"]
table.add_row(["", "Lista de itens:"])
table.add_row(["Espada", "- Espada"])
table.add_row(["Escudo", "- Escudo"])
table.add_row(["Poção", "- Poção"])
table.add_row(["", ""])
table.add_row(["", "Lista de itens:"])
table.add_row(["Gema", "- Gema"])
table.add_row(["Flecha", "- Flecha"])
table.add_row(["Capa", "- Capa"])
table.add_row(["", ""])
table.add_row(["", "Lista de itens:"])
table.add_row(["Masterball", "- Masterball"])
table.add_row(["Potion", "- Potion"])
table.add_row(["Elixir", "- Elixir"])
# Exibir a tabela
print(table)

```

    +---------------------+-------------------+
    | Exemplos de Entrada | Exemplos de Saída |
    +---------------------+-------------------+
    |                     |  Lista de itens:  |
    |        Espada       |      - Espada     |
    |        Escudo       |      - Escudo     |
    |        Poção        |      - Poção      |
    |                     |                   |
    |                     |  Lista de itens:  |
    |         Gema        |       - Gema      |
    |        Flecha       |      - Flecha     |
    |         Capa        |       - Capa      |
    |                     |                   |
    |                     |  Lista de itens:  |
    |      Masterball     |    - Masterball   |
    |        Potion       |      - Potion     |
    |        Elixir       |      - Elixir     |
    +---------------------+-------------------+
    

# Resolução

```python
# Lista para armazenar os itens
input1 = ['Espada', 'Escudo', 'Poção']
input2 = ['Gema', 'Flecha', "Capa"]
input3 = ["Masterball", "Potion", "Elixir"]

def show_items(input):
  print("Lista de itens:")
  # Exibindo items separadamente
  for i in range(3):
      item = input[i]
      print("-", item)
  print('\n')
      
show_items(input1)
show_items(input2)
show_items(input3)
    
```

    Lista de itens:
    - Espada
    - Escudo
    - Poção
    
    
    Lista de itens:
    - Gema
    - Flecha
    - Capa
    
    
    Lista de itens:
    - Masterball
    - Potion
    - Elixir
    
    
    

# Desafio 3

Com as máquinas pesadas agrupadas estrategicamente, graças ao seu algoritmo de cálculo energético, agora a mineração está muito mais eficiente! Com isso, os CodeMiners logo terão que aumentar a capacidade de armazenamento de dados em seus discos de Mithril. Atualmente, cada máquina tem uma capacidade em teraflops e todas terão um upgrade! Escreva um programa que calcule a nova capacidade total de todas as máquinas após um aumento percentual específico.

### Entrada

Dois valores inteiros positivos, representando a capacidade atual total em teraflops e o aumento percentual, separados por espaço.


### Saída

Dois valores inteiros positivos, representando a capacidade atual total em teraflops e o aumento percentual, separados por espaço.


### Exemplos



```python
# Criando a tabela
tabela = PrettyTable(["Entrada", "Saída"])

# Adicionando os dados à tabela
tabela.add_row(["100 20", 120])
tabela.add_row(["50 10", 55])
tabela.add_row(["200 50", 300])

# Exibindo a tabela
print(tabela)
```

    +---------+-------+
    | Entrada | Saída |
    +---------+-------+
    |  100 20 |  120  |
    |  50 10  |   55  |
    |  200 50 |  300  |
    +---------+-------+
    

# Resolução

```python
capacidade1, aumento1 = [100, 20]
capacidade2, aumento2 = [50, 10]
capacidade3, aumento3 = [200, 50]

def teraflop_calc(capacidade, aumento):
  # Calcula o aumento em teraflops
  aumento_teraflops = (aumento / 100) * capacidade
  
  # Calcula a nova capacidade total
  nova_capacidade = capacidade + aumento_teraflops
  
  # Imprime a nova capacidade
  print(int(nova_capacidade), "\n")
  

teraflop_calc(capacidade1, aumento1)
teraflop_calc(capacidade2, aumento2)
teraflop_calc(capacidade3, aumento3)
```

    120 
    
    55 
    
    300 
    
    
