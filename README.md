<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Padiverse | By Aditya</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to right, #1f1c2c, #928DAB);
      color: white;
      text-align: center;
      padding: 20px;
    }
    .page {
      display: none;
      animation: fadeIn 0.6s ease-in-out;
    }
    .active {
      display: block;
    }
    button {
      background: #fff;
      color: #000;
      padding: 12px 25px;
      margin: 10px;
      border: none;
      border-radius: 12px;
      font-size: 16px;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background: #00ffe7;
      transform: scale(1.05);
    }
    input {
      padding: 10px;
      font-size: 16px;
      border-radius: 10px;
      border: none;
      margin-top: 10px;
    }
    h1, h2 {
      margin-top: 10px;
      font-weight: bold;
    }
    #popup {
      display: none;
      position: fixed;
      top: 30%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: #00ffae;
      color: black;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 0 20px #00000080;
      font-size: 24px;
      z-index: 999;
    }

    /* Game menu grid */
    .game-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      padding: 20px;
    }

    .game-card {
      background: linear-gradient(135deg, #fff, #d1f7ff);
      color: #000;
      padding: 30px 10px;
      border-radius: 20px;
      font-size: 18px;
      font-weight: bold;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
      cursor: pointer;
      transition: 0.3s;
    }

    .game-card:hover {
      background: #00ffe7;
      transform: scale(1.05);
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
  
  #tic-board {
    display: grid;
    grid-template-columns: repeat(3, 70px);
    gap: 10px;
    justify-content: center;
    margin: 20px auto;
  }
  #tic-board button {
    width: 70px;
    height: 70px;
    font-size: 28px;
    border-radius: 10px;
    background: #e3e3e3;
    color: #000;
    font-weight: bold;
  }
</style>
</head>
<body>
  <div id="popup">🎉 Congratulations!</div>

  <!-- 🔷 Intro Page -->
  <div id="intro" class="page active">
    <h1>🌟 Welcome to Padiverse 🌟</h1>
    <p>Made by <strong>Aditya</strong></p>
    <p>Instagram: @_uk_adii_0908</p>
    <button onclick="goTo('menu')">Let's Play</button>
  </div>

  <!-- 🔶 Game Menu -->
  <div id="menu" class="page">
    <h2>🎮 Choose Your Game</h2>
    <div class="game-grid">
      <div class="game-card" onclick="goTo('ticInstructions')">Tic Tac Toe</div>
      <div class="game-card" onclick="goTo('guessInstructions')">Number Guessing</div>
      <div class="game-card" onclick="goTo('rpsInstructions')">Rock Paper Scissors</div>
      <div class="game-card" onclick="goTo('diceInstructions')">Dice Simulator</div>
      <div class="game-card" onclick="goTo('reactionInstructions')">Reaction Tester</div>
      <div class="game-card" onclick="goTo('typingInstructions')">Typing Game</div>
      <div class="game-card" onclick="goTo('colorInstructions')">Color Match</div>
      <div class="game-card" onclick="goTo('coinInstructions')">Coin Flip</div>
      <div class="game-card" onclick="goTo('mathInstructions')">Quick Math Quiz</div>
      <div class="game-card" onclick="goTo('mysteryInstructions')">Mystery Door</div>
    </div>
  </div>
  <!-- Tic Tac Toe -->
<div id="ticInstructions" class="page">
  <h2>Tic Tac Toe 🧠</h2>
  <p>Take turns placing X and O. First to 3 in a row wins!</p>
  <button onclick="goTo('ticGame'); startTicTacToe()">Start</button>
</div>
<div id="ticGame" class="page">
  <h2>Tic Tac Toe</h2>
  <div id="tic-board"></div>
  <p id="tic-result"></p>
  <button onclick="startTicTacToe()">🔄 Restart</button>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Number Guessing -->
<div id="guessInstructions" class="page">
  <h2>Number Guessing 🔢</h2>
  <p>Guess a number between 1 and 100. You'll get hints!</p>
  <button onclick="goTo('guessGame'); startGuessing()">Start</button>
