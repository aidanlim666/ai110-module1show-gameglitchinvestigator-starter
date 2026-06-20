# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?
The game has a submit guess button, new game button, and show hint toggle. The user is able to win the game by entering the correct number. The sidebar on the left shows number of attempts, range of numbers, and difficulty. Bugs I have noticed are wrong hints (opposite direction), as well as inability to start a new game with the 'new game' button (it doesn't allow me to guess again).


**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| 1     | Go Higher           Go Lower          
| 60      Go Lower            Go Higher
| 2       Go Higher           Go Lower

---

## 2. How did you use AI as a teammate?

I used Claude Code on this assignment.
The AI pointed out the bug that the user can't win on an even-numbered attempt, which is something I didn't realize the first time, and helped fix it. It also helped me realize the counter needed fixing, it should only increment on valid guesses.
Because this session was rather short, it didn't seem to have generated any misleading suggestions.

---

## 3. Debugging and testing your fixes


To decide whether a bug was really fixed, I tested it myself, trying several edge cases in addition to the failed test cases previously, to see whether it really changed.
For example, for testing the bug that didn't allow the user to win on a even-numbered guess, I tried both winning on an odd and even numbered guess, and both passed.
AI didn't help me design tests, but it said that 'all test passed'.


---

## 4. What did you learn about Streamlit and state?


In Streamlit, every click "reruns" your whole script, so regular variables reset.
You must put any variables you want to survive the "rerun" in the "session state".

---

## 5. Looking ahead: your developer habits


The habit I want to reuse is trying my own edge cases before trusting a fix actually works. Sometimes I allowed the AI to commit before I checked and tested myself first.
Next time, I would give longer prompts to the AI, instead of just asking one sentence questions, such as "why is it doing xxxx"
This project showed me that AI generated code is only as good as the human checking it. For example the original copy had many bugs because it was not checked for edge cases by the human who wrote it. AI is a useful tool to revise and test itself.
