# Desafio de código python

Resolução dos exercícios conforme as devidas solicitações, os códigos foram inclusos em funções para facilitar os testes para comparação com os exemplos.

# Desafio 1

Você foi contratado pela empresa DIO Robots para programar um robô capaz de classificar números em uma das seguintes categorias: negativo, positivo ou zero. Para isso, você deve criar uma função de classificação que receba um número como parâmetro e retorne a mensagem "negativo!" ou " positivo!", de acordo com sua categoria.

O programa deve ser executado continuamente, permitindo que o usuário insira vários números. Quando ele quiser encerrar a execução, deverá digitar um número igual a zero. A cada novo número inserido, o robô deve classificá-lo e exibir a mensagem correspondente. Ao final da execução, o programa deverá exibir a quantidade de números positivos, negativos e zeros que foram inseridos.

### Entrada

A entrada deve receber valores inteiros.

- **numero:** valor inteiro que pode ser positivo, negativo ou zero. Lembrando que a entrada zero deve encerrar o programa.

### Saída

1O código deverá retornar uma mensagem (string) informando se o número é positivo ou não. Ao receber o valor 0, ele deverá encerrar o e informar quantos números foram positivos e negativos.

### Exemplos

A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.


```python
from prettytable import PrettyTable

# Create the table
table = PrettyTable()

# Criando a tabela
table = PrettyTable(["Entrada", "Saída"])



# Add columns
table.field_names = ["Entrada", "Saída"]

# Add rows
table.add_row(["1\n-1\n2\n0", "positivo!\nnegativo!\npositivo!\n2 números positivos, 1 número negativo"])
table.add_row(["", ""])
table.add_row(["1\n-1\n0", "positivo!\nnegativo!\n1 número positivo, 1 número negativo"])
table.add_row(["", ""])
table.add_row(["1\n1\n-1\n-1\n0", "positivo!\npositivo!\nnegativo!\nnegativo!\n2 números positivos, 2 números negativos"])

# Print the table
print(table)
```

    +---------+------------------------------------------+
    | Entrada |                  Saída                   |
    +---------+------------------------------------------+
    |    1    |                positivo!                 |
    |    -1   |                negativo!                 |
    |    2    |                positivo!                 |
    |    0    |  2 números positivos, 1 número negativo  |
    |         |                                          |
    |    1    |                positivo!                 |
    |    -1   |                negativo!                 |
    |    0    |   1 número positivo, 1 número negativo   |
    |         |                                          |
    |    1    |                positivo!                 |
    |    1    |                positivo!                 |
    |    -1   |                negativo!                 |
    |    -1   |                negativo!                 |
    |    0    | 2 números positivos, 2 números negativos |
    +---------+------------------------------------------+
    

# Resolução


```python
def classificar_numero(numero):
    if numero > 0:
        return "positivo!"
    elif numero < 0:
        return "negativo!"
    else:
        return ""
    
def main(input_list):
    positivos = 0
    negativos = 0
    
    for numero in input_list:
        classificacao = classificar_numero(numero)
        print(classificacao)
        
        if classificacao == "positivo!":
            positivos += 1
        elif classificacao == "negativo!":
            negativos += 1
    
    print(f"{positivos} números positivos, {negativos} números negativos")

if __name__ == "__main__":
    input1 = [1, -1, 2, 0]
    input2 = [1, -1, 0]
    input3 = [1, 1, -1, -1, 0]

    print("Input 1:")
    main(input1)
    
    print("\nInput 2:")
    main(input2)
    
    print("\nInput 3:")
    main(input3)

```

    Input 1:
    positivo!
    negativo!
    positivo!
    
    2 números positivos, 1 números negativos
    
    Input 2:
    positivo!
    negativo!
    
    1 números positivos, 1 números negativos
    
    Input 3:
    positivo!
    positivo!
    negativo!
    negativo!
    
    2 números positivos, 2 números negativos
    

# Desafio 2

Nesta missão, sua tarefa é mais desafiadora do que nunca! Em um pomar mágico, as frutas têm características únicas que as diferenciam. Seu objetivo é criar um modelo de machine learning capaz de classificar frutas com base em três características: peso, textura (suave ou áspera) e cor (vermelha, laranja ou amarela). Cada tipo de fruta tem limites específicos para essas características.

- Maçã:

    - Peso mínimo: 130 gramas
    - Textura: Ápera (rough)
    - Cor: Vermelha (red)

