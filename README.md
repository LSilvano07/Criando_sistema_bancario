saldo = 0 
limite = 500
extrato = ''
numero_saques = 0 
LIMITE_SAQUES = 3


while True:
    
    menu = input('Bem vindo ao Banco Dinheiro eu nao vejo!\nEscolha a opção desejada para continuar:\n[d] Depositar\n[s] Sacar\n[e] Extrato\n[q] Sair: ')
 
    if menu == 'd':
        valor = float(input('Digite um valor para depósito: ' ))
        
        if valor > 0:
            saldo += valor
            extrato += f'Depósito: R$ {valor:.2f}\n'
        
        else: 
            print('Operação falhou! O valor informado é inválido.')
    
    if menu == 's':
        if numero_saques < LIMITE_SAQUES:

            numero_saques += 1

            valor = float(input('Informe o valor de saque:'))
            saldo = saldo - valor

            if valor > limite: 
                print('Valor de saque ultrapassa o limite, tente novamente!')
            
            elif saldo < valor:
                print('Saldo insuficiente!')
            
            elif valor <= saldo:
                extrato += f'Saque: R$ {valor:.2f}\n'
                print('Saque realizado com sucesso!')

        else:
            print('Limite de saques atingido!')

    elif menu == 'e':
        print('\n=============== EXTRATO ===============')
        print('Não foram realizadas movimentações.' if not extrato else extrato)
        print(f'\nSaldo: R$ {saldo:.2f}')
        print('=======================================') 

    if menu == 'q':
    
        break
