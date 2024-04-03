# Desafio de código python

Resolução dos exercícios conforme as devidas solicitações, os códigos foram inclusos em funções para facilitar os testes para comparação com os exemplos.

# Desafio 1

Você foi contratado por um banco para desenvolver um programa que auxilie seus clientes a realizar depósitos em suas contas. O programa deve solicitar ao cliente o valor do depósito e verificar se o valor é válido. Se o valor for maior do que zero, o programa deve adicionar o valor ao saldo da conta. Caso contrário, o programa deve exibir uma mensagem de erro. O programa deve solicitar apenas uma vez o valor de depósito.

### Entrada

1. O programa deve receber o valor de depósito digitado pelo cliente. 

2. Os valor pode ser decimal, representando valor em reais.

### Saída

1. O programa deve exibir uma mensagem de sucesso quando um valor de depósito válido for informado e o saldo da conta for atualizado. Se o valor for "0", deverá imprimir uma mensagem encerrando o programa. 

2. Caso um valor inválido seja digitado, o programa deve exibir uma mensagem de erro solicitando um novo valor.

### Exemplos

A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.


```python
from prettytable import PrettyTable

# Criando a tabela
table = PrettyTable(["Entrada", "Saída"])

# Adicionando os dados à tabela
table.add_row([500.50, "Deposito realizado com sucesso!"])
table.add_row(["", ""])
table.add_row([-100, "Valor inválido! Digite um valor maior que zero."])
table.add_row(["", ""])
table.add_row([0, "Encerrando o programa..."])

# Exibindo a tabela
print(table)

```

    +---------+-------------------------------------------------+
    | Entrada |                      Saída                      |
    +---------+-------------------------------------------------+
    |  500.5  |         Deposito realizado com sucesso!         |
    |         |                                                 |
    |   -100  | Valor inválido! Digite um valor maior que zero. |
    |         |                                                 |
    |    0    |             Encerrando o programa...            |
    +---------+-------------------------------------------------+
    

# Resolução


```python
input1, input2, input3 = [500.5, -100, 0]

def caixa_eletronico(valor):
  """Função que recebe um valor de entrada e simula um caixa caixa_eletronico"""  

  saldo = 0
  if valor > 0:
    print("Deposito realizado com sucesso!")
    saldo = saldo + valor
    print(f"Saldo atual: R$ {saldo:.2f}")
    
  elif valor < 0:
    print("Valor invalido! Digite um valor maior que zero.")
  
  else:
    print("Encerrando o programa...")

  print('\n')


  
caixa_eletronico(input1)
caixa_eletronico(input2)
caixa_eletronico(input3)
```

    Deposito realizado com sucesso!
    Saldo atual: R$ 500.50
    
    
    Valor invalido! Digite um valor maior que zero.
    
    
    Encerrando o programa...
    
    
    

# Desafio 2

Após uma análise cuidadosa realizada pela equipe de desenvolvimento de uma empresa bancaria, foi identificado a necessidade de uma nova funcionalidade para otimizar os processos e melhorias da experiência dos usuários. Agora, sua tarefa é implementar uma solução que organize em ordem alfabética uma lista de ativos que será informada pelos usuários. Os ativos são representados por strings que representam seus tipos, como por exemplo: Reservas de liquidez, Ativos intangiveis e dentre outros.


### Entrada

1. A primeira entrada consiste em um número inteiro que representa a  quantidade de ativos que o usuário possui. 

2. Em seguida, o usuário deverá  informar, em linhas separadas, os tipos (strings) dos respectivos ativos.


### Saída

Seu programa deve exibir a lista de Ativos organizada em ordem alfabética. Cada ativo deve ser apresentado em uma linha separada.


### Exemplos

A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.


```python
from prettytable import PrettyTable

# Criar a tabela
table = PrettyTable()
table.field_names = ["Entrada", "Saída"]

# Add rows
table.add_row(["3\nFinanciamento de Imovel\nDeposito\nReservas Bancarias", "\nDeposito\nFinanciamento de Imovel\nReservas Bancarias"])
table.add_row(["", ""])
table.add_row(["3\nCarteiras de Credito\nInvestimentos em Titulos\nDerivativos financeiros", "\nCarteiras de credito\nDerivativos financeiros\nInvestimentos em titulos"])
table.add_row(["", ""])
table.add_row(["3\nReserva de liquidez\nAtivos intangiveis\nFundos de investimento", "\nAtivos intangiveis\nFundos de investimento\nReservas de liquidez"])

# Print the table
print(table)

```

    +--------------------------+--------------------------+
    |         Entrada          |          Saída           |
    +--------------------------+--------------------------+
    |            3             |                          |
    | Financiamento de Imovel  |         Deposito         |
    |         Deposito         | Financiamento de Imovel  |
    |    Reservas Bancarias    |    Reservas Bancarias    |
    |                          |                          |
    |            3             |                          |
    |   Carteiras de Credito   |   Carteiras de credito   |
    | Investimentos em Titulos | Derivativos financeiros  |
    | Derivativos financeiros  | Investimentos em titulos |
    |                          |                          |
    |            3             |                          |
    |   Reserva de liquidez    |    Ativos intangiveis    |
    |    Ativos intangiveis    |  Fundos de investimento  |
    |  Fundos de investimento  |   Reservas de liquidez   |
    +--------------------------+--------------------------+
    

# Resolução


