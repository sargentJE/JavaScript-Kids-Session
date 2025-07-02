# Extension Activities & Challenges
## Number Detective Game - Level Up! 🚀

**For students who finish early or want more programming adventures!**

---

## Quick Modifications (5-10 minutes) ⚡

### 1. Change the Number Range 🎯
**Challenge:** Make the game harder by using bigger numbers!

**What to change:**
```javascript
// Find this line:
let secretNumber = Math.floor(Math.random() * 10) + 1;

// Change to:
let secretNumber = Math.floor(Math.random() * 50) + 1; // Numbers 1-50!
```

**Don't forget to update:**
- The input field: `max="50"`
- The instruction text: "Enter your guess (1-50):"
- The welcome message

---

### 2. Customize the Messages 💬
**Challenge:** Make the game say whatever you want!

**Examples to try:**
```javascript
// Change win message:
"🎉 BOOM! You cracked the code! 🎉"

// Change too high message:
"🔥 Whoa there! That's way too hot! 🔥"

// Change too low message:
"🧊 Brrr! That's too cold! 🧊"
```

**Voice messages too:**
```javascript
speak("Fantastic detective work! You solved the mystery!");
```

---

### 3. Change the Colors 🎨
**Challenge:** Design your own color scheme!

**Try these color combinations:**
```css
/* Ocean theme */
background-color: #001122;
color: #00ccff;
border-color: #0099cc;

/* Forest theme */
background-color: #002200;
color: #00ff66;
border-color: #009933;

/* Sunset theme */
background-color: #220011;
color: #ffaa00;
border-color: #ff6600;
```

---

## Medium Challenges (10-15 minutes) 🔥

### 4. Add a Guess Counter 📊
**Challenge:** Show how many guesses the player has made!

**Where to add it:**
```html
<!-- Add this in your HTML -->
<div id="guessCounter">Guesses made: 0</div>
```

**JavaScript to add:**
```javascript
function updateGuessCounter() {
    document.getElementById('guessCounter').innerText = 
        `Guesses made: ${guessCount}`;
}

// Call this function every time someone makes a guess
updateGuessCounter();
```

---

### 5. Create a High Score System 🏆
**Challenge:** Track the best score (fewest guesses to win)!

**Variables to add:**
```javascript
let bestScore = null; // Track the best score ever
```

**Logic to add in your win condition:**
```javascript
if (bestScore === null || guessCount < bestScore) {
    bestScore = guessCount;
    speak("New high score! Amazing detective work!");
    // Show special celebration
}
```

---

### 6. Add Helpful Hints 💡
**Challenge:** Give players clues about the secret number!

**Add a hint button:**
```html
<button onclick="giveHint()">Give Me a Hint! 💡</button>
```

**JavaScript for hints:**
```javascript
function giveHint() {
    if (secretNumber % 2 === 0) {
        speak("Hint: The secret number is even!");
    } else {
        speak("Hint: The secret number is odd!");
    }
}
```

**More hint ideas:**
- Is it bigger or smaller than 5?
- Is it divisible by 3?
- Is it a prime number?

---

## Advanced Projects (20+ minutes) 🎓

### 7. Word Guessing Game 📝
**Challenge:** Instead of numbers, guess secret words!

**Word list to start:**
```javascript
const secretWords = ["PIZZA", "ROBOT", "MAGIC", "MUSIC", "GAMES"];
let secretWord = secretWords[Math.floor(Math.random() * secretWords.length)];
```

**New comparison logic:**
```javascript
if (playerGuess.toUpperCase() === secretWord) {
    // They got it!
} else {
    // Give hints about letters or word length
}
```

---

### 8. Math Quiz Game 🧮
**Challenge:** Create a multiplication practice game!

**Generate math problems:**
```javascript
let num1 = Math.floor(Math.random() * 10) + 1;
let num2 = Math.floor(Math.random() * 10) + 1;
let correctAnswer = num1 * num2;

// Show the problem
document.getElementById('problem').innerText = 
    `What is ${num1} × ${num2}?`;
```

---

### 9. Multiple Difficulty Levels 🎮
**Challenge:** Let players choose Easy, Medium, or Hard!

