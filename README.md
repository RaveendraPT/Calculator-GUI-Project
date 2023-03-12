# Calculator-GUI-Project
import tkinter as tk
import math

def get_numbers():
    N1 = float(N1_entry.get())
    N2 = float(N2_entry.get())
    return N1,N2

def add():
    N1, N2 = get_numbers()
    result_label.config(text=f"{N1} + {N2} = {N1+N2}")

def subtract():
    N1, N2 = get_numbers()
    result_label.config(text=f"{N1} - {N2} = {N1-N2}")

def multiply():
    N1, N2 = get_numbers()
    result_label.config(text=f"{N1} * {N2} = {N1*N2}")

def divide():
    N1, N2 = get_numbers()
    if N2 == 0:
        result_label.config(text="Error: division by zero")
    else:
        result_label.config(text=f"{N1} / {N2} = {N1/N2}")

def square():
    N1 = float(N1_entry.get())
    result_label.config(text=f"{N1}^2 = {N1**2}")

def square_root():
    N1 = float(N1_entry.get())
    if N1 < 0:
        result_label.config(text="Error: square root of negative number")
    else:
        result_label.config(text=f"sqrt({N1}) = {math.sqrt(N1)}")

def reset():
    N1_entry.delete(0, tk.END)
    N2_entry.delete(0, tk.END)
    result_label.config(text="")

def quit_program():
    window.destroy()

# create the main window
window = tk.Tk()
window.title("Calculator")

# create the input fields and labels
N1_label = tk.Label(window, text="Enter the first number:")
N1_label.pack()
N1_entry = tk.Entry(window)
N1_entry.pack()

N2_label = tk.Label(window, text="Enter the second number:")
N2_label.pack()
N2_entry = tk.Entry(window)
N2_entry.pack()

# create the buttons
add_button = tk.Button(window, text="Add", command=add)
add_button.pack()

subtract_button = tk.Button(window, text="Subtract", command=subtract)
subtract_button.pack()

multiply_button = tk.Button(window, text="Multiply", command=multiply)
multiply_button.pack()

divide_button = tk.Button(window, text="Divide", command=divide)
divide_button.pack()

square_button = tk.Button(window, text="Square", command=square)
square_button.pack()

square_root_button = tk.Button(window, text="Square Root", command=square_root)
square_root_button.pack()

reset_button = tk.Button(window, text="Reset", command=reset)
reset_button.pack()

quit_button = tk.Button(window, text="Quit", command=quit_program)
quit_button.pack()

# create the result label
result_label = tk.Label(window, text="")
result_label.pack()

# start the main loop
window.mainloop()
