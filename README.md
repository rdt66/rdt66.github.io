# rdt66.github.io
<!DOCTYPE html>
<html>
<head>
  <title>Quotes for You</title>
</head>
<body style="text-align:center; margin-top:100px; font-family:Arial;">
  <h1>Welcome!</h1>
  <p>Click the button to get a quote:</p>
  <button onclick="showQuote()">Give me a quote</button>
  <p id="quote" style="margin-top:20px;"></p>

  <script>
    const quotes = [
      "Be yourself; everyone else is already taken.",
      "In the middle of difficulty lies opportunity.",
      "Stars can't shine without darkness.",
      "Everything you can imagine is real.",
      "The best way out is always through.",
      "You are stronger than you think.",
      "Don't watch the clock; do what it does. Keep going.",
      "Dream big. Start small. Act now.",
      "Hope is the heartbeat of the soul.",
      "Let your roots grow deep and your dreams fly high.",
      "You become what you believe.",
      "Kindness is a language the deaf can hear and the blind can see.",
      "A journey of a thousand miles begins with a single step.",
      "You only fail when you stop trying.",
      "Light tomorrow with today.",
      "Be the change you want to see in the world.",
      "Fall seven times, stand up eight.",
      "Doubt kills more dreams than failure ever will.",
      "When nothing goes right, go left.",
      "Even the darkest night will end and the sun will rise.",
      "Take only memories, leave only footprints.",
      "Live simply. Dream big. Be grateful. Give love. Laugh lots.",
      "Don't be afraid to shine.",
      "Somewhere, something incredible is waiting to be known."
    ];

    function showQuote() {
      const random = Math.floor(Math.random() * quotes.length);
      document.getElementById("quote").innerText = quotes[random];
    }
  </script>
</body>
</html>
