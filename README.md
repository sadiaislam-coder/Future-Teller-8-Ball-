<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Magic 8 Ball</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to right, #1f1c2c, #928dab);
      color: white;
      text-align: center;
      padding: 40px;
    }
    h1 {
      margin-bottom: 20px;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
      margin: 10px;
      border-radius: 8px;
      border: none;
    }
    #answer {
      margin-top: 30px;
      font-size: 24px;
      font-weight: bold;
      color: #ffda79;
    }
    .ball {
      margin: 20px auto;
      width: 120px;
      height: 120px;
      background: black;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 28px;
      color: white;
      box-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
    }
  </style>
</head>
<body>

  <h1>Ask the Magic 8 Ball</h1>
  <input type="text" id="question" placeholder="Ask your question..." size="40">
  <button onclick="shakeBall()">Ask</button>

  <div class="ball" id="ball">8</div>
  <div id="answer"></div>

  <script>
    const responses = [
      "Yes, definitely.",
      "No way!",
      "Ask again later.",
      "Absolutely!",
      "I wouldn't count on it.",
      "Signs point to yes.",
      "Very doubtful.",
      "Better not tell you now.",
      "It is certain.",
      "My reply is no."
    ];

    function shakeBall() {
      const question = document.getElementById("question").value.trim();
      const answerDiv = document.getElementById("answer");
      if (question === "") {
        answerDiv.innerText = "Please enter a question.";
        return;
      }

      const randomIndex = Math.floor(Math.random() * responses.length);
      const randomAnswer = responses[randomIndex];
      
      document.getElementById("ball").innerText = "8";
      answerDiv.innerText = "Thinking...";
      
      setTimeout(() => {
        document.getElementById("ball").innerText = "?";
        answerDiv.innerText = randomAnswer;
      }, 1500);
    }
  </script>

</body>
</html>
