# UT-DSA-Web-F25-evil_hangman-SENTHILKUMARSOMASUNDARAM
UTA MS Assignement

### Overview
This project implements an **Evil Hangman** game where the computer acts as a cheating word-maker.  
Instead of choosing a fixed word at the start, the program delays word selection for as long as possible,  
maximizing the difficulty for the word-guesser.

The assignment provides practice in choosing efficient data structures and algorithmic strategies.

### Rules Recap
- Traditional Hangman: The guesser attempts to find a hidden word within a limited number of guesses.  
- Evil Hangman:  
  - The program maintains a pool of possible words.  
  - When a guess is made, it partitions the dictionary into word families based on letter positions.  
  - The largest family is chosen, revealing minimal information to the guesser.  
  - In case of ties, fewer revealed letters are preferred, with `----` (no matches) being the strongest option.  

### Implementation Details
- Implement the `WordMakerAI` class in `py_evil_hangman/word_maker.py`.
- Key methods to implement:
  - `guess(letter)` → return positions of the guessed letter in the chosen family.  
  - `reset(word_length)` → reset the game with a new dictionary of words.  
  - `get_valid_word()` → return one valid word at the end of the game.  
  - `get_amount_of_valid_words()` → return the number of remaining possible words.  
  - `get_letter_positions_in_word(word, letter)` → helper to find letter positions.  

### Efficiency Requirements
- Preprocess dictionary to allow **O(1)** resets.  
- Use **hash tables (dictionaries)** for grouping word families efficiently.  
- Avoid brute-force enumeration of all letter placements.  

### Optional Karma Challenge
- Implement a `WordGuesserAI` in `py_evil_hangman/word_guesser.py`.  
- Document your approach in a `karma.txt` file.  
- Run with `-k` flag to test against the Evil Hangman.  

### Running the Game
- Run **Hangman** or **Evil Hangman** using PyCharm run configurations.  
- Use command-line flags:  
  - `-f <dictionary_file>` → specify dictionary  
  - `-g <num_guesses>` → set number of guesses  
  - `-v` → verbose mode  

### Acknowledgments
This assignment is adapted from Keith Schwarz’s original Evil Hangman project,  
modified by Matthew Giordano and Calvin Lin.