</div>
<div id="guessGame" class="page">
  <h2>Guess the Number</h2>
  <input type="number" id="guessInput" placeholder="Enter number" />
  <button onclick="checkGuess()">Guess</button>
  <p id="guessMessage"></p>
  <button onclick="startGuessing()">🔄 Restart</button>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Rock Paper Scissors -->
<div id="rpsInstructions" class="page">
  <h2>Rock Paper Scissors ✊✋✌️</h2>
  <p>Choose rock, paper or scissors. Beat the computer!</p>
  <button onclick="goTo('rpsGame')">Start</button>
</div>
<div id="rpsGame" class="page">
  <h2>Rock Paper Scissors</h2>
  <button onclick="playRPS('rock')">✊ Rock</button>
  <button onclick="playRPS('paper')">✋ Paper</button>
  <button onclick="playRPS('scissors')">✌️ Scissors</button>
  <p id="rpsResult"></p>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Dice Simulator -->
<div id="diceInstructions" class="page">
  <h2>Dice Roll 🎲</h2>
  <p>Click to roll the dice (1 to 6).</p>
  <button onclick="goTo('diceGame')">Start</button>
</div>
<div id="diceGame" class="page">
  <h2>Dice Simulator</h2>
  <button onclick="rollDice()">🎲 Roll</button>
  <p id="diceResult"></p>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Reaction Tester -->
<div id="reactionInstructions" class="page">
  <h2>Reaction Tester ⚡</h2>
  <p>Tap the box as soon as it turns green!</p>
  <button onclick="goTo('reactionGame'); prepareReaction()">Start</button>
</div>
<div id="reactionGame" class="page">
  <h2>Reaction Time</h2>
  <div id="reactionBox" onclick="recordReaction()" style="padding: 50px; background: red; border-radius: 20px; margin: 20px auto; cursor: pointer;">
    <p id="reactionText">Wait for green...</p>
  </div>
  <p id="reactionResult"></p>
  <button onclick="prepareReaction()">🔄 Retry</button>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Typing Speed Game -->
<div id="typingInstructions" class="page">
  <h2>Typing Speed Test ⌨️</h2>
  <p>Type the shown word as fast as you can!</p>
  <button onclick="goTo('typingGame'); startTyping()">Start</button>
</div>
<div id="typingGame" class="page">
  <h2>Typing Game</h2>
  <p>Word: <strong id="wordToType"></strong></p>
  <input id="typedWord" placeholder="Type here" oninput="checkTyping()" />
  <p id="typingResult"></p>
  <button onclick="startTyping()">🔄 Try Again</button>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Color Match Game -->
<div id="colorInstructions" class="page">
  <h2>Color Match 🎨</h2>
  <p>Click when the background matches the color name!</p>
  <button onclick="goTo('colorGame'); startColorMatch()">Start</button>
</div>
<div id="colorGame" class="page">
  <h2>Color Match</h2>
  <h3 id="targetColor"></h3>
  <div id="colorBox" style="width:100px;height:100px;margin:auto;border-radius:12px;"></div>
  <button onclick="checkColor()">Check</button>
  <p id="colorResult"></p>
  <button onclick="startColorMatch()">🔄 Retry</button>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Coin Flip -->
<div id="coinInstructions" class="page">
  <h2>Coin Flip 🪙</h2>
  <p>Click to flip the coin!</p>
  <button onclick="goTo('coinGame')">Start</button>
</div>
<div id="coinGame" class="page">
  <h2>Flip the Coin</h2>
  <button onclick="flipCoin()">🪙 Flip</button>
  <p id="coinResult"></p>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Math Quiz -->
<div id="mathInstructions" class="page">
  <h2>Quick Math Quiz ➕</h2>
  <p>Solve the math question quickly!</p>
  <button onclick="goTo('mathGame'); startMathQuiz()">Start</button>
