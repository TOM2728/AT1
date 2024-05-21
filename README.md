import tkinter as tk
import random

def is_prime(n):
    if n <= 1:
        return False
    if n <= 3:
        return True
    if n % 2 == 0 or n % 3 == 0:
        return False
    i = 5
    while i * i <= n:
        if n % i == 0 or n % (i + 2) == 0:
            return False
        i += 6
    return True

def sortear():
    numero1 = random.randint(1, 100)
    while not is_prime(numero1):
        numero1 = random.randint(1, 100)
    
    numero2 = random.randint(1, 100)
    while not is_prime(numero2):
        numero2 = random.randint(1, 100)
    
    numero1_label.config(text=f"Número 1: {numero1}")
    numero2_label.config(text=f"Número 2: {numero2}")
    soma_label.config(text=f"Soma: {numero1 + numero2}")

# Criando a janela
janela = tk.Tk()
janela.title("Sorteio de Números Primos e Cálculo")
janela.geometry('300x150')

# Elementos da interface
numero1_label = tk.Label(janela, text="")
numero1_label.pack()

numero2_label = tk.Label(janela, text="")
numero2_label.pack()

soma_label = tk.Label(janela, text="")
soma_label.pack()

sortear_button = tk.Button(janela, text="Sortear", command=sortear)
sortear_button.pack()

# Loop principal
janela.mainloop()
