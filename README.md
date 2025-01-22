import tkinter as tk
from tkinter import messagebox

def add():
    try:
        num1 = float(entry1.get())
        num2 = float(entry2.get())
        result.set(num1 + num2)
    except ValueError:
        messagebox.showerror("Invalid Input", "Please enter valid numbers")

def subtract():
    try:
        num1 = float(entry1.get())
        num2 = float(entry2.get())
        result.set(num1 - num2)
    except ValueError:
        messagebox.showerror("Invalid Input", "Please enter valid numbers")

def multiply():
    try:
        num1 = float(entry1.get())
        num2 = float(entry2.get())
        result.set(num1 * num2)
    except ValueError:
        messagebox.showerror("Invalid Input", "Please enter valid numbers")

def divide():
    try:
        num1 = float(entry1.get())
        num2 = float(entry2.get())
        if num2 == 0:
            messagebox.showerror("Math Error", "Division by zero is not allowed")
        else:
            result.set(num1 / num2)
    except ValueError:
        messagebox.showerror("Invalid Input", "Please enter valid numbers")

# Create the main window
root = tk.Tk()
root.title("Simple Calculator")

# Create input fields and labels
label1 = tk.Label(root, text="Enter first number:")
label1.grid(row=0, column=0, padx=10, pady=5)
entry1 = tk.Entry(root)
entry1.grid(row=0, column=1, padx=10, pady=5)

label2 = tk.Label(root, text="Enter second number:")
label2.grid(row=1, column=0, padx=10, pady=5)
entry2 = tk.Entry(root)
entry2.grid(row=1, column=1, padx=10, pady=5)

# Result display
result = tk.StringVar()
result_label = tk.Label(root, text="Result:")
result_label.grid(row=2, column=0, padx=10, pady=5)
result_entry = tk.Entry(root, textvariable=result, state="readonly")
result_entry.grid(row=2, column=1, padx=10, pady=5)

# Buttons for operations
add_button = tk.Button(root, text="Add", command=add)
add_button.grid(row=3, column=0, padx=10, pady=5)

subtract_button = tk.Button(root, text="Subtract", command=subtract)
subtract_button.grid(row=3, column=1, padx=10, pady=5)

multiply_button = tk.Button(root, text="Multiply", command=multiply)
multiply_button.grid(row=4, column=0, padx=10, pady=5)

divide_button = tk.Button(root, text="Divide", command=divide)
divide_button.grid(row=4, column=1, padx=10, pady=5)

# Run the application
root.mainloop()
