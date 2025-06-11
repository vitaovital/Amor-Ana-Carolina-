
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Amor da minha vida</title>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Open+Sans&display=swap" rel="stylesheet" />
  <style>
    body {
      background: linear-gradient(to right, #ffe1e1, #ffd1dc);
      font-family: 'Open Sans', sans-serif;
      color: #4a1c40;
      text-align: center;
      padding: 2rem;
      opacity: 0;
      animation: fadeIn 2s ease forwards;
      overflow-x: hidden;
    }

    @keyframes fadeIn {
      to { opacity: 1; }
    }

    h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 3rem;
      color: #d81b60;
      white-space: nowrap;
      overflow: hidden;
      border-right: 3px solid #d81b60;
      animation: typing 3s steps(30, end) forwards, blink 0.75s step-end infinite;
      margin-bottom: 2rem;
    }

    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }

    @keyframes blink {
      50% { border-color: transparent; }
    }

    p {
      font-size: 1.2rem;
      max-width: 800px;
      margin: 1rem auto;
      line-height: 1.6;
    }

    .date, .quote, .counter {
      font-weight: bold;
      margin-top: 1rem;
      color: #880e4f;
    }

    button {
      margin-top: 2rem;
      padding: 0.6rem 1.2rem;
      font-size: 1rem;
      border: none;
      background-color: #d81b60;
      color: white;
      border-radius: 12px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #ad1457;
    }

    #secret-message, #poem {
      display: none;
      margin-top: 1rem;
      font-style: italic;
      color: #6a1b4d;
      animation: fadeInText 2s ease forwards;
    }

    @keyframes fadeInText {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .heart {
      position: fixed;
      font-size: 2rem;
      animation: floatUp 10s linear infinite;
      opacity: 0.6;
      pointer-events: none;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) scale(1);
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
      }
    }

    .final-message {
      margin-top: 2rem;
      font-family: 'Great Vibes', cursive;
      font-size: 2rem;
      color: #b71c1c;
      animation: fadeInText 3s ease forwards;
    }
  </style>
</head>
<body>
  <h1>Amor da minha vida</h1>

  <section>
    <p>Uma coisinha especial para uma mulher incrível que posso chamar de namorada. Nunca em minha vida imaginei ser amado dessa forma como você me ama.</p>

    <p>Penso para mim que nada é por acaso, e a forma como o destino uniu eu a você foi incrível. Não canso de me lembrar que nesse dia eu ia ir embora, mas resolvi ficar. Passei na lanchonete, fiquei fazendo uma média... e tudo aconteceu.</p>

    <p>Saio e tem uma mensagem sua. Não foi bem você que mandou, mas era sua. O importante é que deu certo. Inicialmente, tive receio e medo de que você só queria zoar com a minha cara. Porém, com o passar do tempo, eu vi que não.</p>

    <p>Com menos de duas semanas conversando e ficando com você, eu já tinha certeza do que eu queria. Hoje tenho essa menina incrível ao meu lado: linda, inteligente, educada, de uma família linda. Não me entra na cabeça o fato daquele bunda mole ter te traído. Mas agradeço por isso, porque graças a isso tenho você comigo.</p>

    <p>A vida com você tem um brilho. Você é o amor da minha vida — e espero que seja para todo o sempre.</p>
  </section>

  <div class="date">Namorando desde: 23/03/2025</div>
  <div class="counter" id="days-counter"></div>
  <div class="quote">"Amo amar você e viver você"</div>

  <button onclick="revealMessage()">Clique para uma surpresa 💌</button>
  <div id="secret-message">Você é o maior presente que a vida me deu. Te amo infinitamente 💖</div>

  <button onclick="showPoem()">Ver um poema 💘</button>
  <div id="poem"></div>

  <div class="final-message">Com amor, do seu eterno namorado ❤️</div>

  <audio id="music" autoplay loop>
    <source src="musica/sua-musica.mp3" type="audio/mpeg">
    Seu navegador não suporta áudio HTML.
  </audio>

  <script>
    const hearts = ["💕", "💖", "💘", "💝", "💞"];
    for (let i = 0; i < 25; i++) {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDelay = (Math.random() * 10) + "s";
      heart.innerText = hearts[Math.floor(Math.random() * hearts.length)];
      document.body.appendChild(heart);
    }

    const startDate = new Date("2025-03-23");
    const today = new Date();
    const diffTime = today - startDate;
    const diffDays = Math.floor(diffTime / (1000 * 60 * 60 * 24));
    document.getElementById("days-counter").innerText = `Estamos juntos há ${diffDays} dias!`;

    function revealMessage() {
      const msg = document.getElementById("secret-message");
      msg.style.display = msg.style.display === "none" ? "block" : "none";
    }
<audio controls>
  <source src="sua-musica.mp3" type="audio/mpeg">
</audio>
    function showPoem() {
      const poem = document.getElementById("poem");
      const lines = [
        "Nos teus olhos vejo o mundo 🌍",
        "No teu riso, meu abrigo 😄",
        "No teu toque, o paraíso ✨",
        "Em teu amor, eu sigo 💑"
      ];
      poem.innerHTML = "";
      let i = 0;
      function revealLine() {
        if (i < lines.length) {
          const line = document.createElement("p");
          line.innerText = lines[i];
          poem.appendChild(line);
          i++;
          setTimeout(revealLine, 1500);
        }
      }
      poem.style.display = "block";
      revealLine();
    }
  </script>
</body>
</html>
