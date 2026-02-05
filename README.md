# Valentine
My valentine website 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Pareeshay 💖 Sabtain</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <style>
    body {
      margin: 0;
      font-family: 'Poppins', 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #ffc3d1, #ffe4ec);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .card {
      background: #ffffff;
      border-radius: 25px;
      box-shadow: 0 25px 50px rgba(255, 77, 109, 0.25);
      max-width: 450px;
      width: 90%;
      padding: 30px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .card::before {
      content: "💖 💕 💗 💘 💝";
      position: absolute;
      top: 10px;
      left: 0;
      width: 100%;
      text-align: center;
      opacity: 0.15;
      font-size: 22px;
      letter-spacing: 10px;
    }

    h1 {
      color: #ff4d6d;
      margin-bottom: 5px;
      font-size: 28px;
    }

    .name {
      color: #ff7a90;
      font-weight: 600;
      margin-bottom: 15px;
    }

    .photo {
      width: 100%;
      border-radius: 20px;
      margin: 18px 0;
      box-shadow: 0 10px 25px rgba(0,0,0,0.15);
    }

    .message {
      font-size: 15.5px;
      color: #555;
      line-height: 1.7;
      margin: 20px 0;
    }

    h2 {
      color: #ff4d6d;
      margin-top: 10px;
      margin-bottom: 20px;
    }

    .buttons {
      display: flex;
      gap: 15px;
      justify-content: center;
      flex-wrap: wrap;
    }

    button {
      padding: 14px 26px;
      border: none;
      border-radius: 30px;
      font-size: 16px;
      cursor: pointer;
      transition: all 0.25s ease;
    }

    .yes {
      background: linear-gradient(135deg, #ff4d6d, #ff8fa3);
      color: white;
      box-shadow: 0 10px 20px rgba(255,77,109,0.4);
    }

    .yes:hover {
      transform: scale(1.08);
    }

    .no {
      background: #f2f2f2;
      color: #666;
    }

    .no:hover {
      transform: translateX(12px);
    }

    .success {
      display: none;
      margin-top: 25px;
      font-size: 18px;
      color: #ff4d6d;
      font-weight: 600;
      line-height: 1.6;
    }

    .hearts {
      position: fixed;
      inset: 0;
      pointer-events: none;
      overflow: hidden;
    }

    .heart {
      position: absolute;
      animation: floatUp 6s linear infinite;
      opacity: 0.8;
    }

    @keyframes floatUp {
      from {
        transform: translateY(100vh) scale(1);
        opacity: 0.9;
      }
      to {
        transform: translateY(-10vh) scale(1.6);
        opacity: 0;
      }
    }

    .music-note {
      font-size: 12px;
      color: #999;
      margin-top: 8px;
    }
  </style>
</head>
<body>

  <!-- BACKGROUND MUSIC (YouTube Embed - Mast Magan) -->
  <!-- NOTE: Autoplay may require user interaction on some phones -->
  <iframe 
    width="0" 
    height="0" 
    src="https://www.youtube.com/embed/Jc5h4Pr0u0I?autoplay=1&loop=1&playlist=Jc5h4Pr0u0I"
    frameborder="0"
    allow="autoplay"
    allowfullscreen>
  </iframe>

  <div class="card">
    <h1>Pareeshay 💕</h1>
    <div class="name">From Sabtain, with all my love 💖</div>

    <!-- CHANGE TO YOUR OWN PHOTO -->
    <img 
      src="https://images.unsplash.com/photo-1529626455594-4ff0802cfb7e" 
      alt="Us" 
      class="photo"
    />

    <div class="message">
      To the most beautiful girl in this world, to the most amazing, gorgeous girl —  
      the angel in my life, the person I can die for… 💗  
      <br><br>
      I love youuu so much. You’re the most cutiest baby ever.  
      The way you melt my heart, no one does.  
      I loveuuu you so much and I will loveuuu you forever.  
      <br><br>
      You are my happiness, my peace, and my favorite person. Always. 💕
    </div>

    <h2>Will you be my Valentine, Pareeshay? 🌹</h2>

    <div class="buttons">
      <button class="yes" onclick="sayYes()">YES 💘</button>
      <button class="no" onmouseover="moveNo()">No 🙈</button>
    </div>

    <div class="success" id="successMessage">
      AHHHH 😍💖  
      Pareeshay said YES!!!  
      Sabtain is officially the luckiest guy ever 😭💕  
      I promise to make this Valentine’s Day full of love, smiles,
      and unforgettable moments with you 🌹✨
    </div>

    <div class="music-note">
      🎵 Playing: Mast Magan — Arijit Singh
    </div>
  </div>

  <div class="hearts" id="hearts"></div>

  <script>
    function sayYes() {
      document.getElementById("successMessage").style.display = "block";
      createHearts();
    }

    function moveNo() {
      const btn = document.querySelector('.no');
      const x = Math.random() * 120 - 60;
      const y = Math.random() * 60 - 30;
      btn.style.transform = `translate(${x}px, ${y}px)`;
    }

    function createHearts() {
      const heartsContainer = document.getElementById('hearts');

      for (let i = 0; i < 40; i++) {
        const heart = document.createElement('div');
        heart.classList.add('heart');
        heart.innerHTML = '💖';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.fontSize = (16 + Math.random() * 26) + 'px';
        heart.style.animationDuration = (4 + Math.random() * 4) + 's';

        heartsContainer.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 8000);
      }
    }
  </script>

</body>
</html>
