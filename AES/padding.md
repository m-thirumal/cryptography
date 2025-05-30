# Padding

AES is a `block cipher`, which means it encrypts data in `fixed-size` blocks — typically 16 bytes (128 bits) at a time.

### But what if your input message isn’t exactly 16 bytes?

👉 Padding is a technique to fill in the extra space so the message becomes a multiple of 16 bytes.

#### ✅ With Padding (PKCS5/PKCS7 Example)

Let’s say you’re encrypting the string "HELLO" (5 bytes), and AES needs a 16-byte block.

`PKCS5/PKCS7` padding will add extra bytes to fill the gap:

```
Original:  H  E  L  L  O
Bytes:     72 69 76 76 79

Padding needed: 11 bytes
Each padding byte will be: 0x0B (11 in decimal)

Final padded block: [HELLO][0B 0B 0B 0B 0B 0B 0B 0B 0B 0B 0B]
```
#### 🧼 How Padding Is Removed

When you decrypt the message, the system sees the last byte 0B (11), and knows:

    "Ah, the last 11 bytes are padding — remove them."

So you get back just "HELLO".