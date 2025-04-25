
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>r🌑dt66</title>
    <style>
        body {
            margin: 0;
            background: black;
            color: white;
            font-family: Arial, sans-serif;
            overflow: hidden;
        }
        #dot {
            width: 8px;
            height: 8px;
            background: white;
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        #agePrompt, #colorPrompt {
            display: none;
            text-align: center;
            margin-top: 50px;
        }
        .color-option {
            margin: 10px;
            padding: 10px 20px;
            background: gray;
            display: inline-block;
            cursor: pointer;
            border-radius: 10px;
        }
    </style>
</head>
<body>

<div id="dot"></div>

<div id="agePrompt">
    <p>Before we begin... how many seasons have you seen?</p>
    <input type="number" id="ageInput" placeholder="Enter your age">
    <button id="ageContinue">Continue</button>
</div>

<div id="colorPrompt">
    <p>Choose your favorite color</p>
    <div class="color-option" data-color="red">Red</div>
    <div class="color-option" data-color="blue">Blue</div>
    <div class="color-option" data-color="green">Green</div>
    <div class="color-option" data-color="purple">Purple</div>
</div>

<script>
    const dot = document.getElementById('dot');
    const agePrompt = document.getElementById('agePrompt');
    const ageInput = document.getElementById('ageInput');
    const colorPrompt = document.getElementById('colorPrompt');
    const ageContinue = document.getElementById('ageContinue');

    dot.addEventListener('click', () => {
        dot.style.display = 'none';
        agePrompt.style.display = 'block';
    });

    ageContinue.addEventListener('click', () => {
        if (ageInput.value) {
            agePrompt.style.display = 'none';
            colorPrompt.style.display = 'block';
        }
    });

    document.querySelectorAll('.color-option').forEach(option => {
        option.addEventListener('click', () => {
            const color = option.getAttribute('data-color');
            window.location.href = `${color}.html`; // you can create red.html, blue.html etc.
        });
    });
</script>

</body>
</html>
          
      



  
