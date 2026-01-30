<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>TweedGPT</title>

  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=IM+Fell+English&display=swap" rel="stylesheet">

  <style>
    body {
      margin: 0;
      font-family: 'IM Fell English', serif;
      background: #2b1f14;
      color: #2a1c10;
      height: 100vh;
      overflow: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background: rgba(112, 66, 20, 0.25);
      pointer-events: none;
    }

    body::after {
      content: "";
      position: fixed;
      inset: 0;
      background: rgba(255, 230, 180, 0.04);
      animation: flicker 4s infinite;
      pointer-events: none;
    }

    @keyframes flicker {
      0%, 100% { opacity: 0.03; }
      50% { opacity: 0.08; }
      60% { opacity: 0.02; }
      70% { opacity: 0.06; }
    }

    header {
      background: #e6d3a3;
      border-bottom: 2px solid #3a2a1a;
      padding: 15px;
      text-align: center;
    }

    .company {
      font-size: 16px;
    }

    .title {
      font-size: 36px;
      letter-spacing: 2px;
    }

    .chat-container {
      max-width: 800px;
      margin: 40px auto;
      background: #f1e2b8;
      border: 3px solid #3a2a1a;
      padding: 20px;
      box-shadow: 0 0 40px rgba(0,0,0,0.4);
    }

    .chat-log {
      height: 300px;
      overflow-y: auto;
      padding: 10px;
      border: 2px solid #3a2a1a;
      background: #f7ecd1;
      margin-bottom: 15px;
    }

    .user {
      font-weight: bold;
      margin-bottom: 6px;
    }

    .bot {
      margin-top: 10px;
    }

    .input-area {
      display: flex;
      gap: 10px;
    }

    input {
      flex: 1;
      padding: 10px;
      font-family: inherit;
      font-size: 16px;
      border: 2px solid #3a2a1a;
      background: #fff6dc;
    }

    button {
      padding: 10px 20px;
      font-family: inherit;
      font-size: 16px;
      background: #3a2a1a;
      color: #f7ecd1;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background: #2a1c10;
    }
  </style>
</head>

<body>

<header>
  <div class="company">Tweed and Company</div>
  <div class="title">TweedGPT</div>
</header>

<div class="chat-container">
  <div class="chat-log" id="chatLog"></div>

  <div class="input-area">
    <input id="userInput" type="text" placeholder="Speak to BOSS Tweed...">
    <button id="sendBtn">Send</button>
  </div>
</div>

<audio id="typeSound" src="typewriter.mp3"></audio>

<script>
  const responses = [
    "BOOM. Get TWEEDED.",
    "You thought it was a bird. Its just your BOSS.",
    "This is BOSS Tweed speaking. The money is in my pocket.",
    "Tweed did not steal. BOSS borrowed permanently.",
    "Elections are simple when BOSS counts the votes.",
    "Never question BOSS Tweed. The math is done.",
    "Corrupt is just another word for creative.",
    "67",
    "41",
    "GRRRR"
  ];

  const ending = " Go study or ask Mrs Rodino.";

  const chatLog = document.getElementById("chatLog");
  const input = document.getElementById("userInput");
  const button = document.getElementById("sendBtn");
  const sound = document.getElementById("typeSound");

  function sendMessage() {
    if (input.value.trim() === "") return;

    chatLog.innerHTML += "<div class='user'>You: " + input.value + "</div>";
    input.value = "";

    const reply = responses[Math.floor(Math.random() * responses.length)] + ending;

    setTimeout(() => typeReply(reply), 400);
  }

  function typeReply(text) {
    let i = 0;
    const line = document.createElement("div");
    line.className = "bot";
    line.innerHTML = "<strong>BOSS TWEED:</strong> ";
    chatLog.appendChild(line);

    sound.currentTime = 0;
    sound.play();

    const interval = setInterval(() => {
      if (i < text.length) {
        line.innerHTML += text.charAt(i);
        chatLog.scrollTop = chatLog.scrollHeight;
        i++;
      } else {
        clearInterval(interval);
        sound.pause();
      }
    }, 35);
  }

  button.addEventListener("click", sendMessage);
  input.addEventListener("keydown", function(e) {
    if (e.key === "Enter") sendMessage();
  });
</script>

</body>
</html>
