<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>For You 🩷</title>
  <style>
    body {
      background: linear-gradient(to bottom right, #ffe4ec, #fff9c4);
      font-family: 'Comic Sans MS', cursive, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      padding: 40px 20px;
      min-height: 100vh;
      box-sizing: border-box;
      overflow-y: auto;
    }

    h1, p {
      color: #ff69b4;
    }

    #message {
      font-size: 2em;
      margin-bottom: 20px;
      transition: all 0.4s ease;
    }

    .cute-button {
      padding: 15px 25px;
      font-size: 1.2em;
      background-color: #ffd1dc;
      border: 2px solid #ff9aa2;
      border-radius: 30px;
      color: #fff;
      font-weight: bold;
      cursor: pointer;
      animation: bounce 1.5s infinite;
      transition: transform 0.3s ease;
      box-shadow: 0 6px 12px rgba(255, 153, 204, 0.4);
    }

    .cute-button:hover {
      transform: scale(1.05);
      background-color: #ffb7c5;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-6px); }
    }

    .gif {
      width: 130px;
      margin: 15px;
      border-radius: 15px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }

    #gifContainer {
      display: none;
      flex-wrap: wrap;
      justify-content: center;
    }

    #poem {
      display: none;
      margin-top: 20px;
      background: rgba(255, 255, 255, 0.7);
      border-radius: 20px;
      padding: 20px;
      color: #d63384;
      font-size: 1.2em;
      line-height: 1.6;
      max-width: 500px;
      animation: fadeInFloat 3s ease-in-out forwards;
    }

    @keyframes fadeInFloat {
      0% {
        opacity: 0;
        transform: translateY(50px);
      }
      100% {
        opacity: 1;
        transform: translateY(0);
      }
    }

    canvas {
      position: fixed;
      top: 0;
      left: 0;
      pointer-events: none;
      z-index: 9999;
    }
  </style>
</head>
<body>

  <h1 id="message">heyy heroo 🥹</h1>
  <button id="clickMe" class="cute-button">pleek clickk me 🥺👉👈</button>

  <div id="gifContainer">
    <!-- Cat GIFs -->
    <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExODZzZTQzbjZmeXFrYjF0ZHZsdWEyenBsdnY5cWZlYjZwczY0Y2Y3YSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/o3dftQFlgWBuhYnYZ8/giphy.gif" class="gif" alt="clingy cat" />
    <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExaWJ0eW10MXp0bjZiNjJodWMxMnJlNThsc3E4M2NyOHQ3MndpYnRsaSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/tw3OO1YvilPIBrlaRC/giphy.gif" class="gif" alt="clingy cat" />
    <img src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif" class="gif" alt="hug cat" />
  </div>

  <!-- Poem -->
  <div id="poem">
    <p>
      my day begins<br>
      with a thought of you—<br>
      like sunshine<br>
      sneaking through sleepy skies.<br><br>

      and somewhere between<br>
      messages, smiles,<br>
      and silent stares,<br>
      you stay.<br><br>

      it ends the same way—<br>
      with a heart a little lighter,<br>
      a grin i didn’t plan,<br>
      and your name<br>
      still softly resting<br>
      in my mind.<br><br>

      hehe have a nice day 💫
    </p>
  </div>

  <!-- Confetti Script -->
  <canvas id="confetti"></canvas>
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

  <script>
    const message = document.getElementById("message");
    const button = document.getElementById("clickMe");
    const gifContainer = document.getElementById("gifContainer");
    const poem = document.getElementById("poem");

    const steps = [
      "ready for a surprise? 💌",
      "click again heehee 😚",
      "one more? just for me 🥺",
      "okay okay noww waittt 😆",
      "TADAA! 🫶🏽"
    ];

    let clickCount = 0;

    button.addEventListener("click", () => {
      if (clickCount < steps.length) {
        message.textContent = steps[clickCount];
        clickCount++;
      } else {
        button.style.display = "none";
        message.textContent = "this one's for you 💛";
        gifContainer.style.display = "flex";
        poem.style.display = "block";

        // 🎉 Launch confetti when poem appears!
        confetti({
          particleCount: 150,
          spread: 100,
          origin: { y: 0.6 }
        });
      }
    });
  </script>

</body>
</html>
