# Caesar Cipher with Secret Key + Salt

An extension of the classic Caesar Cipher that improves security by introducing a **secret numeric key** and a **random salt**.

---

### What is it?
Improved version of the Caesar cipher:

- **Secret key**: A number (`key`) that determines the base shift.
- **Salt**: A random string that dynamically changes the shift for each character.
- **Result**: The encryption becomes less predictable and more resistant to simple attacks.

---

### How does it work?
1. **Input**:
- `plaintext`: Text to encrypt (e.g. `"HELLO"`).
- `key`: Secret number (e.g. `5`).
- `salt`: Random string (e.g. `"XQ3"`).

2. **Encryption process**:
- For each character in `plaintext`:
- A **dynamic shift** is calculated:
```
shift = (key + current_ASCII_value_of_salt) % 26
```
- Shift is applied to the character (with alphabetic rewind).

3. **Example**:
- `plaintext = "HELLO"`, `key = 5`, `salt = "XQ3"` (ASCII values: `X=88`, `Q=81`, `3=51`).
- Calculated shifts:
```
H → (5 + 88) % 26 = 15 → W
E → (5 + 81) % 26 = 8 → M
L → (5 + 51) % 26 = 4 → P
L → (5 + 88) % 26 = 15 → A
O → (5 + 81) % 26 = 8 → W
```
- **Ciphertext**: `"WMPAW"`.

---

### Decryption
To decrypt, use the inverse formula:

```python
decrypted_char = (encrypted_char - key - salt_val) % 26
```

You can see the code to encrypt in Ceasar Salt here! - **[Ceasar Salt](https://github.com/RykerWilder/ceasar-salt-encryption)**