**Add difficulty selector:**
```html
<select id="difficulty">
    <option value="10">Easy (1-10)</option>
    <option value="50">Medium (1-50)</option>
    <option value="100">Hard (1-100)</option>
</select>
```

**JavaScript to handle difficulty:**
```javascript
function changeDifficulty() {
    let maxNumber = document.getElementById('difficulty').value;
    secretNumber = Math.floor(Math.random() * maxNumber) + 1;
    // Update all the UI to reflect new range
}
```

---

### 10. Two-Player Game 👥
**Challenge:** Take turns with a friend!

**Add player tracking:**
```javascript
let currentPlayer = 1;
let player1Score = 0;
let player2Score = 0;
```

**Switch players after each game:**
```javascript
function switchPlayer() {
    currentPlayer = currentPlayer === 1 ? 2 : 1;
    speak(`Player ${currentPlayer}'s turn!`);
}
```

---

## Super Advanced (30+ minutes) 🚀

### 11. Save Progress in Browser 💾
**Challenge:** Remember high scores even after closing the browser!

**Using localStorage:**
```javascript
// Save high score
localStorage.setItem('bestScore', bestScore);

// Load high score when game starts
let savedScore = localStorage.getItem('bestScore');
if (savedScore) {
    bestScore = parseInt(savedScore);
}
```

---

### 12. Sound Effects Library 🎵
**Challenge:** Create different sounds for different events!

**Web Audio API examples:**
```javascript
function playWinSound() {
    const audioContext = new AudioContext();
    // Create ascending melody for winning
}

function playLoseSound() {
    // Create descending melody for wrong guesses
}

function playClickSound() {
    // Quick beep for button clicks
}
```

---

### 13. Visual Animations ✨
**Challenge:** Add moving and flashing elements!

**CSS animations:**
```css
@keyframes celebration {
    0% { transform: scale(1); }
    50% { transform: scale(1.1); }
    100% { transform: scale(1); }
}

.celebrating {
    animation: celebration 0.5s ease-in-out infinite;
}
```

**JavaScript to trigger:**
```javascript
document.getElementById('result').classList.add('celebrating');
```

---

## Creative Challenges 🎨

### 14. Theme Your Game 🏰
**Ideas for different themes:**
- **Pirate Treasure Hunt:** "Arrr! Find me buried treasure!"
- **Space Mission:** "Navigate to the correct star system!"
- **Detective Mystery:** "Crack the secret code!"
- **Magic School:** "Guess the correct spell number!"

**Change everything to match:**
- Colors and images
- All the text and messages
- Sound effects
- Victory celebrations

---

### 15. Make It Your Own 🌟
**Ultimate challenge:** Add features YOU think would be cool!

**Ideas to spark creativity:**
- Timer for speed challenges
- Bonus points for quick guesses
- Multiple secret numbers at once
- Story mode with different levels
- Accessibility features for different disabilities
- Integration with other games

---

## Debugging Challenges 🐛

Sometimes things don't work perfectly. That's normal! Here are some puzzle-solving challenges:

### Find the Bug! 🔍
**Broken code examples to fix:**

```javascript
// This won't work - can you spot why?
function checkguess() {  // Missing capital G
    if playerGuess = secretNumber {  // Missing parentheses and using = instead of ===
        speak("You won!")
    }
}
```

**Debugging tools:**
- Browser console (F12) shows error messages
- Check spelling of variable names
- Count your parentheses and brackets
- Look for missing semicolons

---

## Share Your Creations! 🤝

### Show and Tell:
1. **Demo your modifications** to friends and family
2. **Explain what you changed** and why
3. **Teach someone else** how to play your version
4. **Document your code** with comments

### Next Learning Steps:
- **Scratch programming** (scratch.mit.edu) - Visual coding
- **HTML/CSS tutorials** - Build websites  
- **Code.org** - More programming lessons
- **Local coding clubs** - Meet other young programmers

---

## Remember: Programming is Creative! 🎨

There's no "wrong" way to modify your game. Try things, break things, fix things. Every programmer learns by experimenting!

**The most important rule:** Have fun and keep exploring! 🚀

---

*Extension activities designed for MyVision Oxfordshire*  
*Keep building, keep learning, keep creating!*