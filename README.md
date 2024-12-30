def caesar_cipher(text, shift, mode): 

    result = "" 

    for char in text: 

        if char.isalpha(): 

            if mode == "encrypt": 

                shift_char = chr((ord(char) + shift - 65) % 26 + 65) 

            elif mode == "decrypt": 

                shift_char = chr((ord(char) - shift - 65) % 26 + 65) 

            result += shift_char 

        else: 

            result += char 

    return result 

 

# Get user input 
text = input("Enter the text: ") 

shift = int(input("Enter the shift value: ")) 

mode = input("Enter mode (encrypt/decrypt): ") 

 

# Call the function and print the result 

if mode == "encrypt": 

    encrypted_text = caesar_cipher(text, shift, mode) 

    print("Encrypted text:", encrypted_text) 

elif mode == "decrypt": 

    decrypted_text = caesar_cipher(text, shift, mode) 

    print("Decrypted text:", decrypted_text) 

else: 

    print("Invalid mode. Please enter 'encrypt' or 'decrypt'.") 
