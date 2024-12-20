***
import random
import string
def generator_password():
    print("\n--- Password Generator ---")
    try:
        length=int(input('enter the desired password length (minimum 6):'))
        if length < 6:
            print('Password must be at least 6 characters')
            return
        print('Select the character types to include:')
        include_uppercase=input('include uppercase letters?(y/n):').lower()=="y"
        include_lowercase=input('include lowercase letters?(y/n):').lower()=="y"
        include_digits=input('include digits?(y/n):').lower()=="y"
        include_symbols=input('include symbols?(y/n):').lower()=="y"
        if not (include_uppercase or include_lowercase or include_digits or include_symbols):
            print('you must select atleast one character type!')
            return
        character_pool=""
        if include_uppercase:
            character_pool=string.ascii_uppercase
        if include_lowercase:
            character_pool=string.ascii_lowercase
        if include_digits:
            character_pool=string.digits
        if include_symbols:
            chatacter_pool=string.punctuation
        password="".join(random.choice(character_pool) for _ in range(length))
        print(f'\nGenerated password:{password}')
    except ValueError:
        print("invalid input!please enter a valid number")
while True:
    generator_password()
    repeat=input("\nDo you want to generate another password?(y/n):").lower()
    if repeat !="y":
        print('exiting password generator. Stay secure!')
        break
        ***
        --- Password Generator ---
enter the desired password length (minimum 6):8
Select the character types to include:
include uppercase letters?(y/n):1
include lowercase letters?(y/n):&
include digits?(y/n):e
include symbols?(y/n):)
you must select atleast one character type!

Do you want to generate another password?(y/n):y

--- Password Generator ---