- Laranja:

    - Peso mínimo: 120 gramas
    - Textura: Suave (smooth)
    - Cor: Laranja (orange)

- Morango:

    - Peso mínimo: 150 gramas
    - Textura: Suave (smooth)
    - Cor: Vermelha (red)

- Banana:

    - Peso mínimo: 150 gramas
    - Textura: Áspera (rough)
    - Cor: Amarela (yellow)


### Entrada

Seu código deve receber as seguintes entradas do usuário:

- Peso da fruta (em gramas): um número real que representa o peso da fruta.
Textura da fruta (suave ou áspera): uma string indicando se a fruta é suave ("smooth") ou áspera ("rough").
Cor da fruta (vermelha, laranja ou amarela): uma string indicando a cor da fruta.

### Saída

O código deve produzir uma saída indicando a classificação da fruta com base nas características fornecidas.


### Exemplos

A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.


```python
from prettytable import PrettyTable

# Create the table
table = PrettyTable()

# Add columns
table.field_names = ["Entrada", "Saída"]

# Add rows
table.add_row(["150\nsmooth\nred", "A fruta é um morango!"])
table.add_row([" ", " "])
table.add_row(["140\nrough\nyellow", "Não foi possível classificar a fruta."])
table.add_row([" ", " "])
table.add_row(["150\nsmooth\norange", "A fruta é uma laranja!"])

# Print the table
print(table)
```

    +---------+---------------------------------------+
    | Entrada |                 Saída                 |
    +---------+---------------------------------------+
    |   150   |         A fruta é um morango!         |
    |  smooth |                                       |
    |   red   |                                       |
    |         |                                       |
    |   140   | Não foi possível classificar a fruta. |
    |  rough  |                                       |
    |  yellow |                                       |
    |         |                                       |
    |   150   |         A fruta é uma laranja!        |
    |  smooth |                                       |
    |  orange |                                       |
    +---------+---------------------------------------+
    

# Resolução


```python
def prever_fruta(peso, textura, cor):
     # Lógica de decisão baseada nas características fornecidas
    if peso >= 150 and textura == "smooth" and cor == "red":
        return "A fruta é um morango!"
    elif peso >= 150 and textura == "rough" and cor == "yellow":
        return "A fruta é uma banana!"
    elif peso >= 130 and textura == "rough" and cor == "red":
        return "A fruta é uma maçã!"
    elif peso >= 120 and textura == "smooth" and cor == "orange":
        return "A fruta é uma laranja!"
    else:
        return "Não foi possível classificar a fruta."
# TODO: Desenvolva a Função para prever a classe da fruta


peso_fruta = [150, 140, 150]
textura_fruta = ['smooth', 'rough', 'smooth']
cor_fruta = ['red', 'yellow', 'orange']

# Chamada da função de previsão
for i in range(3):
    print(prever_fruta(peso_fruta[i], textura_fruta[i], cor_fruta[i]), '\n')

```

    A fruta é um morango! 
    
    Não foi possível classificar a fruta. 
    
    A fruta é uma laranja! 
    
    

# Desafio 3

No reino mágico onde cada feiticeiro possui uma afinidade elemental única, seu desafio é criar um modelo de machine learning para prever essa afinidade. Os feiticeiros podem pertencer a um dos quatro elementos mágicos: Fogo, Água, Terra ou Ar. A predição será baseada em cinco atributos mágicos: intensidade do feitiço, presença de componente raro, fase lunar, idade do feiticeiro e afinidade com animais mágicos.

Aqui estão os critérios mágicos para cada elemento:

- Elemento Fogo:

    - Intensidade do feitiço maior ou igual a 5.
    - Fase lunar durante o feitiço é crescente.
    - Idade do feiticeiro é superior a 100 anos.

- Elemento Água:

    - Intensidade do feitiço maior ou igual a 7.
    - Presença de componente raro.
    - Fase lunar durante o feitiço é cheia.
    - Idade do feiticeiro é igual ou inferior a 100 anos.
    - Afinidade com animais mágicos.

- Elemento Terra:

    - Intensidade do feitiço maior ou igual a 7.
    - Presença de componente raro.
    - Fase lunar durante o feitiço é cheia.
    - Idade do feiticeiro é igual ou inferior a 100 anos.
    - Afinidade com animais mágicos.

- Elemento Ar:

    - Caso não se encaixe nos critérios anteriores.


### Entrada

