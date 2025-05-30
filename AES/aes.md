# AES
`AES (Advanced Encryption Standard)` is a widely used symmetric encryption algorithm (same key is used to encrypt and decrypt). It transforms readable text (plaintext) into scrambled text (ciphertext) and back again using a secret key.
Key Concepts:

* `Secret Key:` Used to encrypt and decrypt the data.
* `Cipher:` A tool that performs encryption/decryption.
* `Base64:` Used to convert binary data into a readable string format.

# Usecase

* HTTPS (secure websites)
* File encryption (ZIP, PDF, etc.)
* Messaging apps (e.g., Signal, WhatsApp)
* Wi-Fi encryption (WPA2/WPA3)
* Cloud storage security

# Algorithm 

* ECB
* CBC
* [GCM - Galois/Counter Mode](AES/gcm.md)

| Mode    | [Padding](AES/padding.md)   | Integrity check?  | Notes                            |
| ------- | ---------  | ----------------- | -------------------------------- |
| ECB     | ✅        | ❌                | Weak — don't use.                |
| CBC     | ✅        | ❌                | Better, but needs padding & IV.  |
| GCM     | ❌        | ✅                | ✅ Recommended for modern use!   |

# [Padding](AES/padding.md)