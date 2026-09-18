# SpeedMind
Um jogo para você fazer cálculos mentais, ainda está no ínicio, mas ja da pra brincar com as funcões iniciais.
import random
import time
#import sys

def sortear_numero(inicio, fim):
    return random.randint(inicio, fim)

def sortear_operacao():
    operacoes = ['+', '-', '*', '/']
    return random.choice(operacoes)

def jogar_rodada():
    #global num1, num2, operacao, pergunta, resultado_correto
    #global calcular_resultado

    num1 = sortear_numero(1, 100)
    num2 = sortear_numero(1, 100)
    operacao = sortear_operacao()
    #pergunta = print(f"\n{num1} {operacao} {num2}")

    def calcular_resultado(num1, num2, operacao):
        if operacao == '+':
            return num1 + num2
        elif operacao == '-':
            return num1 - num2
        elif operacao == '*':
            return num1 * num2
        elif operacao == '/':
            return num1 / num2


def aleatorio():

    num1 = sortear_numero(1, 100)
    num2 = sortear_numero(1, 100)
    operacao = sortear_operacao()
    pergunta = print(f"\n{num1} {operacao} {num2}")

    def calcular_resultado(num1, num2, operacao):
        if operacao == '+':
            return num1 + num2
        elif operacao == '-':
            return num1 - num2
        elif operacao == '*':
            return num1 * num2
        elif operacao == '/':
            return num1 / num2

    resultado_correto = calcular_resultado(num1, num2, operacao)
    global pontos, rodada
    pontos = 0
    rodadas = 0
    print(f"\n{pergunta} ")
    inicio = time.time()
    resposta = float(input("Digite sua resposta: "))

    while True:
        try:
            if resposta == resultado_correto:
                fim = time.time()
                tempo_total = fim - inicio
                print(f"Você levou {tempo_total:.2f} segundos para responder.")
                print("Parabéns! Você acertou!")
                pontos += 1
                rodadas += 1
                continuar = input("Deseja continuar jogando? (1/2): ").strip().lower()
                if continuar != '1':
                    return False
                else:
                    print(f"\n--- Fim de Jogo ---")
                    #print(f"Você acertou {pontos} de {rodadas} rodada(s)!") 
                    return True
            else:
                jogar_rodada()
                print(f"Que pena! A resposta correta era {resultado_correto}.")
                return False
        except ValueError:
            print("Por favor, digite um número válido.")

def configs():

    global resultado_correto

    num1 = sortear_numero(1, 100)
    num2 = sortear_numero(1, 100)
    operacao = sortear_operacao()
    #pergunta = {num1}, {operacao},{num2}

    def calcular_resultado(num1, num2, operacao):
        if operacao == '+':
            return num1 + num2
        elif operacao == '-':
            return num1 - num2
        elif operacao == '*':
            return num1 * num2
        elif operacao == '/':
            return num1 / num2

    resultado_correto = calcular_resultado(num1, num2, operacao)

    


    global operacoes2, rodada, vida, nums1, nums2
    nums1 = 0
    nums2 = 0
    soma = '+'
    sub = '-'
    multi = '*'
    div = '/'
    sort = 2
    rodada = 3
    vida = 4
    print(f"Escolha o que você quer mudar")
    print("Operações:1")
    print(f"Números máximo e minímo:2")
    print(f"Quantidade de rodadas: 3")
    print(f"Quantidade de vidas:4")
    config = input("Digite sua escolha:")
    if config == "1":
        print(f"soma = 1")
        print(f'sub = 2')
        print(f'multi = 3')
        print(f'div = 4')
        while True:
            oper = int(input(f"Qual operação?"))
            if oper == 1:                
                print(f"Calcule {num1} '+' {num2}")
                int(input(""))
                print(f"O resultado era: ")
                resultado1 = num1 + num2
                print(f"O resultado: {resultado1}")
                break
            elif oper == 2:
                print(f"Calcule {num1} '-' {num2}")
                int(input("?"))
                print(f"O resultado era: ")
                resultado2 = num1 - num2
                print(f"O resultado era: {resultado2} ")
                break
            elif oper == 3:
                print(f"Calcule {num1} '*' {num2}")
                int(input("?"))
                resultado3 = num1 * num2
                print(f"O resultado era: {resultado3} ")
                break
            elif oper == 4:
                print(f"Calcule {num1} '/' {num2}")
                int(input("?"))
                resultado4 = num1 - num2
                print(f"O resultado era: {resultado4} ")
                break
    if config == "2":
        nums1 = int(input(""))
        nums2 = int(input(""))
        sort(nums1, nums2)
        return random.randint(nums1, nums2)
        print(f"Calcule {nums1} {sortear_operacao} {nums2}")

    if config == "3":
        rodada
    if config == "4":
        vida



def main():
    pontos = 0
    rodadas = 0

    while True:
        print("=== Bem-vindo ao Speed Mind! ===")
        print("1:Modo aleatorio")
        print("2:Sair")
        print("3:configurações")
        escolha = input("Escolha:").strip().lower()
        if escolha == "1":
            print("Modo aleatorio selecionado")
            aleatorio()
        elif escolha == "2":
             break

        elif escolha == "3":
            configs()


if __name__ == "__main__":
    main()
