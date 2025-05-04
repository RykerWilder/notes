# Fake Data in Python
Image captcha generator using Python.

---

```python
from captcha.image import ImageCaptcha
from PIL import Image

#specify image size
image = ImageCaptcha(width=300, height=100)

#specify text for captcha
captcha_text = input("Enter Captcha text: ")

#generate the image of the given text
data = image.generate(captcha_text)

#write the image on the given file and save it
image.write(captcha_text, 'CAPTCHA.png')

Image.open('CAPTCHA.png')
```

---

### Requirements 

- Python 3.x
- captcha 
  ```bash
  pip install captcha
  ```
- Pillow
  ```bash
  pip install Pillow
  ```