from Pessoas import Pessoas

pessoas=Pessoas('moleza.sqlite')

while True:
    print("""   
    Escolha uma opção:
    1 - Inserir seus dados
    2 - Ler os dados
    3 - Alterar algum dado
    4 - Deletar um id 
    5 - Sair
""")
    valor= input('--> ')
    if valor == "1":
        nome = str(input("Digite o seu nome: "))
        cpf= int(input("Digite o seu cpf: "))
        dados = {
            'tabela':'pessoas',
            'campos': ['nome','cpf'],
            'valores': [nome,cpf]
}
        pessoas.inserir_dados(nome,cpf)
    elif valor == "2":
        results= pessoas.ler_tabela()
        print('RESULTADO:', results)
    elif valor =="3":
        nome = str(input("Digite o seu nome: "))
        cpf= int(input("Digite o seu cpf: "))
        dados = {
            'tabela':'pessoas',
            'campos': ['nome','cpf'],
            'valores': [nome,cpf]
}
        pessoas.alterar_dados()
    elif valor == "4":
        a_id= int(input("Digite o id para deletar os dados: "))
        pessoas.deletar_dados(a_id)
    else:
        break
