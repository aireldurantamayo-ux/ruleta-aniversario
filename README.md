<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Reluta de premios 💘</title>

<style>
  body {
    margin: 0;
    font-family: 'Arial', sans-serif;
    text-align: center;
    background: linear-gradient(#ffd6e8, #fff);
    overflow: hidden;
  }

  h1 {
    margin-top: 30px;
    color: #c9184a;
  }

  p {
    color: #6a040f;
    font-size: 18px;
    margin: 10px 20px;
  }

  .ruleta {
    width: 220px;
    height: 220px;
    border-radius: 50%;
    border: 10px solid #ff4d6d;
    margin: 30px auto;
    background: conic-gradient(
      #ffccd5 0deg 90deg,
      #ff8fab 90deg 180deg,
      #ffccd5 180deg 270deg,
      #ff8fab 270deg 360deg
    );
    transition: transform 4s ease-out;
  }

  button {
    padding: 14px 24px;
    font-size: 18px;
    border: none;
    border-radius: 25px;
    background: #ff4d6d;
    color: white;
    cursor: pointer;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  }

  #resultado {
    margin-top: 25px;
    font-size: 22px;
    font-weight: bold;
    color: #9d0208;
  }

  /* FLORES */
  .flower {
    position: fixed;
    top: -50px;
    font-size: 24px;
    animation: fall linear infinite;
  }

  @keyframes fall {
    to {
      transform: translateY(110vh);
    }
  }
</style>
</head>

<body>

<h1>🎡 Reluta de premios<br>For my precious love 💖</h1>

<p>Feliz primer año y aniversario mi amor.<br>
Elije el pozo de premios MLBB 💘</p>

<div class="ruleta" id="ruleta"></div>

<button onclick="girar()">Girar 💝</button>

<div id="resultado"></div>

<script>
  const premios = [
    "🎮 Nolan Skin Epic",
    "👑 VIP Hilda",
    "✨ Skin a desear",
    "💌 Carta romántica"
  ];

  function girar() {
    const ruleta = document.getElementById("ruleta");
    const resultado = document.getElementById("resultado");

    const grados = Math.floor(Math.random() * 360) + 1440;
    ruleta.style.transform = `rotate(${grados}deg)`;

    const premio = premios[Math.floor(Math.random() * premios.length)];

    setTimeout(() => {
      resultado.innerText = "💖 Te tocó: " + premio;
    }, 4000);
  }

  // FLORES CAYENDO
  const flores = ["🌸","🌹","💐","🌷","🌺"];
  setInterval(() => {
    const flor = document.createElement("div");
    flor.className = "flower";
    flor.innerText = flores[Math.floor(Math.random() * flores.length)];
    flor.style.left = Math.random() * 100 + "vw";
    flor.style.animationDuration = (3 + Math.random() * 5) + "s";
    document.body.appendChild(flor);

    setTimeout(() => {
      flor.remove();
    }, 8000);
  }, 500);
</script>

</body>
</html>
