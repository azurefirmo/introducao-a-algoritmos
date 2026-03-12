INÍCIO

// --- Função para validar senha ---
FUNÇÃO validarSenha(senhaInformada)
SENHA_CORRETA ← 1234
SE senhaInformada = SENHA_CORRETA ENTÃO
RETORNAR VERDADEIRO
SENÃO
RETORNAR FALSO
FIMSE
FIMFUNÇÃO

// --- Função para exibir menu ---
FUNÇÃO exibirMenu()
ESCREVA("===== MENU CAIXA ELETRÔNICO =====")
ESCREVA("1 - Consultar saldo")
ESCREVA("2 - Sacar")
ESCREVA("3 - Depositar")
ESCREVA("0 - Sair")
ESCREVA("Escolha uma opção: ")
FIMFUNÇÃO

// --- Variáveis principais ---
saldo ← 1000
tentativas ← 0
MAX_TENTATIVAS ← 3

// --- Validação de senha ---
REPITA
ESCREVA("Digite sua senha: ")
LEIA(senha)

SE validarSenha(senha) = VERDADEIRO ENTÃO
ESCREVA("Acesso permitido!")
PARE
SENÃO
tentativas ← tentativas + 1
ESCREVA("Senha incorreta! Tentativa ", tentativas, " de ", MAX_TENTATIVAS)
FIMSE

SE tentativas = MAX_TENTATIVAS ENTÃO
ESCREVA("Cartão bloqueado!")
ENCERRA_PROGRAMA
FIMSE
ATÉ validarSenha(senha) = VERDADEIRO

// --- Loop principal do menu ---
REPITA
exibirMenu()
LEIA(opcao)

ESCOLHA opcao
CASO 1:
ESCREVA("Seu saldo é: R$ ", saldo)
CASO 2:
ESCREVA("Valor para saque: ")
LEIA(valor)
SE valor > saldo ENTÃO
ESCREVA("Saldo insuficiente!")
SENÃO
saldo ← saldo - valor
ESCREVA("Saque realizado! Novo saldo: R$ ", saldo)
FIMSE
CASO 3:
ESCREVA("Valor para depósito: ")
LEIA(valor)
saldo ← saldo + valor
ESCREVA("Depósito realizado! Novo saldo: R$ ", saldo)
CASO 0:
ESCREVA("Encerrando...")
CASO CONTRÁRIO:
ESCREVA("Opção inválida!")
FIMESCOLHA

ATÉ opcao = 0

FIM