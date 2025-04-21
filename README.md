<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Portal Experience</title>
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond&display=swap" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      background-color: #000;
      font-family: 'EB Garamond', serif;
      color: white;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      overflow: hidden;
    }

    #dot {
      width: 10px;
      height: 10px;
      background-color: white;
      border-radius: 50%;
      animation: pulse 2s infinite;
      cursor: pointer;
    }

    @keyframes pulse {
      0% { transform: scale(1); opacity: 0.5; }
      50% { transform: scale(1.3); opacity: 1; }
      100% { transform: scale(1); opacity: 0.5; }
    }

    .hidden {
      display: none;
    }

    .question-box {
      text-align: center;
      max-width: 90%;
    }

    input, button {
      margin-top: 20px;
      padding: 10px;
      font-size: 1rem;
    }

    .color-option {
      margin: 10px;
      width: 80px;
      height: 80px;
      border-radius: 50%;
      border: 2px solid white;
      cursor: pointer;
      display: inline-block;
    }
  </style>
</head>
<body>

  <div id="dot"></div>

  <div id="agePrompt" class="question-box hidden">
    <div>Before we begin... how many seasons have you seen?</div>
    <input type="number" id="ageInput" placeholder="Enter your age" />
  </div>

  <div id="colorPrompt" class="question-box hidden">
    <div>Select your favorite color:</div>
    <div>
      <div class="color-option" style="background: #3498db" data-color="blue"></div>
      <div class="color-option" style="background: #e74c3c" data-color="red"></div>
      <div class="color-option" style="background: #2ecc71" data-color="green"></div>
      <div class="color-option" style="background: #9b59b6" data-color="purple"></div>
    </div>
  </div>

  <script>
    const dot = document.getElementById("dot");
    const agePrompt = document.getElementById("agePrompt");
    const colorPrompt = document.getElementById("colorPrompt");
    const ageInput = document.getElementById("ageInput");

    dot.addEventListener("click", () => {
      dot.classList.add("hidden");
      agePrompt.classList.remove("hidden");
    });

    ageInput.addEventListener("keypress", function (e) {
      if (e.key === "Enter" && ageInput.value) {
        agePrompt.classList.add("hidden");
        colorPrompt.classList.remove("hidden");
      }
    });

    document.querySelectorAll(".color-option").forEach(color => {
      color.addEventListener("click", () => {
        const selectedColor = color.getAttribute("data-color");
        // Redirect to themed page (to be created)
        window.location.href = `${selectedColor}.html`;
      });
    });
  </script>
</body>
</html>
