# Rock-Paper-Scissors-Game

import random
while True:
    # Get player name
    player_name = input("Enter your name: ")
    
    # Initialize scores and choices
    player_score = 0
    computer_score = 0
    choices = ['rock', 'paper', 'scissors']

    while player_score < 5 and computer_score < 5:
        # Get player choice
        player_choice = ''
        while player_choice not in choices:
            player_choice = input(f"{player_name}, enter your choice (rock/paper/scissors): ").lower()

        # Get computer choice
        computer_choice = random.choice(choices)

        # Determine winner
        if player_choice == computer_choice:
            print(f"Both players chose {player_choice}. It's a tie!")
        elif (player_choice == 'rock' and computer_choice == 'scissors') or \
             (player_choice == 'paper' and computer_choice == 'rock') or \
             (player_choice == 'scissors' and computer_choice == 'paper'):
            print(f"{player_name} chose {player_choice} and the computer chose {computer_choice}. {player_name} wins!")
            player_score += 1
        else:
            print(f"{player_name} chose {player_choice} and the computer chose {computer_choice}. Computer wins!")
            computer_score += 1

        # Print current scores
        print(f"{player_name}: {player_score}, Computer: {computer_score}")

    # Print final result
    if player_score > computer_score:
        print(f"Congratulations, {player_name} wins!")
    else:
        print("Computer wins!")

    # Ask if player wants to play again
    if input('Do you want to play again? ').lower().startswith('y'):
        # Reset scores and play again
        player_score = 0
        computer_score = 0
        continue
    else:
        print("Thanks for playing!")
        break
