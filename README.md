# Guessing game
Having fun while working in Python, I created an interactive guessing game

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
