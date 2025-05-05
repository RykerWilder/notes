# Generate OTP (One Time Password) in Python
How to generate OTP in python.

---

```python
import secrets

def generate_otp(length=6):
    return ''.join(str(secrets.randbelow(10))
    for _ in range(length))

print("Generated OTP: ", generate_otp())
```

---

### Requirements 

- Python 3.x