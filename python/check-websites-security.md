```python
import certifi
import requests

def is_secure_website(url):
    try:
        # Aggiunge 'https://' se non presente (ma meglio gestire l'input)
        if not url.startswith(('http://', 'https://')):
            url = 'https://' + url
            
        response = requests.get(url, verify=certifi.where(), timeout=5)
        response.raise_for_status()
        return response.url.startswith('https://')
    except requests.exceptions.RequestException:
        return False

if __name__ == "__main__":
    website_url = input('Enter the website URL: ').strip()
    
    if is_secure_website(website_url):
        print(f'{website_url} is a secure website.')
    else:
        print(f'{website_url} is not a secure website or is unreachable.')
```

