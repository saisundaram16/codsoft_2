#Password_Generator
import random
import string

def generate_password(length, use_uppercase, use_lowercase, use_numbers):
   
    characters = ""
    
    
    if use_uppercase:
        characters += string.ascii_uppercase
    if use_lowercase:
        characters += string.ascii_lowercase
    if use_numbers:
        characters += string.digits
    
    
    if not characters:
        characters = string.ascii_lowercase
        print("No options selected, defaulting to lowercase letters only.")
    
    
    password = ""
    for _ in range(length):
        password += random.choice(characters)
    
    return password

print("Welcome to the Random Password Generator!")


while True:
    try:
        length = int(input("Enter the desired length of the password: "))
        if length <= 0:
            print("Please enter a positive number!")
            continue
        break
    except ValueError:
        print("Please enter a valid number!")


use_uppercase = input("Include uppercase letters? (y/n): ").lower() == 'y'
use_lowercase = input("Include lowercase letters? (y/n): ").lower() == 'y'
use_numbers = input("Include numbers? (y/n): ").lower() == 'y'


password = generate_password(length, use_uppercase, use_lowercase, use_numbers)
print(f"Generated Password: {password}")
