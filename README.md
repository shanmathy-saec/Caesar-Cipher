def caesar_cipher(text, shift, mode='encrypt'):
    if mode == 'decrypt':
        shift = -shift

    result = ""
    for char in text:
        if char.isalpha(): 
            base = ord('A') if char.isupper() else ord('a')
            
            new_char = chr((ord(char) - base + shift) % 26 + base)
            result += new_char
        else:
            
            result += char

    return result

if __name__ == "__main__":
    print("Welcome to the Caesar Cipher Tool!")
    while True:
        mode = input("Do you want to encrypt or decrypt a message? (enter 'encrypt' or 'decrypt'): ").strip().lower()
        if mode not in ['encrypt', 'decrypt']:
            print("Invalid option. Please enter 'encrypt' or 'decrypt'.")
            continue

        text = input("Enter your message: ").strip()
        try:
            shift = int(input("Enter the shift value (integer): "))
        except ValueError:
            print("Shift value must be an integer. Try again.")
            continue

        
        result = caesar_cipher(text, shift, mode)
        print(f"The resulting message is: {result}")

        
        again = input("Do you want to process another message? (yes/no): ").strip().lower()
        if again != 'yes':
            print("Goodbye!")
            break
