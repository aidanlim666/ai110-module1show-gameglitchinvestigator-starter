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

- [ ] Describe the game's purpose.
- [ ] Detail which bugs you found.
- [ ] Explain what fixes you applied.

The game is a number guessing game, where the computer picks a secret number within the range (corresponding with difficulty), and the player attempts to guess it.
Some bugs I found were the "new game" button broken, unable to win on even-numbered attempt, hints were opposite of what they were supposed to be, attempt counter was off by one, and difficulty levels were inconsistent.
To fix this, I asked Claude Code, and it recommended to refactor all four functions into logic_utils.py and have app.py import them. I fixed the logic behind the attempt counter (initialized attempts to 0 and only increment on valid guess), added a start_new_game() helper, and removed the str() coersion, so comparisons are always between integers. I also made check_guess return just the outcome string, and corrected the hint directions.


## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. Run python -m streamlit run app.py.
2. Pick difficulty level in the sidebar.
3. Type a guess and click submit, which returns a hint.
4. Look at the hint and narrow down your next guess.
5. Keep going until the game is over, and then click new game.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
# pytest tests/
# ========================= X passed in 0.XXs =========================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