```python
# Entrada da quantidade de ativos
input1 = ["Financiamento de Imovel", "Deposito" , "Reservas Bancarias"]
input2 = ["Carteiras de credito", "Investimentos em titulos", "Derivativos financeiros"]
input3 = ["Reservas de liquidez", "Ativos intangiveis", "Fundos de investimento"]


def ordenar_ativos(quantidadeAtivos):
  # Ordenar os ativos em ordem alfabética.
  quantidadeAtivos.sort()
  
  # Imprimir a lista de ativos ordenada, conforme a tabela de exemplos.
  for i in quantidadeAtivos:
    print(i)
  print('\n')  
  
      
  
ordenar_ativos(input1)
ordenar_ativos(input2)
ordenar_ativos(input3)
    
```

    Deposito
    Financiamento de Imovel
    Reservas Bancarias
    
    
    Carteiras de credito
    Derivativos financeiros
    Investimentos em titulos
    
    
    Ativos intangiveis
    Fundos de investimento
    Reservas de liquidez
    
    
    

# Desafio 3

Você está trabalhando para uma empresa que utiliza extensivamente os serviços da AWS, e após algumas análises a equipe de segurança identificou que algumas senhas dos usuários no IAM são fracas e podem representar um risco à segurança dos dados da empresa. Para resolver esse problema, foi solicitado que você desenvolva um programa capaz de analisar as senhas dos usuários e fornecer uma validação de força com base em critérios predefinidos.

**Requisitos de segurança para a senha:**

- A senha deve ter no mínimo 8 caracteres.
- A senha deve conter pelo menos uma letra maiúscula (A-Z).
- A senha deve conter pelo menos uma letra minúscula (a-z).
- A senha deve conter pelo menos um número (0-9).
- A senha deve conter pelo menos um caractere especial, como !, @, #, $, %, etc.

### Entrada

A entrada será uma única string representando a senha que precisa ser validada.


### Saída

Seu programa deve retornar uma mensagem indicando se a senha fornecida pelo usuário atende aos requisitos de segurança ou não, juntamente com um feedback explicativo sobre os critérios considerados.


### Exemplos



```python
# Criando a tabela
tabela = PrettyTable(["Entrada", "Saída"])

table = PrettyTable()

# Add columns
table.field_names = ["Entrada", "Saída"]

# Add rows
table.add_row(["0101", "Sua senha é muito curta. Recomenda-se no mínimo 8 caracteres."])
table.add_row(["", ""])
table.add_row(["030609saturno*", "Sua senha atende aos requisitos de segurança. Parabéns!"])
table.add_row(["", ""])
table.add_row(["010203Jupiter", "Sua senha não atende aos requisitos de segurança."])

# Print the table
print(table)
```

    +----------------+---------------------------------------------------------------+
    |    Entrada     |                             Saída                             |
    +----------------+---------------------------------------------------------------+
    |      0101      | Sua senha é muito curta. Recomenda-se no mínimo 8 caracteres. |
    |                |                                                               |
    | 030609saturno* |    Sua senha atende aos requisitos de segurança. Parabéns!    |
    |                |                                                               |
    | 010203Jupiter  |       Sua senha não atende aos requisitos de segurança.       |
    +----------------+---------------------------------------------------------------+
    

# Resolução


```python
input1, input2, input3 = ["0101", "030609Saturno*", "010203Jupiter"]


def verificar_forca_senha(senha):

    comprimento_minimo = 8
    tem_letra_maiuscula = any(char.isupper() for char in senha)
    tem_letra_minuscula = any(char.islower() for char in senha)
    tem_numero = any(char.isdigit() for char in senha)
    tem_caractere_especial = any(char in "!@#$%^&*()[]{};:,./<>?\\|`~" for char in senha)

    # Verificando o comprimento da senha
    if len(senha) < comprimento_minimo:
        return f"Sua senha é muito curta. Recomenda-se no mínimo {comprimento_minimo} caracteres."

    # Verifique se a senha contém pelo menos uma letra maiúscula e uma minúscula
    if not (tem_letra_maiuscula and tem_letra_minuscula):
        return "Sua senha não atende aos requisitos de segurança."

    # Verificando se a senha contém sequências comuns
    sequencias_comuns = ["123456", "abcdef"]
    for sequencia in sequencias_comuns:
        if sequencia in senha:
            return "Sua senha contém uma sequência comum. Tente uma senha mais complexa."

    # Verificando se a senha contém palavras comuns
    palavras_comuns = ["password", "123456", "qwerty"]
    if senha in palavras_comuns:
        return "Sua senha é muito comum. Tente uma senha mais complexa."

    # Verificando o comprimento da senha
    if len(senha) < comprimento_minimo:
        return f"Sua senha é muito curta. Recomenda-se no mínimo {comprimento_minimo} caracteres."

    if not tem_caractere_especial:
        return "Sua senha não atende aos requisitos de segurança."

    # Se todas as verificações passarem, a senha é considerada forte
    return "Sua senha atende aos requisitos de segurança. Parabéns!"



# Verificando a força da senha
resultado1 = verificar_forca_senha(input1)
resultado2 = verificar_forca_senha(input2)
resultado3 = verificar_forca_senha(input3)

# Imprimindo o resultado
print(resultado1, '\n')
print(resultado2, '\n')
print(resultado3, '\n')

```

    Sua senha é muito curta. Recomenda-se no mínimo 8 caracteres. 
    
    Sua senha atende aos requisitos de segurança. Parabéns! 
    
    Sua senha não atende aos requisitos de segurança. 
    
    
