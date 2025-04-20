<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Choose Your Quote</title>
  <style>
    body {
      background: linear-gradient(135deg, #000428, #004e92);
      color: white;
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
      padding: 50px;
    }

    button {
      background-color: #fff;
      color: #004e92;
      padding: 15px 25px;
      margin: 10px;
      border: none;
      border-radius: 10px;
      font-size: 1.2em;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background-color: #004e92;
      color: white;
    }

    .quote-box {
      margin-top: 30px;
      font-size: 1.5em;
      font-style: italic;
      max-width: 800px;
      margin-left: auto;
      margin-right: auto;
    }

    input[type="number"] {
      padding: 10px;
      font-size: 1em;
      border-radius: 10px;
      border: none;
      width: 60px;
      margin: 20px 0;
    }
  </style>
</head>
<body>

<h1>Do you want a quote?</h1>

<div id="options">
  <button onclick="selectYes()">Yes</button>
  <button onclick="selectNo()">No</button>
</div>

<div id="step2"></div>
<div id="quoteBox" class="quote-box"></div>

<script>
  const quotes = [
    "The best time to start was yesterday. The next best time is now.",
    "Be yourself; everyone else is already taken.",
    "Success is not final, failure is not fatal: it is the courage to continue that counts.",
    "Dream big and dare to fail.",
    "Turn your wounds into wisdom.",
    "You miss 100% of the shots you don’t take.",
    "Stars can’t shine without darkness.",
    "In the middle of every difficulty lies opportunity.",
    "Don’t count the days, make the days count.",
    "Do what you can, with what you have, where you are.",
    "Everything you can imagine is real.",
    "If you’re going through hell, keep going.",
    "Life is short, smile while you still have teeth.",
    "Make each day your masterpiece.",
    "Whatever you are, be a good one.",
    "Stay hungry. Stay foolish.",
    "The harder you work for something, the greater you’ll feel when you achieve it.",
    "Don’t watch the clock; do what it does. Keep going.",
    "Push yourself, because no one else is going to do it for you.",
    "Sometimes later becomes never. Do it now.",
    "Little things make big days.",
    "It always seems impossible until it’s done.",
    "The only limit to our realization of tomorrow is our doubts of today.",
    "Happiness is not by chance, but by choice."
  ];

  function selectYes() {
    document.getElementById("options").style.display = "none";
    document.getElementById("step2").innerHTML = `
      <p>Select a number from 1 to 24:</p>
      <input type="number" id="quoteNumber" min="1" max="24">
      <button onclick="showSelectedQuote()">Get Quote</button>
    `;
  }

  function showSelectedQuote() {
    const num = parseInt(document.getElementById("quoteNumber").value);
    const quoteBox = document.getElementById("quoteBox");

    if (num >= 1 && num <= 24) {
      quoteBox.innerHTML = `"${quotes[num - 1]}"`;
    } else {
      quoteBox.innerHTML = "Please enter a number between 1 and 24.";
    }
  }

  function selectNo() {
    document.getElementById("options").style.display = "none";
    document.getElementById("step2").innerHTML = `
      <p>Why not?</p>
      <button onclick="randomQuote()">I'm afraid</button>
      <button onclick="randomQuote()">Not interested</button>
    `;
  }

  function randomQuote() {
    const randomIndex = Math.floor(Math.random() * quotes.length);
    document.getElementById("step2").innerHTML = '';
    document.getElementById("quoteBox").innerHTML = `"${quotes[randomIndex]}"`;
  }
</script>

</body>
</html>
