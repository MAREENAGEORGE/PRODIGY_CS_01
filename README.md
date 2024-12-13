def caesar_cipher(text, shift, mode):
    result = ""
    if mode == "decrypt":
        shift = -shift

    for char in text:
        if char.isalpha():
            start = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - start + shift) % 26 + start)
        else:
            result += char
    return result

message = input("Enter the message: ")
shift_value = int(input("Enter the shift value: "))
operation = input("Type 'encrypt' to encrypt or 'decrypt' to decrypt: ").lower()

output = caesar_cipher(message, shift_value, operation)
print(f"Result: {output}")
