<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
  <title>💘 Valentine Puzzle 💘</title>

  <style>
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", Arial, sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      padding: 15px;
    }

    .card {
      background: white;
      padding: 25px 20px;
      border-radius: 20px;
      width: 100%;
      max-width: 360px;
      box-shadow: 0 15px 30px rgba(0,0,0,0.25);
      text-align: center;
    }

    h2, h3 {
      margin-top: 0;
    }

    button {
      width: 100%;
      background: #ff4d6d;
      color: white;
      border: none;
      padding: 16px;
      border-radius: 30px;
      font-size: 18px;
      margin-top: 15px;
      cursor: pointer;
    }

    button:active {
      transform: scale(0.97);
      background: #e63950;
    }

    input {
      width: 100%;
      padding: 14px;
      font-size: 18px;
      margin-top: 12px;
      border-radius: 14px;
      border: 1px solid #ccc;
      text-align: center;
      box-sizing: border-box;
    }

    .hidden {
      display: none;
    }

    p {
      font-size: 16px;
      line-height: 1.4;
    }
  </style>
</head>
<body>

  <div class="card">

    <!-- Start -->
    <div id="start">
      <h2>💘 Happy Valentine’s Day 💘</h2>
      <p>Tap below to unlock your surprise</p>
      <button onclick="startPuzzle()">Start 💌</button>
    </div>

    <!-- Puzzle -->
    <div id="puzzle" class="hidden">
      <h3>❤️ Valentine Puzzle ❤️</h3>
      <p>
        I’m not a phone, but I ring.<br>
        I’m not a door, but I open hearts.<br><br>
        What am I?
      </p>
      <input id="answer" placeholder="Type your answer">
      <button onclick="checkAnswer()">Submit 💕</button>
      <p id="feedback"></p>
    </div>

    <!-- Success -->
    <div id="success" class="hidden">
      <h2>💖 You Got It 💖</h2>
      <p>
        The answer is <strong>LOVE</strong> ❤️<br><br>
        Which brings me to this…
      </p>
      <button onclick="showValentine()">Will you be my Valentine? 🥰</button>
    </div>

    <!-- Final -->
    <div id="final" class="hidden">
      <h2>🥰 Yayyyy 🥰</h2>
      <p>
        Best answer ever ❤️<br>
        Happy Valentine’s Day 💘
      </p>
    </div>

  </div>

  <script>
    function startPuzzle() {
      document.getElementById("start").classList.add("hidden");
      document.getElementById("puzzle").classList.remove("hidden");
    }

    function checkAnswer() {
      const answer = document.getElementById("answer").value.trim().toLowerCase();
      const feedback = document.getElementById("feedback");

      if (answer === "love") {
        document.getElementById("puzzle").classList.add("hidden");
        document.getElementById("success").classList.remove("hidden");
      } else {
        feedback.innerText = "❌ Try again… you got this 💕";
      }
    }

    function showValentine() {
      document.getElementById("success").classList.add("hidden");
      document.getElementById("final").classList.remove("hidden");
    }
  </script>

</body>
</html>
