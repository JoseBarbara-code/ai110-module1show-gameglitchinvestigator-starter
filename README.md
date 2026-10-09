# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- The purpose of the game was for the player to guess the secret number using the hints to guess correctly. The player had a limited number of attempts, and the game's hints told the player whether their guess was too high or too low. The game also tracked the player's score and displayed it at the end, regardless of whether they won or lost.
- There were three major bugs that I found while testing the game. The first bug was that the hints were pointing me in the wrong direction. For example, when the secret number was 54 and I guessed 1, the hint would tell me to guess lower instead of higher. The second major bug was that regardless of whether I won or lost, the New Game button would not work. The last bug was that the game would display a prompt revealing the secret number while the player still had one attempt left.
-I used Claude and Copilot to help find and fix the bugs. The hint was corrected so that the hints pointed the player in the right direction. The game status was found to be the reason the New Game button was not working. This was then fixed so that the button worked regardless of whether the player won or lost. I reviewed the code and manually tested the game to make sure the fixes worked correctly. After making those changes, I ran py -m pytest -v in my terminal to check the automated tests.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. The player automatically starts a new game where they have to guess a secret number while having a limited number of attempts.
2. The secret number is 78, and the player guesses 42. The game gives a hint telling the player to guess higher.
3. The player then guesses 79, and the game responds with a hint telling the player to guess lower.
4. The player guesses the correct number, 78, and the game responds with a message stating that they won.
5. The game displays the player's final score.
6. The player can then click the New Game button, allowing them to start another game and replay as many times as they want.




