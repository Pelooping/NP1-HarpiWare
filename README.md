print("Esse codigo é de uso exclusivo para associados HarpiWare\n")
print("Bem-vindos ao menu de cálculo mensal da HarpiWare\nDispomos de três categorias disponíveis no momento: Ouro, Prata e Bronze.")

print('Por sermos uma afiliada kabum temos desconto de custo de ate 50% nos componentes Ouro e Prata ')

estoque = {

"ouro": {"Fonte : MSI MAG A850GL, 850W, 80 Plus Gold, Modular, PFC Ativo, Com Cabo, Preto" : 314.50,

         "Gabinete Gamer Corsair 3000D RGB Airflow, Mid-Tower, ATX, Lateral em Vidro Temperado, com FAN, Branco - CC-9011256-WW" : 325.00,

         "Processador : Intel Core i9-14900K, 14ª Geração, 6GHz Max Turbo, Cache 36MB, 24 Núcleos, 32 Threads, LGA1700 - BX8071514900K": 1700.00,

         "Paca-Mãe: ASRock B450M Steel Legend, AMD AM4, mATX, DDR4, Preto - B450M Steel Legend" : 379.50, 

         "Placa de Vídeo: RTX 3060 Inno3D Twin X2 OC NVIDIA Geforce, 12GB GDDR6": 999.95, 

         "Memória RAM: Kingston Fury Beast, 16GB, 3200MHz, DDR4 " : 130.00, 

         "SSD: Kingston NV3, 1 TB, M.2 2280" : 222.50, 

         "WINDOWS 11 PRO + OFFICE 2021 PRO PLUS 32/64 BITS + LICENÇA VITALÍCIA + NOTA FISCAL": 179.99},



"prata": { "Gabinete Gamer Rise Mode Glass 06x, Mid Tower, ARGB, ATX, Lateral e Frente em Vidro, 6x Fans, Preto - RM-CA-06XB-ARGB" : 174.95,

           "Fonte Gamer Rise Mode Zeus, 650W, Modular, PFC Ativo, Preto - RM-PSU-01-BZ-650" : 164.95,

           "Processador Intel Core i5-10400F, 2.9GHz (4.3GHz Max Turbo), Cache 12MB, 6 Núcleos, 12 Threads, LGA 1200 - BX8070110400F": 349.95, 

           "Placa Mãe Gigabyte B450M Gaming, AMD AM4, mATX, DDR4, Chipset Amd B450" : 217.45,

          " Placa De Vídeo Zotac Gtx1650, 4GB, GDDR6 Amp - T16520j-10l" : 675.00, 

           "Memória RAM XPG Gammix D35, 8GB, 3200MHz, DDR4, CL16, Preto - AX4U32008G16A-SBKD35": 75.00, 

           "SSD Kingston A400, 480GB, SATA III, 2.5, Leitura: 500MB/s, Gravação: 450MB/s, Preto - SA400S37/480G" : 120.00, 

           "WINDOWS 11 PRO + OFFICE 2021 PRO PLUS 32/64 BITS + LICENÇA VITALÍCIA + NOTA FISCAL" : 90.00},

"bronze": {"Gabinete Gamer Rise Mode Z3 Glass, Lateral em Vidro Fumê, Preto - RM-Z03-03-FB" : 105.00,

           "Processador AMD Ryzen 3 5300G, 4GHz (4.2GHz Max Turbo), Cache 8MB, AM4, 4 Núcleos, 8 Threads, Vídeo Integrado - 100-100000253BOX": 599.99,

           "Placa Mãe Gigabyte B450M Gaming, AMD AM4, mATX, DDR4, Chipset Amd B450" : 434.90, 

           "Memória RAM Kingston Fury Beast, 8GB, 3200MHz, DDR4, CL16, Preto - KF432C16BB/8": 149.99, 

           "SSD WD Green, 240GB, SATA III, 2.5, Leitura: 545MB/s, Gravação: 430MB/s, Preto - WDS240G3G0A": 189.99, 

           "WINDOWS 11 PRO + OFFICE 2021 PRO PLUS 32/64 BITS + LICENÇA VITALÍCIA + NOTA FISCAL" : 179.99}

}

despesasfixas = {"Energia" :  580.00, "Agua" : 60.00, "Minigalpao" : 800.00, "internet" : 159.99}

participacao_lucro = {"Fabio" : 0.40, "Pedro" : 0.15, "Maria Eduarda" : 0.15, "Ana Flavia" : 0.15, "João" : 0.15 }

while True:
    print('_' * 60)
    categoria_escolhida1 = input('Digite a categoria desejada (ouro, prata ou bronze): ').strip().lower()

    if categoria_escolhida1 not in estoque:
        print('Categoria inválida. Por favor, escolha entre "ouro", "prata" ou "bronze".')
        continue

    print('_' * 60)
    print(f'\nCategoria: {categoria_escolhida1.upper()}\n')
    print("_" * 60)
    for k, v in estoque[categoria_escolhida1].items():
        print(f'{k}: R$ {v}')

  

    print("_" * 60)
    
    # Loop para solicitar a quantidade correta
    while True:
        try:
            quantidade = int(input('\nDigite a quantidade vendida neste mês deste item:'))
            print("_" * 60)
            
            break  # Se for um número válido para o loop
        except ValueError:
            print('Digite um valor numérico válido.')

    total_custo = sum(estoque[categoria_escolhida1].values())
    lucro = total_custo * 0.25
    lucro_real = total_custo + lucro
    montante_mensal = lucro_real * quantidade
    juros_final = lucro * quantidade
    descontos = sum(despesasfixas.values())
    lucro_descontado =  juros_final - descontos
    divi = "_" * 60

    print(f"\nA CATEGORIA {categoria_escolhida1.upper()} OBTEVE OS SEGUINTE VALORES:\n\n")
    print(f"Valor de custo por unidade: R${total_custo:.2f}\n{divi}\n")
    print(f"Valor por unidade vendida : R${lucro_real:.2f}\n{divi}\n")
    print(f"Com a porcentagem de 25% por total de custo :\nLucro estimado por unidade: R$ {lucro:.2f}\n{divi}\n")
    print(f"Quantidade vendida mensal da categoria: {quantidade}\n{divi}\n")
    print(f"O montante final de venda foi de: R$ {montante_mensal:.2f}\n{divi}\n")
    
    print("Despesas:\n")
 
    for k, v in despesasfixas.items():
        print(f'{k}: R$ {v}')
    
    print(f"A quantidade de descontos fixos foram: {descontos:.2f}")
    print("_" * 60)
    
    print(f"Lucro final foi de: R$ {lucro_descontado:.2f}\n")
    
    
    print('Participação nos lucros:\n\nFabio 40%\nPedro 15%\nMaria Eduardo 15%\nAna Flavia 15%\nJoão 15%\n')


    while True:

         nome_socio = input('Digite seu nome para ver sua participação nos lucros: ').strip().title()
        
         if nome_socio in participacao_lucro:
            valor_socio = participacao_lucro[nome_socio] * lucro_descontado
            print(f'\nSócio: {nome_socio} receberá o valor de: R$ {valor_socio:.2f}')
            break  # parar  se o nome for válido
        
         else:
            print('Nome inválido. Por favor, escolha um nome de sócio válido.')

    # imput pra perguntar se quer q continue
    continuar = input("Deseja escolher outra categoria? (Sim ou Não): ").strip().lower()
    if continuar != 'sim':
        break
