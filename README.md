# calculadora
# CALCULADORA 

# HELLEN ANDRADE - 67001108  

import tkinter as tk 

 

def click(valor): 

    if valor == "=": 

        try: 

            entrada.delete(0, tk.END) 

            entrada.insert(tk.END, str(eval(entrada.get()))) 

        except: 

            entrada.delete(0, tk.END) 

            entrada.insert(tk.END, "Error") 

    elif valor == "C": 

        entrada.delete(0, tk.END) 

    else: 

        entrada.insert(tk.END, valor) 

 

ventana = tk.Tk() 

ventana.title("Calculadora") 

ventana.geometry("300x450") 

ventana.resizable(False, False) 

 

 

entrada = tk.Entry(ventana, font=("Arial", 20), justify="right") 

entrada.pack(fill="both", ipadx=8, ipady=8, pady=10) 

 

botones = [ 

    "7", "8", "9", "/", 

    "4", "5", "6", "*", 

    "1", "2", "3", "-", 

    "0", ".", "=", "+", 

    "C"    

] 

 

frame_botones = tk.Frame(ventana) 

frame_botones.pack() 

 

for i, texto in enumerate(botones): 

    fila = i // 4 

    columna = i % 4 

    tk.Button(frame_botones, text=texto, width=5, height=2, font=("Arial", 14), 

              command=lambda t=texto: click(t)).grid(row=fila, column=columna, padx=5, pady=5) 

 

ventana.mainloop() 

 
