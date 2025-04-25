import random
import string

ADJECTIVES = ("Cool", "Happy", "Lazy", "Brave", "Smart", "Funky", "Witty", "Wild", "Silly", "Chill")
NOUNS = ("Tiger", "Panda", "Unicorn", "Wizard", "Ninja", "Pirate", "Dragon", "Robot", "Knight", "Phoenix")

def generate_username(include_number=True, include_special=True, length=0):
    parts = [random.choice(ADJECTIVES), random.choice(NOUNS)]
    if include_number:
        parts.append(f"{random.randint(0, 999):03d}")
    if include_special:
        parts.append(random.choice(string.punctuation))
    username = "".join(parts)
    if length > 0:
        username = username[:length]
    return username

def get_boolean_input(prompt):
    while True:
        user_input = input(prompt + " (yes/no): ").strip().lower()
        if user_input in ('y', 'yes'):
            return True
        if user_input in ('n', 'no'):
            return False
        print("Please enter 'y' or 'n'.")

def get_integer_input(prompt):
    while True:
        try:
            user_input = int(input(prompt))
            if user_input >= 0:
                return user_input
            print("Please enter a non-negative integer.")
        except ValueError:
            print("Invalid input. Please enter a valid integer.")

def main():
    print("Welcome to the Random Username Generator!")
    while True:
        try:
            count = int(input("How many usernames do you want to generate? "))
            if count > 0:
                break
            print("Please enter a positive integer.")
        except ValueError:
            print("Invalid input. Please enter a valid integer.")

    include_number = get_boolean_input("Include numbers in usernames?")
    include_special = get_boolean_input("Include special characters in usernames?")
    username_length = get_integer_input("Enter the maximum length of the username (0 for no limit): ")

    print("\nGenerating usernames...\n")
    usernames = []
    for _ in range(count):
        username = generate_username(include_number, include_special, username_length)
        usernames.append(username)
        print(username)

    save_to_file = get_boolean_input("Do you want to save the generated usernames to a file?")
    if save_to_file:
        filename = input("Enter the filename to save usernames (e.g., usernames.txt): ")
        try:
            with open(filename, "w") as file:
                for username in usernames:
                    file.write(username + "\n")
            print(f"Usernames saved to {filename}")
        except Exception as e:
            print(f"Error saving to file: {e}")

    print("\nThank you for using the Random Username Generator! Goodbye!")

if _name_ == "_main_":
    main()