</div>
<div id="mathGame" class="page">
  <h2>Math Quiz</h2>
  <p id="mathQuestion"></p>
  <input type="number" id="mathAnswer" />
  <button onclick="checkMath()">Submit</button>
  <p id="mathResult"></p>
  <button onclick="startMathQuiz()">🔄 Retry</button>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<!-- Mystery Door -->
<div id="mysteryInstructions" class="page">
  <h2>Mystery Door 🚪</h2>
  <p>Choose one of the 3 doors. One has treasure!</p>
  <button onclick="goTo('mysteryGame'); setupDoors()">Start</button>
</div>
<div id="mysteryGame" class="page">
  <h2>Mystery Door</h2>
  <div style="display:flex;justify-content:center;gap:20px;">
    <button onclick="chooseDoor(1)">🚪 Door 1</button>
    <button onclick="chooseDoor(2)">🚪 Door 2</button>
    <button onclick="chooseDoor(3)">🚪 Door 3</button>
  </div>
  <p id="mysteryResult"></p>
  <button onclick="setupDoors()">🔄 Retry</button>
  <button onclick="goTo('menu')">⬅ Back</button>
</div>
<script>
  // 🔄 PAGE SWITCHER
  function goTo(id) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById(id).classList.add('active');
  }

  // 🎉 POPUP
  function showPopup(message) {
    const popup = document.getElementById('popup');
    popup.textContent = message;
    popup.style.display = 'block';
    setTimeout(() => {
      popup.style.display = 'none';
    }, 2000);
  }

  // ✅ TIC TAC TOE
  let currentPlayer = 'X';
  function startTicTacToe() {
    const board = document.getElementById('tic-board');
    board.innerHTML = '';
    document.getElementById('tic-result').textContent = '';
    currentPlayer = 'X';
    for (let i = 0; i < 9; i++) {
      const btn = document.createElement('button');
      btn.onclick = () => markCell(btn);
      board.appendChild(btn);
    }
  }
  function markCell(btn) {
    if (btn.textContent === '') {
      btn.textContent = currentPlayer;
      if (checkWin()) {
        document.getElementById('tic-result').textContent = `${currentPlayer} Wins!`;
        showPopup(`${currentPlayer} Wins!`);
      } else if ([...document.querySelectorAll('#tic-board button')].every(b => b.textContent)) {
        document.getElementById('tic-result').textContent = `Draw!`;
        showPopup(`It's a Draw!`);
      } else {
        currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
      }
    }
  }
  function checkWin() {
    const b = [...document.querySelectorAll('#tic-board button')].map(btn => btn.textContent);
    const wins = [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]];
    return wins.some(([a,b1,c]) => b[a] && b[a] === b[b1] && b[a] === b[c]);
  }

  // 🔢 NUMBER GUESSING
  let guessNumber = 0;
  function startGuessing() {
    guessNumber = Math.floor(Math.random() * 100) + 1;
    document.getElementById('guessMessage').textContent = '';
    document.getElementById('guessInput').value = '';
  }
  function checkGuess() {
    const guess = parseInt(document.getElementById('guessInput').value);
    const msg = guess > guessNumber ? 'Too High!' : guess < guessNumber ? 'Too Low!' : '🎉 Correct!';
    document.getElementById('guessMessage').textContent = msg;
    if (guess === guessNumber) showPopup('You guessed it!');
  }

  // ✊ ROCK PAPER SCISSORS
  function playRPS(player) {
    const options = ['rock', 'paper', 'scissors'];
    const comp = options[Math.floor(Math.random() * 3)];
    let result = '';
    if (player === comp) result = 'Draw!';
    else if (
      (player === 'rock' && comp === 'scissors') ||
      (player === 'paper' && comp === 'rock') ||
      (player === 'scissors' && comp === 'paper')
    ) result = 'You Win!';
    else result = 'You Lose!';
    document.getElementById('rpsResult').textContent = `Computer chose ${comp}. ${result}`;
    showPopup(result);
  }

  // 🎲 DICE ROLL
  function rollDice() {
    const dice = Math.floor(Math.random() * 6) + 1;
    document.getElementById('diceResult').textContent = `🎲 Rolled: ${dice}`;
    showPopup(`You got ${dice}`);
  }

  // ⚡ REACTION TIME
  let reactionStart = 0;
  function prepareReaction() {
    const box = document.getElementById('reactionBox');
    const text = document.getElementById('reactionText');
    text.textContent = 'Wait for green...';
    box.style.background = 'red';
    box.onclick = () => {};
    setTimeout(() => {
      box.style.background = 'green';
      text.textContent = 'Click!';
      reactionStart = Date.now();
      box.onclick = recordReaction;
    }, Math.random() * 3000 + 1000);
  }
  function recordReaction() {
    const time = (Date.now() - reactionStart) / 1000;
    document.getElementById('reactionResult').textContent = `⚡ Your time: ${time}s`;
    showPopup(`${time}s`);
  }

  // ⌨️ TYPING SPEED
  let typingStart = 0;
  const wordList = ['banana', 'galaxy', 'reactor', 'magic', 'keyboard', 'jump'];
  function startTyping() {
    const word = wordList[Math.floor(Math.random() * wordList.length)];
    document.getElementById('wordToType').textContent = word;
    document.getElementById('typedWord').value = '';
    document.getElementById('typingResult').textContent = '';
    typingStart = Date.now();
  }
  function checkTyping() {
    const input = document.getElementById('typedWord').value.trim();
    const word = document.getElementById('wordToType').textContent;
    if (input === word) {
      const time = ((Date.now() - typingStart) / 1000).toFixed(2);
      document.getElementById('typingResult').textContent = `🎯 Time: ${time}s`;
      showPopup(`Speed: ${time}s`);
    }
  }

  // 🎨 COLOR MATCH
  const colorOptions = ['red', 'blue', 'green', 'yellow', 'purple', 'orange'];
  function startColorMatch() {
    const target = colorOptions[Math.floor(Math.random() * colorOptions.length)];
    const actual = colorOptions[Math.floor(Math.random() * colorOptions.length)];
    document.getElementById('targetColor').textContent = target.toUpperCase();
    const box = document.getElementById('colorBox');
    box.style.background = actual;
    box.dataset.actual = actual;
    document.getElementById('colorResult').textContent = '';
  }
  function checkColor() {
    const shown = document.getElementById('targetColor').textContent.toLowerCase();
    const actual = document.getElementById('colorBox').dataset.actual;
    const result = shown === actual ? "🎯 Correct!" : `❌ Wrong! It was ${actual}`;
    document.getElementById('colorResult').textContent = result;
    showPopup(result);
  }

  // 🪙 COIN FLIP
  function flipCoin() {
    const result = Math.random() < 0.5 ? 'Heads' : 'Tails';
    document.getElementById('coinResult').textContent = `🪙 ${result}`;
    showPopup(result);
  }

  // ➕ MATH QUIZ
  let mathAnswer = 0;
  function startMathQuiz() {
    const a = Math.floor(Math.random() * 10) + 1;
    const b = Math.floor(Math.random() * 10) + 1;
    mathAnswer = a + b;
    document.getElementById('mathQuestion').textContent = `What is ${a} + ${b}?`;
    document.getElementById('mathAnswer').value = '';
    document.getElementById('mathResult').textContent = '';
  }
  function checkMath() {
    const input = parseInt(document.getElementById('mathAnswer').value);
    const result = input === mathAnswer ? '✅ Correct!' : '❌ Try again!';
    document.getElementById('mathResult').textContent = result;
    if (input === mathAnswer) showPopup('Correct!');
  }

  // 🚪 MYSTERY DOOR
  let treasureDoor = 1;
  function setupDoors() {
    treasureDoor = Math.floor(Math.random() * 3) + 1;
    document.getElementById('mysteryResult').textContent = '';
  }
  function chooseDoor(n) {
    const msg = n === treasureDoor ? '🎉 You found the treasure!' : '❌ Empty door!';
    document.getElementById('mysteryResult').textContent = msg;
    showPopup(msg);
  }
</script>
</body>
</html>
