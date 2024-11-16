# Funcao-Cadastro-APP-BEL
Função de Login e Cadastro do projeto de aplicativo BEL. Desenvolvimento acadêmico.

import getpass

# Lista para armazenar os dados dos usuários
usuarios = []

def cadastrar_usuario():
    print("\n--- Cadastro de Usuário ---")

  # Captura o e-mail
   email = input("Digite seu e-mail: ")
    
  # Verifica se o e-mail já foi cadastrado
  for usuario in usuarios:
      if usuario['email'] == email:
          print("Erro: Este e-mail já está cadastrado.\n")
          return

   # Captura o nome de usuário
  nome = input("Digite seu nome: ")

   # Captura a senha e confirmação de senha
  senha = getpass.getpass("Digite sua senha: ")
   confirma_senha = getpass.getpass("Confirme sua senha: ")

  # Valida a confirmação de senha
   if senha != confirma_senha:
      print("Erro: As senhas não coincidem.\n")
      return

   # Armazena os dados do usuário no sistema (simulado em uma lista)
   usuarios.append({
      'nome': nome,
      'email': email,
      'senha': senha
   })

   print(f"\nCadastro realizado com sucesso! Seja bem-vindo, {nome}.")

def exibir_usuarios():
    if usuarios:
        print("\n--- Usuários Cadastrados ---")
        for i, usuario in enumerate(usuarios, 1):
            print(f"{i}. Nome: {usuario['nome']} | E-mail: {usuario['email']}")
    else:
        print("Nenhum usuário cadastrado no sistema.")

# Execução do programa
while True:
    print("\n1. Cadastrar Novo Usuário")
    print("2. Exibir Usuários Cadastrados")
    print("3. Sair")

   opcao = input("Escolha uma opção: ")

   if opcao == '1':
      cadastrar_usuario()
   elif opcao == '2':
       exibir_usuarios()
   elif opcao == '3':
       print("Encerrando o programa...")
       break
   else:
      print("Opção inválida. Tente novamente.")
