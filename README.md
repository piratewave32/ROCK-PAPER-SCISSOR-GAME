import random

choice = {
    "rock": "scissor",
    "paper": "rock",
    "scissor": "paper"
}
number_of_games = int(input("How many games do you want to play? "))
winof_computer  = 0
user_win = 0 
while number_of_games > 0:
  computer_choice = random.choice(list(choice.keys()))
  user_input = input("Enter rock, paper, or scissor: ").lower().strip()
  if user_input not in choice:
    print("Please insert a valid input.")
  
  try:
     def play_game(user_input,computer_choice):
      global user_win, winof_computer
     
 
      if user_input == computer_choice:
        return f"Computer chose {computer_choice}. It's a tie!"
        
      elif (choice[user_input] == computer_choice):
         
         user_win += 1
         return f"Computer chose {computer_choice}. You win!"
      else:
        winof_computer += 1
      return f"Computer chose {computer_choice}. You lose!"
     print(play_game(user_input,computer_choice)) 
  except Exception as e:
        print("An error occurred.", e)
 
  number_of_games -= 1
  

print(f"User wins: {user_win}, Computer wins: {winof_computer}")
