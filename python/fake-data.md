# Fake Data in Python
How to create fake data in python.

---

```python
from  faker import Faker

fake = Faker('it_IT', 'en_US', 'ja_JP')

print(fake.name())
print(fake.address())
print(fake.text())
print(fake.email())
print(fake.country())
print(fake.latitude(), fake.longitude())
print(fake.url())
```

---

### Requirements 

- Python 3.x
- Faker 
  ```bash
  pip install Faker
  ```
