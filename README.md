[code_1.py](https://github.com/user-attachments/files/32579810/code_1.py)

import random
import time
#import sys

CONFIGS = {
    "num_min": 1,
    "num_max": 100,
    "vidas": 3,
    "operacoes": ['+', '-', '*' '/']
}

def sortear_numero(inicio, fim):
    return random.randint(inicio, fim)

def sortear_operacao():
    operacoes = ['+', '-', '*', '/']
    return random.choice(operacoes)

def calcular_resultado(num1, num2, operacao):
    if operacao == '+':
        return num1 + num2
    elif operacao == '-':
        return num1 - num2
    elif operacao == '*':
        return num1 * num2
    elif operacao == '/':
        return round(num1 / num2, 2)


def jogar_rodada():
    num1 = random.randint(1,100)
    num2 = random.randint(1,100)
    operacao = sortear_operacao()
    resultado_correto = calcular_resultado(num1, num2, operacao)

    print(f"calcule: {num1}, {operacao}, {num2}")

    try:
        inicio = time.time()
        resposta = float(input())
        fim = time.time()
        tempo_total = fim - inicio

        if resposta == resultado_correto:
            print(f"Você acertou em {tempo_total:.2f} segundos.")
            return True
        else:
            print(f"Você errou a resposta era {resultado_correto}")
            return False
    except ValueError:
        print("Digite algo válido!")
        return False

def modo_aleatorio():
    rodadas = 0
    pontos = 0

    while True:
        rodadas +=1
        acertou = jogar_rodada()
        if acertou:
            pontos +=1
        continuar = input("\nDeseja continuar jogando? 1-sim / 2-Não").strip()
        if continuar != '1':
            print(f"\n--- Fim de jogo---")
            print(f"Você acertou {pontos} de {rodadas} rodada(s)!")
            break


def configs():

    global resultado_correto
    global operacoes2, rodada, vida, nums1, nums2
    nums1 = 0
    nums2 = 0
    soma = '+'
    sub = '-'
    multi = '*'
    div = '/'
#    print(f"Números máximo e minímo:2")
 #   print(f"Quantidade de rodadas: 3")
  #  print(f"Quantidade de vidas:4")

    print(f"soma = 1")
    print(f'sub = 2')
    print(f'multi = 3')
    print(f'div = 4')
    oper = int(input(f"Qual operação?"))    

    while True:
            num1 = sortear_numero(1, 100)
            num2 = sortear_numero(1, 100)
            if oper == 1:
                inicio = time.time()     
                print(f"Calcule {num1} '+' {num2}")
                resultado1 = int(input(""))
                fim = time.time()
                if resultado1 == num1 + num2:
                    print(f"Certo, isso em {fim - inicio}")
                else:
                    print("Errado")
                repetir = int(input(f"Deseja continuar? Digite:1 "))
                if repetir != 1:
                    return True

            elif oper == 2:
                inicio = time.time()     
                print(f"Calcule {num1} '-' {num2}")
                resultado1 = int(input(""))
                fim = time.time()
                if resultado1 == num1 - num2:
                    print(f"Certo, isso em {fim - inicio}")
                else:
                    print("Errado")
                repetir = int(input(f"Deseja continuar? Digite:1 "))
                if repetir != 1:
                    return True

            elif oper == 3:
                inicio = time.time()     
                print(f"Calcule {num1} '*' {num2}")
                resultado1 = int(input(""))
                fim = time.time()
                if resultado1 == num1 * num2:

                    print(f"Certo, isso em {fim - inicio}")
                else:
                    print("Errado")
                repetir = int(input(f"Deseja continuar? Digite:1 "))
                if repetir != 1:
                    return True

            elif oper == 4:
                inicio = time.time()     
                print(f"Calcule {num1} '/' {num2}")
                resultado1 = float(input(""))
                fim = time.time()
                if resultado1 == round(num1 / num2, 2):
                    
                    print(f"Certo, isso em {fim - inicio}")
                else:
                    print("Errado")
                    print(f"{round(num1 / num2, 1)}")
                repetir = int(input(f"Deseja continuar? Digite:1 "))
                if repetir != 1:
                    return True

#    if config == "2":
        #nums1 = int(input(""))
        #nums2 = int(input(""))
        #sort(nums1, nums2)
        #return random.randint(nums1, nums2)
        #print(f"Calcule {nums1} {sortear_operacao} {nums2}")


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
            modo_aleatorio()
        elif escolha == "2":
             break

        elif escolha == "3":
            configs()


if __name__ == "__main__":
    main()
