<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>The Dot Portal</title>
  <style>
    body {
      margin: 0;
      background-color: black;
      color: white;
      font-family: 'Arial', sans-serif;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      flex-direction: column;
    }
    #dot {
      width: 10px;
      height: 10px;
      background-color: white;
      border-radius: 50%;
    }
    .hidden {
      display: none;
    }
    .prompt {
      text-align: center;
    }
    .color-option {
      margin: 10px;
      padding: 10px 20px;
      border: 2px solid white;
      display: inline-block;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <div id="dot"></div>

  <div id="agePrompt" class="hidden prompt">
    <p>Before we begin... how many seasons have you seen?</p>
    <input type="number" id="ageInput">
    <button id="ageContinue">Continue</button>
  </div>

  <div id="colorPrompt" class="hidden prompt">
    <p>Choose your favorite color:</p>
    <div class="color-option" data-color="red">Red</div>
    <div class="color-option" data-color="blue">Blue</div>
    <div class="color-option" data-color="green">Green</div>
  </div>

  <script>
    const dot = document.getElementById("dot");
    const agePrompt = document.getElementById("agePrompt");
    const colorPrompt = document.getElementById("colorPrompt");
    const ageInput = document.getElementById("ageInput");

    document.body.addEventListener("click", () => {
      dot.classList.add("hidden");
      agePrompt.classList.remove("hidden");
    }, { once: true });

    ageInput.addEventListener("keypress", function (e) {
      if (e.key === "Enter" && ageInput.value) {
        agePrompt.classList.add("hidden");
        colorPrompt.classList.remove("hidden");
      }
    });

    document.getElementById("ageContinue").addEventListener("click", () => {
      if (ageInput.value) {
        agePrompt.classList.add("hidden");
        colorPrompt.classList.remove("hidden");
      }
    });

    document.querySelectorAll(".color-option").forEach(color => {
      color.addEventListener("click", () => {
        const selectedColor = color.getAttribute("data-color");
        window.location.href = `${selectedColor}.html`;
      });
    });
  </script>

</body>
</html>

