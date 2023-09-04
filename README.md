# Desafio_Dio_Python
Desafio Python criar um sistema bancário

**Objetivo Geral**

Criar um sistema bancário com as operações: sacar, depositar e visualizar extrato.

**Desafio**

Fomos contratados por um grande banco para desenvolver o seu novo sistema. Esse banco deseja modernizar suas operações e para isso escolheu a linguagem Python. Para a primeira versão do sistema devemos implementar apenas 3 operações: depósito, saque e extrato.

**Operação de depósito**

Deve ser possível depositar valores positivos para a minha conta bancária. A v1 do projeto trabalha apenas com 1 usuário, dessa forma não precisamos nos preocupar em identificar qual é o número da agência e conta bancária. Todos os depósitos devem ser armazenados em uma variável e exibidos na operação de extrato.

**Operação de saque**

O sistema deve permitir realizar 3 saques diários com limite máximo de R$ 500,00 por saque. Caso o usuário não tenha saldo em conta, o sistema deve exibir uma mensagem informando que não será possível sacar o dinheiro por falta de saldo. Todos os saques devem ser armazenados em uma variável e exibidos na operação de extrato.

**Operação de extrato**

Essa operação deve listar todos os depósitos e saques realizados na conta. No fim da listagem deve ser exibido o saldo atual da conta. Se o extrato estiver em branco, exibir a mensagem: (Não foram realizadas movimentações). Os valores devem ser exibidos utilizando o formato R$ xxx.xx, exemplo: 1500.45 = R$ 1500.45

**Códigos usado no Python**

Para dar solução ao desafio, foram utilizados os comandos abaixo, com base orientada pelo instrutor:

menu = """

[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair

=> """

saldo = 0

limite = 700

extrato = ""

numero_saques = 0

LIMITE_SAQUES = 3


while True:

    opcao = input(menu)

    if opcao == "d":
        valor = float(input("Informe o valor do depósito: "))

        if valor > 0:
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f}\n"

        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "s":
        valor = float(input("Informe o valor do saque: "))

        excedeu_saldo = valor > saldo

        excedeu_limite = valor > limite

        excedeu_saques = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print("Operação falhou! Você não tem saldo suficiente.")

        elif excedeu_limite:
            print("Operação falhou! O valor do saque excede o limite.")

        elif excedeu_saques:
            print("Operação falhou! Número máximo de saques excedido.")

        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1

        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "e":
        print("\n================ EXTRATO ================")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("==========================================")

    elif opcao == "q":
        break

    else:
        print("Operação inválida, por favor selecione novamente a operação desejada.")

        
**Evidências dos comandos**

Foram realizados os testes de cada comando, para verificar eficácia dos mesmos.


  oendi@LAPTOP-6LGU484R MINGW64 ~
$ C:/Users/oendi/AppData/Local/Programs/Python/Python311/python.exe "c:/Users/oendi/OneDrive/Dio.me/Python/Desafio Sistema Bancario.py"


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair

=> e


================ EXTRATO ================

Não foram realizadas movimentações.

Saldo: R$ 0.00

==========================================


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> C:/Users/oendi/AppData/Local/Programs/Python/Python311/python.exe "c:/Users/oendi/OneDrive/Dio.me/Python/Desafio Sistema Bancario II.py"
Operação inválida, por favor selecione novamente a operação desejada.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> c

Operação inválida, por favor selecione novamente a operação desejada.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> C:/Users/oendi/AppData/Local/Programs/Python/Python311/python.exe "c:/Users/oendi/OneDrive/Dio.me/Python/Desafio Sistema Bancario II.py"
Operação inválida, por favor selecione novamente a operação desejada.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> C:/Users/oendi/AppData/Local/Programs/Python/Python311/python.exe "c:/Users/oendi/OneDrive/Dio.me/Python/Desafio Sistema Bancario II.py"
Operação inválida, por favor selecione novamente a operação desejada.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> C:/Users/oendi/AppData/Local/Programs/Python/Python311/python.exe "c:/Users/oendi/OneDrive/Dio.me/Python/Desafio Sistema Bancario II.py"
Operação inválida, por favor selecione novamente a operação desejada.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> C:/Users/oendi/AppData/Local/Programs/Python/Python311/python.exe "c:/Users/oendi/OneDrive/Dio.me/Python/Desafio Sistema Bancario II.py"
Operação inválida, por favor selecione novamente a operação desejada.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> e

================ EXTRATO ================

Não foram realizadas movimentações.

Saldo: R$ 0.00

==========================================


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> s

Informe o valor do saque: 500

Operação falhou! Você não tem saldo suficiente.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> r

Operação inválida, por favor selecione novamente a operação desejada.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> d

Informe o valor do depósito: 100


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> e


================ EXTRATO ================

Depósito: R$ 100.00


Saldo: R$ 100.00

==========================================


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> s

Informe o valor do saque: 90


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> e

================ EXTRATO ================

Depósito: R$ 100.00
Saque: R$ 90.00


Saldo: R$ 10.00

==========================================


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> d

Informe o valor do depósito: 600


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> e

================ EXTRATO ================

Depósito: R$ 100.00
Saque: R$ 90.00
Depósito: R$ 600.00


Saldo: R$ 610.00

==========================================


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> s

Informe o valor do saque: 510

Operação falhou! O valor do saque excede o limite.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> s

Informe o valor do saque: 300


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> e

================ EXTRATO ================

Depósito: R$ 100.00
Saque: R$ 90.00
Depósito: R$ 600.00
Saque: R$ 300.00


Saldo: R$ 310.00

==========================================


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> s

Informe o valor do saque: 200


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> e

================ EXTRATO ================

Depósito: R$ 100.00
Saque: R$ 90.00
Depósito: R$ 600.00
Saque: R$ 300.00
Saque: R$ 200.00


Saldo: R$ 110.00

==========================================


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair

=> s

Informe o valor do saque: 110

Operação falhou! Número máximo de saques excedido.


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> e

================ EXTRATO ================

Depósito: R$ 100.00
Saque: R$ 90.00
Depósito: R$ 600.00
Saque: R$ 300.00
Saque: R$ 200.00


Saldo: R$ 110.00

==========================================


[d] Depositar

[s] Sacar

[e] Extrato

[q] Sair


=> q
