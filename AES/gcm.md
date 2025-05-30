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

### 🧠 Why Do We Need IVs?

Let’s say you’re encrypting the word "HELLO" multiple times using the same key:

    Without an IV: the encrypted result will always be the same — predictable! ❌

    With an IV: the encrypted result is different every time — secure! ✅

This is especially important in modes like CBC or GCM where encryption depends on the previous block or a counter.

### 🔐 IV in AES-GCM (our example)

GCM requires a 12-byte IV (recommended).

We generate it randomly:
```java
byte[] iv = new byte[12]; // 12 bytes = 96 bits
new SecureRandom().nextBytes(iv); // fills it with random bytes
```
It must be passed along with the encrypted data so it can be used during decryption.

The IV itself is not secret, but it must be unique every time you encrypt.

| Rule                                       | Why It Matters                                                |
| ------------------------------------------ | ------------------------------------------------------------- |
| **Must be random or unique**               | To prevent repeatable outputs.                                |
| **Must be the same for encrypt & decrypt** | Or the data won’t decrypt properly.                           |
| **Should never be reused with same key**   | Especially in modes like GCM or CBC, this can break security. |

### 📤 How to Store or Transmit IV

Since IV is needed for decryption, it's usually:

    Stored with the encrypted data (e.g., IV + ciphertext)

    Or sent alongside it

For example, you can combine them:

``` java
byte[] output = ByteBuffer.allocate(iv.length + ciphertext.length)
                          .put(iv)
                          .put(ciphertext)
                          .array();
```

| Term                 | What it is                                               | Needed for                                       |
| -------------------- | -------------------------------------------------------- | ------------------------------------------------ |
| **IV**               | A random starting value for encryption                   | Secure encryption in block modes like GCM or CBC |
| **Not a key**        | IV is public; the key is secret                          | Keep key secret, IV can be stored/transmitted    |
| **Random each time** | Same message + same key still gives different ciphertext | Prevents pattern attacks                         |
