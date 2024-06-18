# techTide
tech
import random
import string

def generate_password(length=12):
    # Створюємо список символів для генерації пароля
    characters = string.ascii_letters + string.digits + string.punctuation

    # Генеруємо пароль за вказаною довжиною
    password = ''.join(random.choice(characters) for _ in range(length))

    # Перевіряємо складність пароля
    strength = "Weak"
    if any(char.isdigit() for char in password) and any(char.isalpha() for char in password):
        strength = "Strong"
    
    return password, strength

# Викликаємо функцію для генерації пароля та визначення його складності
generated_password, password_strength = generate_password()
print(f"Generated Password: {generated_password}")
print(f"Password Strength: {password_strength}")
