<!DOCTYPE html><html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Untukmu ❤️</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      overflow: hidden;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      color: #fff;
    }
    .card {
      background: rgba(0,0,0,0.4);
      padding: 40px;
      border-radius: 25px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.3);
      text-align: center;
      z-index: 10;
    }
    h1 {
      font-size: 2.5rem;
      margin-bottom: 20px;
      animation: fadeIn 2s ease-in-out;
    }
    #typed-text {
      font-size: 1.3rem;
      min-height: 60px;
    }
    button {
      margin-top: 20px;
      padding: 12px 25px;
      border: none;
      border-radius: 20px;
      background: #ff5e78;
      color: white;
      font-size: 1.1rem;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background: #ff2a50;
    }
    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }
    .heart {
      position: absolute;
      color: rgba(255,255,255,0.7);
      font-size: 20px;
      animation: floatUp 5s linear infinite;
    }
    @keyframes floatUp {
      0% {transform: translateY(0) scale(1); opacity: 1;}
      100% {transform: translateY(-100vh) scale(1.5); opacity: 0;}
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Hai, aku ada sesuatu untukmu...</h1>
    <button onclick="startConfession()">Klik di sini ❤️</button>
    <p id="typed-text"></p>
  </div>  <!-- Musik romantis -->  <audio id="bg-music" autoplay loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_1e1a3e67ba.mp3?filename=romantic-piano-112194.mp3" type="audio/mpeg">
  </audio>  <script>
    function startConfession() {
      const text = "Aku sayang kamu... maukah kamu jadi bagian terpenting dalam hidupku? 💖";
      let i = 0;
      const speed = 70;
      const output = document.getElementById("typed-text");
      output.innerHTML = "";
      function typeWriter() {
        if (i < text.length) {
          output.innerHTML += text.charAt(i);
          i++;
          setTimeout(typeWriter, speed);
        }
      }
      typeWriter();

      // Mulai musik jika belum berjalan
      const music = document.getElementById("bg-music");
      music.play();
    }

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "❤";
      document.body.appendChild(heart);

      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = Math.random() * 20 + 10 + "px";
      heart.style.animationDuration = (Math.random() * 3 + 3) + "s";

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    setInterval(createHeart, 400);
  </script></body>
</html>
