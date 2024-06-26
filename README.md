import random

def number_guessing_game():
    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100.")
    
    # Generate a random number between 1 and 100
    number_to_guess = random.randint(1, 100)
    
    attempts = 0
    guessed = False
    
    while not guessed:
        try:
            # Take a guess from the user
            guess = int(input("Take a guess: "))
            attempts += 1
            
            if guess < 1 or guess > 100:
                print("Please enter a number between 1 and 100.")
            elif guess < number_to_guess:
                print("Your guess is too low. Try again.")
            elif guess > number_to_guess:
                print("Your guess is too high. Try again.")
            else:
                guessed = True
                print(f"Congratulations! You've guessed the right number in {attempts} attempts.")
        except ValueError:
            print("Invalid input. Please enter a valid number.")

# Run the game
number_guessing_game()
