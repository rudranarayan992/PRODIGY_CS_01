# PRODIGY_CS_01
Task-01: Implement Caesar Cipher This repository contains a Python implementation of the Caesar Cipher algorithm for both encryption and decryption. Users can input any text message along with a shift value to see the transformed output. This project is a part of the PRODIGY Cyber Security Internship tasks.

# PRODIY_CS_01

## 🔐 Task-01: Implement Caesar Cipher

This repository contains a simple Python implementation of the Caesar Cipher, a classic encryption technique where each letter in the plaintext is shifted by a fixed number of positions.

---

## 🧠 What is Caesar Cipher?

The Caesar Cipher is one of the earliest known encryption techniques. It works by shifting each letter in a message by a set number of positions down the alphabet.

---

## 🚀 How to Use

1. Run the[caesar_cipher.py](https://github.com/rudranarayan992/PRODIGY_CS_01/commit/ed0ed6dfc31632ba3d9d9c17e3c455d2d72adc8a#diff-5408e2413fab80eb5f85a26579b3b52fe98ffef1085969666f3b07faf74a6a6a)

2. Choose whether to encrypt or decrypt.
3. Input your message.
4. Enter a shift value.


---

## 🛠️ Requirements
- Python 3

To run the script:
```bash
def caesar_encrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            start = ord('A') if char.isupper() else ord('a')
            # Shift character and wrap around the alphabet
            result += chr((ord(char) - start + shift) % 26 + start)
        else:
            result += char  # Keep non-alphabet characters unchanged
    return result

def caesar_decrypt(text, shift):
    return caesar_encrypt(text, -shift)

def main():
    print("=== Caesar Cipher Program ===")
    choice = input("Do you want to (E)ncrypt or (D)ecrypt? ").strip().upper()
    
    if choice not in ['E', 'D']:
        print("Invalid choice. Please enter 'E' for encryption or 'D' for decryption.")
        return

    message = input("Enter your message: ")
    try:
        shift = int(input("Enter shift value (integer): "))
    except ValueError:
        print("Shift must be an integer.")
        return

    if choice == 'E':
        encrypted = caesar_encrypt(message, shift)
        print("Encrypted message:", encrypted)
    else:
        decrypted = caesar_decrypt(message, shift)
        print("Decrypted message:", decrypted)

if __name__ == "__main__":
    main()


  
