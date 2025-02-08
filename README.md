<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Valentine?</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 100px;
      background-color: #f9f9f9;
    }
    h1 {
      color: #e91e63;
    }
    .buttons {
      margin-top: 20px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    #yesButton {
      background-color: #4caf50;
      color: white;
    }
    #noButton {
      background-color: #f44336;
      color: white;
      position: absolute;
    }
    .confetti {
      position: fixed;
      width: 10px;
      height: 10px;
      background-color: #ff0;
      animation: confetti-fall 2s linear infinite;
    }
    @keyframes confetti-fall {
      0% { transform: translateY(0) rotate(0deg); }
      100% { transform: translateY(100vh) rotate(360deg); }
    }
  </style>
</head>
<body>
  <h1>Will you be my Valentine?</h1>
  <div class="buttons">
    <button id="yesButton">Yes</button>
    <button id="noButton">No</button>
  </div>
  <div id="celebration" style="display: none;">
    <h2>Yay! You made my day! 💖🎉</h2>
    <div id="confettiContainer"></div>
  </div>

  <script>
    const yesButton = document.getElementById('yesButton');
    const noButton = document.getElementById('noButton');
    const celebration = document.getElementById('celebration');
    const confettiContainer = document.getElementById('confettiContainer');

    yesButton.addEventListener('click', () => {
      celebration.style.display = 'block';
      createConfetti();
    });

    noButton.addEventListener('click', () => {
      moveNoButton();
    });

    function moveNoButton() {
      const x = Math.random() * (window.innerWidth - noButton.offsetWidth);
      const y = Math.random() * (window.innerHeight - noButton.offsetHeight);
      noButton.style.left = ${x}px;
      noButton.style.top = ${y}px;
    }

    function createConfetti() {
      for (let i = 0; i < 100; i++) {
        const confetti = document.createElement('div');
        confetti.classList.add('confetti');
        confetti.style.left = ${Math.random() * 100}vw;
        confetti.style.animationDelay = ${Math.random() * 2}s;
        confetti.style.backgroundColor = hsl(${Math.random() * 360}, 100%, 50%);
        confettiContainer.appendChild(confetti);
      }
    }
  </script>
</body>
</html>
