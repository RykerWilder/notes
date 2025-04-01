# ROT13 Encryption

ROT13 ("rotate by 13 places") is a simple letter substitution cipher that replaces a letter with the 13th letter after it in the alphabet.

---

### Characteristics
- It's a special case of the Caesar cipher with a shift of 13.
- Works only on alphabetic characters (a-z, A-Z).
- Leaves numbers, symbols, and whitespace unchanged.
- It's its own inverse: the same function encodes and decodes.
- Provides essentially no cryptographic security (easily broken).

### How ROT13 Works

For each letter in the text:
1. Find its position in the alphabet (A=0, B=1, ..., Z=25).
2. Add 13 to this position (wrapping around after Z).
3. Find the letter corresponding to the new position.

Example:
- 'A' → (0 + 13) = 13 → 'N'
- 'n' → (13 + 13) = 26 → 26-26=0 → 'a'

## Security Note

ROT13 is not a secure encryption method! It's useful for:

- Obscuring text from casual viewing (spoilers, jokes, puzzles).
- Learning about basic cipher techniques.
- Simple text obfuscation.
**Never use ROT13 for sensitive data protection.**

## Why 13?

The alphabet has 26 letters, so rotating by 13 means applying the rotation twice returns the original text (13+13=26). This makes the same function usable for both encoding and decoding.

You can see the code to encrypt in ROT13 here! - **[ROT13](https://github.com/RykerWilder/rot13-encryption)**