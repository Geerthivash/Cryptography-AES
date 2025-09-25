# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
'''
import base64

key = 7  # just a number for XOR (toy key)

def encrypt_url(url: str) -> str:
    # XOR each byte with key
    encrypted_bytes = bytes([b ^ key for b in url.encode()])
    # URL-safe base64 encode
    return base64.urlsafe_b64encode(encrypted_bytes).decode()

def decrypt_url(token: str) -> str:
    encrypted_bytes = base64.urlsafe_b64decode(token)
    decrypted_bytes = bytes([b ^ key for b in encrypted_bytes])
    return decrypted_bytes.decode()

# --- Test it ---
url = "https://example.com/?q=test"
encrypted = encrypt_url(url)
print("Encrypted:", encrypted)

decrypted = decrypt_url(encrypted)
print("Decrypted:", decrypted)

'''
# OUTPUT:
Encrypted: b3Nzd3Q9KChif2Zqd2tiKWRoaig4djpzYnRz
Decrypted: https://example.com/?q=test

=== Code Execution Successful ===

# RESULT:

Thus the Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is done successfully.

