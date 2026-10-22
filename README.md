# Rock Paper Scissors (Python)

A simple command-line Rock Paper Scissors game written in Python. You choose how many rounds to play, the computer picks randomly each round, and your final score is saved to a text file.

## Features

- Play any number of rounds in one session
- Computer picks rock, paper, or scissor at random
- Input is case-insensitive and ignores extra spaces (`Rock`, ` PAPER `, etc.)
- Tracks wins for both the user and the computer
- Saves the final score to `file1.txt`
- Basic error handling with `try/except`

## Requirements

- Python 3.6 or higher
- No external libraries (only the built-in `random` module)

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. Run the program:

   ```bash
   python import_random.py
   ```

## How to Play

1. Enter how many games you want to play.
2. For each round, type `rock`, `paper`, or `scissor`.
3. The computer's choice and the result are shown after every round.
4. When all rounds are finished, the final score is printed and saved.

### Rules

| Your choice | Beats    |
|-------------|----------|
| rock        | scissor  |
| paper       | rock     |
| scissor     | paper    |

If both choose the same, the round is a tie and nobody scores.

## Example Output

```
How many games do you want to play? 3
Enter rock, paper, or scissor: rock
Computer chose scissor. You win!
Enter rock, paper, or scissor: paper
Computer chose paper. It's a tie!
Enter rock, paper, or scissor: scissor
Computer chose rock. You lose!
User wins: 1, Computer wins: 1
```

## Saved Score

After the last round, the result is written to `file1.txt`:

```
  USER WIN 1 	 COMPUTER WIN : 1
```

Note: the file is opened in write mode (`"w"`), so each run replaces the previous score.

## How It Works

- A dictionary maps each choice to the choice it beats:

  ```python
  choice = {"rock": "scissor", "paper": "rock", "scissor": "paper"}
  ```

- `random.choice()` picks the computer's move from the dictionary keys.
- `play_game()` compares the two moves, updates the score, and returns the result message.
- `file_save()` writes the final score to `file1.txt`.

## Concepts Practiced

- Dictionaries and random selection
- `while` loops and counters
- Functions and the `global` keyword
- String methods (`.lower()`, `.strip()`)
- Exception handling (`try/except`)
- File handling (writing to a text file)

## Known Limitations and Future Improvements

- An invalid input shows a message but still uses up one round. It should ask again instead.
- Scores are not kept between runs (the file is overwritten each time).
- Ideas for later:
  - Re-ask on invalid input without losing a round
  - Append scores to the file (`"a"` mode) to keep a history
  - Show a final winner message ("You won the match!")
  - Add a "play again" option
  - Build a GUI with `tkinter`

## Project Structure

```
.
├── import_random.py   # main game code
├── file1.txt          # created after playing (final score)
└── README.md
```

## Author

Your Name  
GitHub: [@piratewave32](https://github.com/piratewave32)

## License

This project is open source and free to use for learning purposes.
