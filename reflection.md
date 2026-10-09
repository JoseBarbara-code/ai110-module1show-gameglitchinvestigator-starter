# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

The game looked good at the beginning. But you can tell where the code falls almost right away.
One concrete bug is that the hints are just completely off when i guessed 1 is said Lower and when i guessed 100 it said higher.
The other bug is that when the game is over and you try to press new game it doesnt work and an error command pops up.
Finally the last bug that i observed was when you have one attempt left it does not let you guess anything rather just gives you the answer.


**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| New Game | new game | Game over | Start a new game to try again. |
| guess of 1 | hint to be higher | hint was lower | none |
| Attempts left 1 | one more attempt | answer was given | Out of attempts! The secret was 67. Score: -35 |


---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
I used Claude in VS Code along with Copilot to verify whether the Claude code was correct. I then checked the changes in both suggestions of code before choosing and verifying that the code was fixed effectively. I ran the tests in my terminal as well for extra assurance.
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
One of the suggestions that claude suggested was to reset the game status to be playing. Checking the code I found that the old status stayed in either won or lost not letting the player play another game. The copiolt went over the same code and confirmed that the issue lied in the status. I then looked over the code that was fixed and saw that the changes made sense. I tested both when i won and lost to see if the new game button worked as intened. Once I made sure that the code was good I ran the tests on my terminal to check the guessing logic.
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.
While I was reviewing the new game button code with Copilot after talking to Claude, Copilot suggested a line of code to reset the score to zero for every new game. I left the suggestion out because I just wanted to make sure that my New Game button worked as intended. Once I verified that the button worked after a win and a loss, I knew that I really did not need to add it. st.session_state.score = 0 --- This was the suggestion.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
When the code was fixed for the hints, I guessed numbers below and above the secret number to check if it was giving the right hints. For the New Game code, I clicked new game after I won and lost to make sure that it worked when both were in different status. Along with that, I ran py -m pytest -v in my terminal, making sure that all four tests passed.
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
I manually checked the secret to see whether the hints were correct. I made a guess of 1 when the secret was 67. The hint was higher, which let me know the code worked for the case I was testing. Before that, the code was saying that it was lower than 1. It showed me that the code was pointing in the wrong direction.
- Did AI help you design or understand any tests? How?
Claude updated the starter tests to check the hint message. It also helped by giving me the command py -m pytest -v for me to manually type in my terminal. Using the functions that the AI made, I was able to check, using that command, whether they passed the test. I also verified the code, making sure that the testing of the functions made sense.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
