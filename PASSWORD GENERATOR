import random
import string

def get_user_preferences():
    """
    Collects the user's input for password length and character preferences.
    Returns:
        length (int): Desired length of the password.
        use_lower (bool): Include lowercase letters.
        use_upper (bool): Include uppercase letters.
        use_digits (bool): Include digits.
        use_symbols (bool): Include special characters.
    """
    print("Welcome to the Password Generator!\n")

    # Get password length from the user
    while True:
        try:
            length = int(input("Enter desired password length (e.g., 8, 12, 16): "))
            if length < 4:
                print("⚠️ Password should be at least 4 characters long.")
            else:
                break
        except ValueError:
            print("❌ Please enter a valid number.")

    # Ask for complexity preferences
    use_lower = input("Include lowercase letters? (y/n): ").lower() == 'y'
    use_upper = input("Include uppercase letters? (y/n): ").lower() == 'y'
    use_digits = input("Include digits? (y/n): ").lower() == 'y'
    use_symbols = input("Include special characters? (y/n): ").lower() == 'y'

    return length, use_lower, use_upper, use_digits, use_symbols

def generate_password(length, use_lower, use_upper, use_digits, use_symbols):
    """
    Generates a password based on user preferences.
    Returns:
        password (str): The generated password.
    """
    character_pool = ""

    # Add character types based on user preferences
    if use_lower:
        character_pool += string.ascii_lowercase
    if use_upper:
        character_pool += string.ascii_uppercase
    if use_digits:
        character_pool += string.digits
    if use_symbols:
        character_pool += string.punctuation

    if not character_pool:
        return "⚠️ You must select at least one character type!"

    # Generate a password using random choices from the pool
    password = ''.join(random.choice(character_pool) for _ in range(length))
    return password

def main():
    # Get user preferences
    length, use_lower, use_upper, use_digits, use_symbols = get_user_preferences()

    # Generate password
    password = generate_password(length, use_lower, use_upper, use_digits, use_symbols)

    # Display the password
    print("\n🔐 Your Generated Password:")
    print(password)

# Run the program
if __name__ == "__main__":
    main()
