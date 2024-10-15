def caesar(text, shift, mode):
    shift *= 1 if mode == 'e' else -1
    return ''.join(
        chr((ord(c) + shift - (65 if c.isupper() else 97)) % 26 + (65 if c.isupper() else 97)) if c.isalpha() else c
        for c in text
    )

text = input("Message: ")
shift = int(input("Shift: "))
mode = input("(e)ncrypt or (d)ecrypt: ").lower()

print(caesar(text, shift, mode))
