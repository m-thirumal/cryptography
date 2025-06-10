# cryptography

## [Mathematics](Mathematics/mathematics.md)

## Definition:

* [Repudiation]  - denial of the truth or validity of something.
* Non-reudiation - Can't deny

## Symmetric and Asymmetric Encryption

* `Symmetric key algorithm` - uses same key to encrypt & decrypt data
    * [AES](AES/aes.md)
        * [GCM - Galois/Counter Mode](AES/gcm.md)
* `Asymmetric` - uses public key to encrypt & private key to descrypt data
    * [RSA](RSA/rsa.md)
    * ECC - Elliptic Curve Cryptography
    * [ECDH - Elliptic Curve Diffie-Hellman](ECDH/ecdh.md)


## Building blocks

* Cryptographic Hash Functions - take an input (or message) and produce a fixed-size string of bytes. They are designed to be fast and to produce a unique hash value for each unique input.
* Secure Hash Algorithm (SHA)
* Message Digest Algorithm 5 (MD5)
* Message Authentication Code (MAC)
* Hashed Message Authentication Code (HMAC)
* [Advanced Encryption Standard (AES)](AES/aes.md)
* Block encryption operating models
* Authenticated encryption
* [RSA public key cryptosystem](RSA/rsa.md)
* Elliptic curve public key cryptosystem
* Diffie-Helman key exchange
* X.509 digital certificates
* Certificate authorities and public key infrastructure

## Cryptographic Protocols

* `Secure Sockets Layer (SSL) / Transport Layer Security (TLS)` -  designed to provide secure communication over a computer network. They use a combination of symmetric-key and asymmetric-key algorithms to ensure data confidentiality and integrity.
* `Pretty Good Privacy (PGP)` - PGP is a data encryption and decryption program that provides cryptographic privacy and authentication. It uses a combination of symmetric-key and asymmetric-key algorithms to secure emails and files.
* `Digital Signatures` - provide a way to verify the authenticity and integrity of a message. They use asymmetric-key algorithms to create a unique signature that can be verified by anyone with the sender’s public key.

## Applications/Usecases of Cryptography

* Secure Communication
* Data Protection
* Authentication
* Digital Signatures
* Blockchain and Cryptocurrencies

## Cryptographic Challenges and Future Directions

* Quantum Computing - Quantum computers can solve certain mathematical problems much faster than classical computers, potentially breaking widely used algorithms like RSA and ECC.

* Efficient Algorithms

* Privacy-Preserving Cryptography