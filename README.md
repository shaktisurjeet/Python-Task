def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error! Division by zero."
    return x / y

def calculator():
    print("Simple CLI Calculator")
    print("Select operation:")
    print("1. Add (+)")
    print("2. Subtract (-)")
    print("3. Multiply (*)")
    print("4. Divide (/)")

    while True:
        choice = input("Enter choice (1/2/3/4 or + - * /): ").strip()

        if choice in ('1', '2', '3', '4', '+', '-', '*', '/'):
            try:
                num1 = float(input("Enter first number: "))
                num2 = float(input("Enter second number: "))
            except ValueError:
                print("Invalid input! Please enter numbers.")
                continue

            if choice in ('1', '+'):
                print(f"Result: {add(num1, num2)}")
            elif choice in ('2', '-'):
                print(f"Result: {subtract(num1, num2)}")
            elif choice in ('3', '*'):
                print(f"Result: {multiply(num1, num2)}")
            elif choice in ('4', '/'):
                print(f"Result: {divide(num1, num2)}")
        else:
            print("Invalid choice! Please select a valid operation.")

        next_calc = input("Do you want to perform another calculation? (yes/no): ").lower()
        if next_calc not in ('yes', 'y'):
            print("Thanks for using the calculator. Goodbye!")
            break

if __name__ == "__main__":
    calculator()

