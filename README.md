# PRODIGY_CS_01
Prodigy Cyber Security Internship - Task 1 - Implement Caesar Cipher

Create a Python program that can encrypt and decrypt text using the Caesar Cipher algorithm. Allow users to input a message and a shift value to perform encryption and decryption.

Here’s a simple Python program that uses the Caesar Cipher algorithm for encryption and decryption:

def caesar_cipher(text, shift, mode):
    result = ""
    for char in text:
        if char.isalpha():
            ascii_offset = ord('a') if char.islower() else ord('A')
            cipher_char = chr((ord(char) - ascii_offset + shift * mode) % 26 + ascii_offset)
            result += cipher_char
        else:
            result += char
    return result

def main():
    text = input("Enter the text: ")
    shift = int(input("Enter the shift value: "))
    mode = input("Choose mode - Encrypt (E) or Decrypt (D): ")

    if mode.lower() == 'e':
        print("Encrypted text: ", caesar_cipher(text, shift, 1))
    elif mode.lower() == 'd':
        print("Decrypted text: ", caesar_cipher(text, shift, -1))
    else:
        print("Invalid mode. Please choose 'E' for encryption or 'D' for decryption.")

if __name__ == "__main__":
    main()

In this program, the caesar_cipher function performs the encryption or decryption based on the mode parameter. If mode is 1, it encrypts the text; if mode is -1, it decrypts the text. The main function handles user input and output. It asks the user to enter the text, shift value, and mode 
(E for encryption, D for decryption). Then it calls the caesar_cipher function with the appropriate parameters and prints the result. If the user enters an invalid mode, it prints an error message. You can run this program in a Python environment.
