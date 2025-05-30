# GCM - Galois/Counter Mode

*GCM (Galois/Counter Mode) is a modern mode for AES.

It provides:

    * Confidentiality (hides data like regular encryption),
    * Integrity (detects if someone tampered with the message).

✅ No padding needed — it works with variable-length messages.

[Gcm](AES/Gcm.java ':include :type=code')

| Term                           | Description                                                                                                       |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| **AES-GCM**                    | A mode of AES that offers both encryption and authentication.                                                     |
| **IV (Initialization Vector)** | A random value used once per encryption to ensure uniqueness. GCM uses a 12-byte IV.                              |
| **Tag**                        | Automatically generated during encryption and checked during decryption to verify data hasn’t been tampered with. |
| **NoPadding**                  | GCM works without padding! No need to manually add or strip bytes.                                                |


 ### What Is an Initialization Vector (IV)?

An `Initialization Vector (IV)` is a random or unique value used along with the encryption key to add randomness to the encryption process.
You can think of the IV as:

    A "starting point" for the encryption algorithm.

It ensures that:

   * Even if you encrypt the same data with the same key, the output will be different each time.

   * This makes it much harder for attackers to guess patterns in your data.