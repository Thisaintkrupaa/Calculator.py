# Calculator.py


import os

# Function to handle user input for numbers
def get_number_input(prompt):
    while True:
        try:
            num = float(input(prompt))
            return num
        except ValueError:
            print("Invalid input. Please enter a number.")

# Function to handle user input for operator
def get_operator_input(prompt):
    while True:
        operator = input(prompt)
        if operator in ['+', '-', '*', '/']:
            return operator
        else:
            print("Invalid operator. Please enter one of the following: +, -, *, /")

# Function to perform calculation based on numbers and operator

def calculate(num1, num2, operator):
    if operator == '+':
        result = num1 + num2
    elif operator == '-':
        result = num1 - num2
    elif operator == '*':
        result = num1 * num2
    elif operator == '/':
        if num2 == 0:
            print("Error: Division by zero")
            return None
        else:
            result = num1 / num2
    return result

# Function to write equation and result to a file
def write_equation_to_file(num1, num2, operator, result):
    with open('equations.txt', 'a') as f:
        f.write(f"{num1} {operator} {num2} = {result}\n")

# Function to read equations from a file and print them out
def read_equations_from_file(filename):
    try:
        with open(filename, 'r') as f:
            equations = f.read()
            print(equations)
    except FileNotFoundError:
        print("File not found. Please enter a valid file name.")
        read_equations_from_file()

# Function to handle user input for whether to enter new equation or read from file
def main():
    while True:
        choice = input("Would you like to enter a new equation (1) or read equations from a file (2)? ")
        if choice == '1':
            num1 = get_number_input("Enter the first number: ")
            num2 = get_number_input("Enter the second number: ")
            operator = get_operator_input("Enter the operator (+, -, *, /): ")
            result = calculate(num1, num2, operator)
            print(f"{num1} {operator} {num2} = {result}")
            write_equation_to_file(num1, num2, operator, result)
            break
        elif choice == '2':
            filename = input("Enter the file name: ")
            read_equations_from_file(filename)
            break
        else:
            print("Invalid choice. Please enter either 1 or 2.")

if __name__ == "__main__":
    main()


#extended version

import os

# Function to handle user input for numbers
def get_number_input(prompt):
    while True:
        try:
            num = float(input(prompt))
            return num
        except ValueError:
            print("Invalid input. Please enter a number.")

# Function to handle user input for operator
def get_operator_input(prompt):
    while True:
        operator = input(prompt)
        if operator in ['+', '-', '*', '/']:
            return operator
        else:
            print("Invalid operator. Please enter one of the following: +, -, *, /")

# Function to perform calculation based on numbers and operator
def calculate(num1, num2, operator):
    if operator == '+':
        result = num1 + num2
    elif operator == '-':
        result = num1 - num2
    elif operator == '*':
        result = num1 * num2
    elif operator == '/':
        if num2 == 0:
            print("Error: Division by zero")
            return None
        else:
            result = num1 / num2
    return result

# Function to write equation and result to a file
def write_equation_to_file(num1, num2, operator, result):
    with open('equations.txt', 'a') as f:
        f.write(f"{num1} {operator} {num2} = {result}\n")

# Function to read equations from a file and print them out
def read_equations_from_file(filename):
    try:
        with open(filename, 'r') as f:
            equations = f.read()
            print(equations)
    except FileNotFoundError:
        print("File not found. Please enter a valid file name.")
        read_equations()

# Function to handle user input for whether to enter new equation or read from file
def main():
    while True:
        choice = input("Would you like to enter a new equation (1) or read equations from a file (2)? ")
        if choice == '1':
            num1 = get_number_input("Enter the first number: ")
            num2 = get_number_input("Enter the second number: ")
            operator = get_operator_input("Enter the operator (+, -, *, /): ")
            result = calculate(num1, num2, operator)
            print(f"{num1} {operator} {num2} = {result}")
            write_equation_to_file(num1, num2, operator, result)
            break
        elif choice == '2':
            filename = input("Enter the file name: ")
            read_equations_from_file(filename)
            break
        else:
            print("Invalid choice. Please enter either 1 or 2.")

if __name__ == "__main__":
    main()
