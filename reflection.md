# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| Guess 1 (secret is 28)                         | Too Low, shows Go HIGHER!                       | Shows Go LOWER! (wrong direction)                    | None; incorrect UI hint                     |
| Guess 30 (secret is 28)                        | Too High, shows Go LOWER!                       | Shows Go HIGHER! (wrong direction)                   | None; incorrect UI hint                     |
| Guess 100 (secret below 100)                   | Reject out-of-range guess or show Go LOWER!     | Can show Go HIGHER! for 100                          | None; misleading result                     |
| Use all attempts, click New Game, submit guess | New game starts, guesses accepted               | Attempts reset but game stays in game-over state     | Game over. Start a new game to try again.   |
| Select Easy or Hard, click New Game            | Secret within 1-20 (Easy) or 1-50 (Hard)        | Secret generated from 1-100 regardless of difficulty | None; debug panel shows out-of-range secret |
| Start new game, no guesses yet                 | Full attempt allowance shown (e.g. 8 on Normal) | Shows one fewer attempt (counter starts at 1)        | None; incorrect attempt display    

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
Claude CHATBOT
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
The attempts being needed to change and how they were the root cause was something I was not expecting at all. I accidentally let it auto push, but I asked it to explain each line it changed and went in and either changed it myself or reviewed and let it stay
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). 
It was doing too much with the pytestcase, it was accessing and mutating files and just made it much more complicated than necessary. refining code it didnt need to, while im sitting there with no idea if the current logic issues are fixed or not. So i asked it to tell me if the testcase will run or not, and since it did I didn't need to waste time on minimal changes unless the change was absolutely necessary for the purpose of checking if the logic works.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
It ran initially and the testing proved fruitful (no additional errors)
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
I did a pytest using 1 and 101, and kept zooming into the number, all the hints were correct
- Did AI help you design or understand any tests? How?
AI helped design its own tests, but it left me still confused, so I had to adminster my own knowing the intended output.
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
