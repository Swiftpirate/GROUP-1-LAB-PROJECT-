# Simple Calculator in Python

def calculator():
    print("Simple Calculator")
    print("Enter 'quit' to exit")
    
    while True:
        # Get user input
        print("\n" + "-" * 30)
        expr = input("Enter expression (e.g., 5 + 3): ").strip()
        
        if expr.lower() == 'quit':
            print("Goodbye!")
            break
        
        try:
            # Safely evaluate the expression
            # Only allow numbers and basic operators
            allowed_chars = set('0123456789+-*/(). ')
            if not all(c in allowed_chars for c in expr):
                print("Error: Invalid characters. Use only numbers and operators (+, -, *, /)")
                continue
                
            result = eval(expr)
            print(f"Result: {result}")
            
        except ZeroDivisionError:
            print("Error: Cannot divide by zero!")
        except SyntaxError:
            print("Error: Invalid expression syntax!")
        except Exception as e:
            print(f"Error: {e}")

# Run the calculator
if __name__ == "__main__":
    calculator()# GROUP-1-LAB-PROJECT-
