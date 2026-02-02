<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy Valentine’s Day ❤️</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', sans-serif; }
    body {
      min-height: 100vh;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      overflow: hidden;
    }
    .card {
      background: rgba(255,255,255,0.15);
      backdrop-filter: blur(10px);
      border-radius: 20px;
      padding: 40px;
      max-width: 420px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
      animation: pop 1s ease;
    }
    @keyframes pop {
      from { transform: scale(0.8); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }
    h1 {
      font-size: 2.2rem;
      margin-bottom: 15px;
    }
    p {
      font-size: 1.05rem;
      line-height: 1.6;
      margin-bottom: 25px;
    }
    button {
      background: #fff;
      color: #ff4f81;
      border: none;
      padding: 12px 26px;
      border-radius: 30px;
      font-size: 1rem;
      cursor: pointer;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(0,0,0,0.25);
    }
    .hidden {
      display: none;
      margin-top: 20px;
      font-size: 1.1rem;
    }
    .heart {
      position: absolute;
      bottom: -20px;
      font-size: 20px;
      animation: floatUp 6s linear infinite;
      opacity: 0.7;
    }
    @keyframes floatUp {
      from { transform: translateY(0); opacity: 0; }
      10% { opacity: 0.7; }
      to { transform: translateY(-110vh); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="card" style="display:grid; grid-template-columns: 1fr; gap:20px;">
    <h1 style="grid-column:1/-1;">Happy Valentine’s Day 💖</h1>
    <p style="font-size:1.1rem;">
      One simple question, from the heart.
    </p>
    <div style="display:flex; justify-content:center; gap:15px; margin-top:10px;">
      <button onclick="yesClick()">Yes 💖</button>
      <button id="noBtn" style="background:#ffb3c7; color:#fff;" onmouseover="moveNo()">No 🙈</button>
    </div>
    <div id="msg" class="hidden" style="margin-top:25px; text-align:left;">
      <h2 style="font-size:1.4rem; margin-bottom:10px;">You said YES 💞</h2>
      <p>✨ Thank you for choosing love today.</p>
      <p>🌹 May your days be full of smiles, warmth, and good vibes.</p>
      <p>💫 Here’s to shared laughs, kind moments, and sweet memories.</p>
      <p style="margin-top:12px; font-size:1.2rem; text-align:center;">Happy Valentine’s Day 💖</p>
    </div>
  </div>
    </div>
  </div>

  <script>
    function yesClick() {
      const msg = document.getElementById('msg');
      msg.style.display = 'block';
      // extra heart burst
      for (let i = 0; i < 15; i++) {
        const h = document.createElement('div');
        h.className = 'heart';
        h.innerText = '💖';
        h.style.left = 40 + Math.random() * 20 + 'vw';
        h.style.animationDuration = 3 + Math.random() * 2 + 's';
        document.body.appendChild(h);
        setTimeout(() => h.remove(), 5000);
      }
    }

    function moveNo() {
      const btn = document.getElementById('noBtn');
      btn.style.position = 'absolute';
      btn.style.left = Math.random() * 70 + 'vw';
      btn.style.top = Math.random() * 70 + 'vh';
    }

    // floating hearts
    const hearts = ['❤️','💖','💘','💕','💗'];
    setInterval(() => {
      const h = document.createElement('div');
      h.className = 'heart';
      h.innerText = hearts[Math.floor(Math.random() * hearts.length)];
      h.style.left = Math.random() * 100 + 'vw';
      h.style.animationDuration = 4 + Math.random() * 4 + 's';
      document.body.appendChild(h);
      setTimeout(() => h.remove(), 8000);
    }, 500);
  </script>
</body>
</html>
