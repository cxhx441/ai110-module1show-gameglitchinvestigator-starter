# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
On first open, there is a title, a prompt for the user to make a guess, some developer info.
There's a box to input the user's guess.
two buttons: "submit guess" and "new game"
check box that allows turning off hints.
a selector dropdown for choosing the difficulty.

- List at least two concrete bugs you noticed at the start
  (for example: "the hints were backwards").
1. The hints are backwards. Guessing too low tells you to go lower and same for higher.
2. Clicking new game, after already won, doesn’t work. Resets the secret, but can’t input more. Same on game loss. Can only start new game in the middle or hard page refresh.


**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| "-1"  | hint to go higher | hint to go lower| NA                     |
| "101" | hint to go lower  |hint to go higher| NA                     |
| Click New Game after losing| Starts new game| No input accepted| NA |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
Claude.

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
It correctly found bugs about the backwards hints and fixed them. It found this same bug in multiple places. It also found other causes of the issue that I hadn't even realized. It suggest the correct fix for the hints. This was verified with a pytest and my own usability test by running the app.

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
When moving the game logic to the correct file, I only asked it to move 3 of the functions (called out specifically), it moved 3 these 3 but wanted to delete all 4 game logic functions from the original file. If I was blindly following, I would have lost the logic.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I wrote a pytest (with the help of claude) and confirmed the asserts made sense. I also ran the app and played the game to check if the hints were fixed.
- Describe at least one test you ran (manual or using pytest)
  and what it showed you about your code.
One test was to check that the hint string was correct. It showed that the original code was incorrect. This was also shown in the manual testing I did and the original 3 test already in the file.
- Did AI help you design or understand any tests? How?
Yes I asked claude to write pytests for the 3 functions we fixed. It added them to the pytest file and then even gave me a bash command to run pytest. 

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
