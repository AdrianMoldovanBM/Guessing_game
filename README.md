# Guessing game
Coding using Jupyter Notebook, I created a fun little game, that allows the user to guess a random number between 1 and 10 and provides helpful feedback based on their guesses.
If the user guesses a wrong number, the program prompts for a higher or lower number, until it's correct.
I also implemented a function for the player to restart or stop the game at the end.

# Code:
        # Using the random library as a base for generating numbers
        import random

        # Providing feedback on whether the guess is too high, too low, or correct
        def play_round():
            magic_num = random.randint(1, 10)
            user_input = None
            while user_input != magic_num:
                try:
                    user_input = int(input("Guess a number between 1-10: "))
                    if user_input < 1 or user_input > 10:
                        print("Please guess a number between 1 and 10.")
                    elif user_input == magic_num:
                        print("You got it!")
                    elif user_input < magic_num:
                        print("Guess higher")
                    else:
                        print("Guess lower")
                except ValueError:
                    print("Invalid input. Please enter a number between 1 and 10.")
            
            # Managing the overall game loop, allowing the player to play multiple rounds
        def guess_game():
            while True:
                play_round()
                while True:
                    play_again = input("Wanna try again? (Yes!/No!): ").strip().lower()
                    if play_again in ["yes", "no"]:
                        break
                    else:
                        print("Invalid input. Please enter 'Yes' or 'No'.")

                if play_again == "no":
                    print("Game Over")
                    break

# Execution:
    guess_game()
