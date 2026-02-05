<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Valentine 💘</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(180deg, #ff9a9e, #fad0c4);
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .card {
      background: white;
      width: 90%;
      max-width: 380px;
      padding: 25px;
      border-radius: 25px;
      text-align: center;
      box-shadow: 0 15px 30px rgba(0,0,0,0.2);
      position: relative;
      z-index: 2;
    }

    h1 {
      color: #ff2f92;
      font-size: 26px;
      margin-bottom: 30px;
    }

    .buttons {
      position: relative;
      height: 90px;
    }

    button {
      border: none;
      padding: 14px 22px;
      font-size: 18px;
      border-radius: 25px;
      cursor: pointer;
    }

    #yes {
      background: #ff2f92;
      color: white;
    }

    #no {
      background: #ffd6e8;
      color: #444;
      position: absolute;
      left: 55%;
      top: 0;
    }

    .balloon {
      position: absolute;
      bottom: -120px;
      width: 45px;
      height: 60px;
      border-radius: 50% 50% 50% 50%;
      opacity: 0.7;
      animation: floatUp 9s linear infinite;
      z-index: 1;
    }

    @keyframes floatUp {
      from { transform: translateY(0); }
      to { transform: translateY(-130vh); }
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Issa du Kelb? 💖</h1>
    <div class="buttons">
      <button id="yes" onclick="sayYes()">Yes 😍</button>
      <button id="no">No 🙃</button>
    </div>
  </div>

  <!-- Balloons -->
  <div class="balloon" style="left:10%; background:#ff6fae; animation-delay:0s"></div>
  <div class="balloon" style="left:30%; background:#ff9acb; animation-delay:2s"></div>
  <div class="balloon" style="left:55%; background:#ffc1dc; animation-delay:4s"></div>
  <div class="balloon" style="left:75%; background:#ff85b3; animation-delay:1s"></div>

  <script>
    const noBtn = document.getElementById('no');
    const btnArea = document.querySelector('.buttons');

    function moveNo() {
      const maxX = btnArea.offsetWidth - noBtn.offsetWidth;
      const maxY = btnArea.offsetHeight - noBtn.offsetHeight;

      const x = Math.random() * maxX;
      const y = Math.random() * maxY;

      noBtn.style.left = x + 'px';
      noBtn.style.top = y + 'px';
    }

    // Mobile + desktop
    noBtn.addEventListener('touchstart', moveNo);
    noBtn.addEventListener('mouseover', moveNo);

    function sayYes() {
      document.body.innerHTML = '<div style="color:white; text-align:center; font-size:32px;">💘 I knew it! Happy Valentine 💘</div>';
    }
  </script>

</body>
</html>
