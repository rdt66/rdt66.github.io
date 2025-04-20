<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Whispering Page</title>
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
      font-family: 'EB Garamond', serif;
      color: #ffffff;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      flex-direction: column;
      transition: background 1s ease;
    }

    .quote-box {
      text-align: center;
      max-width: 80%;
      font-size: 1.5rem;
      margin-bottom: 20px;
      display: none;
      animation: fadeIn 2s forwards;
    }

    .intro-line {
      font-size: 1.7rem;
      text-align: center;
      opacity: 0;
      animation: fadeIn 3s forwards;
    }

    .reveal-button, .next-button {
      margin-top: 20px;
      padding: 12px 24px;
      background-color: rgba(255, 255, 255, 0.1);
      border: 1px solid #ffffff;
      color: #ffffff;
      font-size: 1rem;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    .reveal-button:hover, .next-button:hover {
      background-color: rgba(255, 255, 255, 0.3);
    }

    .signature {
      position: absolute;
      bottom: 15px;
      font-size: 0.9rem;
      opacity: 0.6;
      text-align: center;
    }

    @keyframes fadeIn {
      to {
        opacity: 1;
      }
    }
  </style>
</head>
<body>
  <div class="intro-line" id="intro">Every soul carries a quote it never speaks out loud...</div>
  <button class="reveal-button" id="revealBtn">Reveal the Whisper</button>

  <div class="quote-box" id="quoteBox"></div>
  <button class="next-button" id="nextBtn" style="display:none;">Next Whisper</button>

  <div class="signature">Brewed in silence. Inspired by sky, roots, and a cup of blue tea.</div>

  <script>
    const quotes = [
      "Sometimes, silence is the loudest scream.",
      "The roots remember what the branches forget.",
      "There’s magic in the unseen, whispered between stars.",
      "A quote unspoken is still a song inside the soul.",
      "We are made of stories we never tell anyone."
    ];

    const quoteBox = document.getElementById("quoteBox");
    const revealBtn = document.getElementById("revealBtn");
    const nextBtn = document.getElementById("nextBtn");
    const intro = document.getElementById("intro");

    function getRandomQuote() {
      return quotes[Math.floor(Math.random() * quotes.length)];
    }

    function showQuote() {
      quoteBox.style.display = "block";
      quoteBox.textContent = '';
      const quote = getRandomQuote();
      let i = 0;
      const typewriter = setInterval(() => {
        quoteBox.textContent += quote.charAt(i);
        i++;
        if (i > quote.length - 1) clearInterval(typewriter);
      }, 50);
    }

    revealBtn.addEventListener("click", () => {
      intro.style.display = "none";
      revealBtn.style.display = "none";
      showQuote();
      nextBtn.style.display = "inline-block";
    });

    nextBtn.addEventListener("click", showQuote);
  </script>
</body>
</html>
