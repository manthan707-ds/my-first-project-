# my-first-project-
import random

def get_computer_choice():
    return random.choice(['snake', 'water', 'gun'])

def determine_winner(user, computer):
    if user == computer:
        return "draw"
    elif (user == 'snake' and computer == 'water') or \
         (user == 'gun' and computer == 'snake') or \
         (user == 'water' and computer == 'gun'):
        return "user"
    else:
        return "computer"

def play_game():
    print("Welcome to Snake, Water, Gun Game!")
    user_choice = input("Enter your choice (snake, water, gun): ").lower()
    
    if user_choice not in ['snake', 'water', 'gun']:
        print("Invalid choice! Please choose snake, water, or gun.")
        return

    computer_choice = get_computer_choice()
    print(f"Computer chose: {computer_choice}")

    winner = determine_winner(user_choice, computer_choice)

    if winner == "draw":
        print("It's a draw!")
    elif winner == "user":
        print("You win!")
    else:
        print("Computer wins!")

# Run the game
play_game()

