**def calculate():
    """
    Performs a basic mathematical operation based on user input.
    Asks for two numbers and an operation (+, -, *, /), then prints the result.
    Handles invalid input and division by zero.
    """
    print("Welcome to the Basic Calculator!")

    # Get the first number from the user
    while True:
        try:
            num1 = float(input("Enter the first number: "))
            break  # Exit loop if input is valid
        except ValueError:
            print("Invalid input. Please enter a valid number.")

    # Get the second number from the user
    while True:
        try:
            num2 = float(input("Enter the second number: "))
            break  # Exit loop if input is valid
        except ValueError:
            print("Invalid input. Please enter a valid number.")

    # Get the operation from the user
    while True:
        operation = input("Enter the operation (+, -, *, /): ").strip()
        if operation in ['+', '-', '*', '/']:
            break  # Exit loop if operation is valid
        else:
            print("Invalid operation. Please choose from +, -, *, /.")

    result = None
    equation = f"{num1} {operation} {num2}"

    # Perform the calculation based on the operation
    if operation == '+':
        result = num1 + num2
    elif operation == '-':
        result = num1 - num2
    elif operation == '*':
        result = num1 * num2
    elif operation == '/':
        if num2 == 0:
            print("Error: Division by zero is not allowed.")
            return # Exit the function if division by zero occurs
        else:
            result = num1 / num2

    # Print the result if a valid operation was performed
    if result is not None:
        # Format the result to avoid excessive decimal places for whole numbers
        if result == int(result):
            result_display = int(result)
        else:
            result_display = result
        print(f"{equation} = {result_display}")

# Call the function to run the calculator
calculate()