Seu código deve receber as seguintes entradas do usuário:

- Intensidade do feitiço (de 1 a 10): um número inteiro representando a força do feitiço.
- Componente raro (sim ou não): uma string indicando se o feitiço contém um componente raro.
- Fase lunar (cheia, crescente ou minguante): uma string indicando a fase lunar durante o lançamento do feitiço.
- Idade do feiticeiro (em anos): um número inteiro representando a idade do feiticeiro.
- Afinidade com animais mágicos (sim ou não): uma string indicando se o feiticeiro tem afinidade com animais mágicos.


### Saída

O código deve produzir uma saída indicando a afinidade elemental prevista do feiticeiro com base nos atributos fornecidos.


### Exemplos

A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.



```python
# Create the table
table = PrettyTable()

# Add columns
table.field_names = ["Entrada", "Saída"]

# Add rows
table.add_row(["6\nsim\ncrescente\n110\nsim", "\n\nA afinidade elemental do feiticeiro é com o elemento Fogo!"])
table.add_row(["", ""])
table.add_row(["8\nsim\ncheia\n80\nnão", "\n\nA afinidade elemental do feiticeiro é com o elemento Água!"])
table.add_row(["", ""])
table.add_row(["9\nsim\ncheia\n80\nsim", "\n\nA afinidade elemental do feiticeiro é com o elemento Terra!"])
table.add_row(["", ""])

# Print the table
print(table)
```

    +-----------+-------------------------------------------------------------+
    |  Entrada  |                            Saída                            |
    +-----------+-------------------------------------------------------------+
    |     6     |                                                             |
    |    sim    |                                                             |
    | crescente |  A afinidade elemental do feiticeiro é com o elemento Fogo! |
    |    110    |                                                             |
    |    sim    |                                                             |
    |           |                                                             |
    |     8     |                                                             |
    |    sim    |                                                             |
    |   cheia   |  A afinidade elemental do feiticeiro é com o elemento Água! |
    |     80    |                                                             |
    |    não    |                                                             |
    |           |                                                             |
    |     9     |                                                             |
    |    sim    |                                                             |
    |   cheia   | A afinidade elemental do feiticeiro é com o elemento Terra! |
    |     80    |                                                             |
    |    sim    |                                                             |
    |           |                                                             |
    +-----------+-------------------------------------------------------------+
    

# Resolução


```python
# Função para prever a afinidade elemental do feiticeiro
def prever_afinidade_elemental(intensidade, componente_raro, fase_lunar, idade_feiticeiro, afinidade_animais):
    # Convertendo a resposta do componente raro e afinidade com animais para booleanos
    componente_raro = componente_raro.lower() == "sim"
    afinidade_animais = afinidade_animais.lower() == "sim"

    # Desenvolvendo a Lógica de decisão para prever a afinidade elemental
    if intensidade >= 5 and fase_lunar == "crescente" and idade_feiticeiro > 100:
        return "A afinidade elemental do feiticeiro é com o elemento Fogo!"
    elif intensidade >= 7 and componente_raro and fase_lunar == "cheia" and idade_feiticeiro <= 100 and afinidade_animais:
        return "A afinidade elemental do feiticeiro é com o elemento Terra!"
    elif intensidade >= 7 and componente_raro and fase_lunar == "cheia" and idade_feiticeiro <= 100:
        return "A afinidade elemental do feiticeiro é com o elemento Água!"
    elif intensidade >= 5:
        return "A afinidade elemental do feiticeiro é com o elemento Ar!"
    else:
        return "A afinidade elemental do feiticeiro não pode ser determinada."
   

# Entrada do usuário
intensidade_feitico = [6,8,9]
componente_raro_feitico = ['sim', 'sim', 'sim']
fase_lunar_feitico = ['crescente', 'cheia', 'cheia']
idade_feiticeiro = [110, 80, 80]
afinidade_animais_feiticeiro = ['sim', 'não', 'sim']

# Fazendo a previsão
for i in range(3):
    print(prever_afinidade_elemental(intensidade_feitico[i], componente_raro_feitico[i], fase_lunar_feitico[i], idade_feiticeiro[i], afinidade_animais_feiticeiro[i]), '\n')

```

    A afinidade elemental do feiticeiro é com o elemento Fogo! 
    
    A afinidade elemental do feiticeiro é com o elemento Água! 
    
    A afinidade elemental do feiticeiro é com o elemento Terra! 
    
    
