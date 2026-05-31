Here is a complete, ready-to-run HTML document that creates a romantic lock screen page. You must type "i love you too" to unlock the music and reveal the main content.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>💖 For You, My Love 💖</title>
  <!-- Poppins Font & smooth feel -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      user-select: none; /* subtle, but won't break typing */
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)),
                  url('https://images.pexels.com/photos/2253870/pexels-photo-2253870.jpeg?auto=compress&cs=tinysrgb&w=1600');
      background-size: cover;
      background-position: center center;
      background-attachment: fixed;
      color: white;
      min-height: 100vh;
      overflow-x: hidden;
      position: relative;
    }

    /* fallback if image fails -> romantic solid overlay */
    @media (max-width: 768px) {
      body {
        background: linear-gradient(135deg, #2b1a2e, #1f1222);
      }
    }

    /* MAIN CONTENT (visible after unlock) */
    .heart-content {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      text-align: center;
      padding: 2rem;
      backdrop-filter: brightness(0.95);
      position: relative;
      z-index: 10;
    }

    .romance-card {
      background: rgba(255, 255, 255, 0.12);
      backdrop-filter: blur(12px);
      border-radius: 60px 30px 60px 30px;
      padding: 3rem 2rem;
      max-width: 700px;
      width: 90%;
      margin: 1rem;
      box-shadow: 0 25px 45px rgba(0,0,0,0.3), 0 0 0 1px rgba(255,255,255,0.2);
      border: 1px solid rgba(255,255,240,0.4);
      transition: all 0.3s ease;
      animation: fadeGlow 1.5s ease-out;
    }

    @keyframes fadeGlow {
      0% { opacity: 0; transform: scale(0.96); backdrop-filter: blur(0px);}
      100% { opacity: 1; transform: scale(1); backdrop-filter: blur(12px);}
    }

    .romance-card h1 {
      font-size: 3rem;
      font-weight: 800;
      background: linear-gradient(135deg, #ffe6f0, #ffb6c7);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      text-shadow: 0 2px 10px rgba(255,80,120,0.4);
      margin-bottom: 1rem;
    }

    .romance-card h2 {
      font-size: 1.9rem;
      font-weight: 600;
      margin: 0.5rem 0;
      letter-spacing: 1px;
    }

    .romance-card p {
      font-size: 1.2rem;
      margin: 1.2rem 0;
      opacity: 0.95;
      font-weight: 400;
      line-height: 1.5;
    }

    .glow-heart {
      font-size: 4rem;
      animation: pulseHeart 1.2s infinite ease;
      display: inline-block;
      margin: 0.5rem 0;
    }

    @keyframes pulseHeart {
      0% { transform: scale(1); text-shadow: 0 0 2px #ff3366;}
      50% { transform: scale(1.2); text-shadow: 0 0 18px #ff6699;}
      100% { transform: scale(1); text-shadow: 0 0 2px #ff3366;}
    }

    /* ----- LOCK SCREEN (full overlay) ----- */
    #lockScreen {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(145deg, #ff4f8b, #ff2d6c, #d43f6b);
      background-attachment: fixed;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 9999;
      backdrop-filter: blur(3px);
      transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
    }

    .lock-box {
      background: rgba(255, 255, 255, 0.98);
      color: #ff3b6f;
      padding: 2.5rem 2rem;
      border-radius: 58px;
      text-align: center;
      width: 90%;
      max-width: 450px;
      box-shadow: 0 30px 50px rgba(0, 0, 0, 0.4), 0 0 0 6px rgba(255,220,240,0.6);
      transition: 0.2s;
      animation: gentleRise 0.6s ease;
    }

    @keyframes gentleRise {
      from { opacity: 0; transform: translateY(25px);}
      to { opacity: 1; transform: translateY(0);}
    }

    .lock-box h2 {
      font-size: 2rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
    }

    .lock-box p {
      color: #b33b5c;
      font-weight: 500;
      margin: 0.5rem 0;
    }

    .lock-box input {
      padding: 14px 16px;
      width: 85%;
      margin: 1.2rem 0 0.5rem;
      border-radius: 60px;
      border: 1.5px solid #ffb7c9;
      font-size: 1rem;
      text-align: center;
      font-family: 'Poppins', monospace;
      transition: 0.2s;
      outline: none;
      color: #a13252;
      font-weight: 500;
    }

    .lock-box input:focus {
      border-color: #ff2d6c;
      box-shadow: 0 0 0 3px rgba(255, 45, 108, 0.3);
    }

    .lock-box button {
      margin-top: 1rem;
      padding: 12px 32px;
      border: none;
      background: #ff4f8b;
      color: white;
      font-weight: bold;
      border-radius: 40px;
      cursor: pointer;
      font-size: 1.1rem;
      font-family: 'Poppins', sans-serif;
      transition: 0.2s;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    }

    .lock-box button:hover {
      background: #ff2060;
      transform: scale(1.02);
      box-shadow: 0 8px 18px rgba(0,0,0,0.25);
    }

    #errorMsg {
      margin-top: 1rem;
      font-size: 0.9rem;
      font-weight: 500;
      color: #c9254f;
      background: rgba(255,200,210,0.5);
      display: inline-block;
      padding: 6px 12px;
      border-radius: 50px;
    }

    /* floating hearts animation */
    .floating-heart {
      position: fixed;
      bottom: -20px;
      pointer-events: none;
      z-index: 999;
      font-size: 1.4rem;
      animation: floatUpLove 5s linear forwards;
      filter: drop-shadow(0 0 4px rgba(255, 80, 120, 0.5));
    }

    @keyframes floatUpLove {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }
      80% {
        opacity: 0.9;
      }
      100% {
        transform: translateY(-110vh) rotate(360deg);
        opacity: 0;
      }
    }

    /* music hint small */
    .music-tag {
      position: fixed;
      bottom: 12px;
      right: 16px;
      background: rgba(0,0,0,0.5);
      backdrop-filter: blur(5px);
      padding: 6px 14px;
      border-radius: 60px;
      font-size: 0.75rem;
      color: #ffcddf;
      z-index: 20;
      font-weight: 500;
      pointer-events: none;
    }

    /* responsiveness */
    @media (max-width: 550px) {
      .romance-card h1 { font-size: 2.2rem; }
      .romance-card h2 { font-size: 1.5rem; }
      .lock-box { padding: 1.8rem 1.2rem; }
      .lock-box h2 { font-size: 1.7rem; }
    }
  </style>
</head>
<body>

  <!-- BACKGROUND MUSIC (looping, hidden but play after unlock) -->
  <audio id="bgMusic" loop preload="auto">
    <!-- Replace this with your own romantic mp3 file. The file name from original specs is kept as placeholder -->
    <source src="Record_2026-05-31-21-33-34_213650698.mp3" type="audio/mpeg">
    <!-- fallback message if file missing – silent but functional -->
    Your browser does not support the audio element. 💕
  </audio>

  <!-- LOCK SCREEN OVERLAY -->
  <div id="lockScreen">
    <div class="lock-box">
      <h2>💖 Secret Heart Lock 💖</h2>
      <p>✨ Only the sweetest words can open ✨</p>
      <input type="text" id="loveInput" placeholder="💌 whisper your answer..." autocomplete="off">
      <button onclick="unlockRomance()">🔓 Unlock my heart 🔓</button>
      <p id="errorMsg"></p>
      <div style="margin-top: 12px; font-size: 0.8rem;">💭 hint: three little words + "too"</div>
    </div>
  </div>

  <!-- MAIN CONTENT (hidden until unlocked) initially visible but lockScreen covers it -->
  <div id="mainContent" class="heart-content">
    <div class="romance-card">
      <div class="glow-heart">❤️💖❤️</div>
      <h1>You unlocked my soul!</h1>
      <h2>✨ Every heartbeat belongs to you ✨</h2>
      <p>💕 My love for you grows stronger with every second. <br>
      You are my sunshine, my midnight wish, and every beautiful dream. <br>
      <span style="font-weight: bold; font-size: 1.3rem;">🎶 The music is playing — just for us 🎶</span></p>
      <div style="margin: 20px 0 8px; font-size: 2rem;">💞 🌹 💞</div>
      <p style="font-size: 0.9rem;">Forever yours, with all my heart.</p>
    </div>
    <div class="music-tag">
      🎵 love melody • looping for eternity
    </div>
  </div>

  <script>
    // DOM elements
    const lockScreenDiv = document.getElementById('lockScreen');
    const loveInput = document.getElementById('loveInput');
    const errorMsgSpan = document.getElementById('errorMsg');
    const bgAudio = document.getElementById('bgMusic');

    // Floating hearts generator (gentle romantic effect)
    let heartInterval = null;

    // function to start floating hearts if not already running
    function startFloatingHearts() {
      if (heartInterval) return;
      heartInterval = setInterval(() => {
        const heart = document.createElement('div');
        heart.classList.add('floating-heart');
        // random heart symbols variety
        const heartVariants = ['❤️', '💖', '💗', '💓', '💕', '💞', '❣️', '💘'];
        heart.innerHTML = heartVariants[Math.floor(Math.random() * heartVariants.length)];
        // random horizontal position
        const randomLeft = Math.random() * 100;
        heart.style.left = randomLeft + '%';
        // random font size for depth
        const size = Math.random() * 20 + 16;
        heart.style.fontSize = size + 'px';
        heart.style.opacity = Math.random() * 0.8 + 0.3;
        heart.style.animationDuration = Math.random() * 4 + 3.5 + 's';
        heart.style.animationDelay = '0s';
        document.body.appendChild(heart);
        // auto remove after animation ends (6s safety)
        setTimeout(() => {
          if (heart && heart.remove) heart.remove();
        }, 5500);
      }, 320);
    }

    // unlock function: check password "i love you too"
    function unlockRomance() {
      let userInput = loveInput.value.trim().toLowerCase();
      // secret phrase exactly "i love you too"
      if (userInput === "i love you too") {
        // Hide lock screen with smooth effect
        lockScreenDiv.style.opacity = '0';
        setTimeout(() => {
          lockScreenDiv.style.display = 'none';
        }, 400);
        
        // Play background music (user gesture triggered - works on modern browsers)
        if (bgAudio) {
          bgAudio.play().then(() => {
            console.log("🎵 Music is playing sweetly");
          }).catch((err) => {
            console.warn("Audio play failed (maybe missing file): ", err);
            // we still show visual feedback but background plays no error
            const note = document.createElement('div');
            note.className = 'music-tag';
            note.style.bottom = '45px';
            note.style.background = '#ff4f8bcc';
            note.innerText = '🎧 Please add your favorite MP3 ❤️';
            document.body.appendChild(note);
            setTimeout(() => note.remove(), 3500);
          });
        } else {
          console.log("audio element missing?");
        }

        // start floating hearts if not running (creates romantic atmosphere)
        startFloatingHearts();

        // optional celebration effect: create a few instant hearts burst
        for (let i = 0; i < 20; i++) {
          setTimeout(() => {
            const burstHeart = document.createElement('div');
            burstHeart.classList.add('floating-heart');
            burstHeart.innerHTML = ['❤️', '💖', '💗', '💘'][Math.floor(Math.random()*4)];
            burstHeart.style.left = Math.random() * 100 + '%';
            burstHeart.style.fontSize = (Math.random() * 26 + 15) + 'px';
            burstHeart.style.animationDuration = '3s';
            document.body.appendChild(burstHeart);
            setTimeout(() => burstHeart.remove(), 3000);
          }, i * 50);
        }
      } else {
        // wrong password: romantic error hint
        errorMsgSpan.innerText = "❀ Not the magic words... try 'I love you too' ❀";
        loveInput.style.borderColor = "#ff7b9c";
        loveInput.style.boxShadow = "0 0 0 2px rgba(255, 80, 120, 0.5)";
        setTimeout(() => {
          if (errorMsgSpan.innerText.includes("magic")) {
            errorMsgSpan.innerText = "";
            loveInput.style.borderColor = "#ffb7c9";
            loveInput.style.boxShadow = "none";
          }
        }, 2000);
        loveInput.value = "";
        loveInput.focus();
      }
    }

    // allow "Enter" key in input field to trigger unlock
    if (loveInput) {
      loveInput.addEventListener('keypress', function(event) {
        if (event.key === 'Enter') {
          event.preventDefault();
          unlockRomance();
        }
      });
    }

    // preload audio settings, set volume lower for comfort
    if (bgAudio) {
      bgAudio.volume = 0.5;
      bgAudio.loop = true;
    }

    // On page load, ensure main content is visible behind lock, but lock covers all
    // also if any freak event, set lockScreen fully visible.
    window.addEventListener('load', () => {
      lockScreenDiv.style.display = 'flex';
      lockScreenDiv.style.opacity = '1';
      // small aesthetic: background floating hearts will only start after unlock,
      // but can also pre- generate a few? Not needed for lock screen mystery.
      // also set up a placeholder error removal on typing
      if (loveInput) {
        loveInput.addEventListener('input', () => {
          if (errorMsgSpan.innerText !== "") {
            errorMsgSpan.innerText = "";
            loveInput.style.borderColor = "#ffb7c9";
          }
        });
      }
      // additionally, prevent body scroll when lock screen is active
      document.body.style.overflow = 'hidden';
      // unlock function will reset overflow
    });

    // When lock screen disappears, remove hidden overflow & make main content interactive
    const observer = new MutationObserver(function(mutations) {
      mutations.forEach(function(mutation) {
        if (mutation.attributeName === 'style' && lockScreenDiv.style.display === 'none') {
          document.body.style.overflow = 'auto';
          observer.disconnect();
        }
      });
    });
    observer.observe(lockScreenDiv, { attributes: true });

    // handle if someone tries to inspect and remove lock manually? keep romantic integrity
    // Also if music fails because of missing mp3, show small tooltip but not disrupt experience.
    // Ensure background image & main content load perfectly.
  </script>
  
  <!-- Inline additional style for scrollbar & elegance -->
  <style>
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: #2e1a24;
      border-radius: 10px;
    }
    ::-webkit-scrollbar-thumb {
      background: #ff6b9d;
      border-radius: 10px;
    }
    body {
      scroll-behavior: smooth;
    }
    .romance-card p {
      text-shadow: 0 1px 3px rgba(0,0,0,0.2);
    }
    button, input {
      font-family: 'Poppins', monospace;
    }
    .floating-heart {
      user-select: none;
    }
    /* lock screen disappears with transition */
    #lockScreen {
      transition: opacity 0.4s ease, visibility 0s linear 0.4s;
    }
    #lockScreen[style*="display: none"] {
      transition: opacity 0.3s ease, visibility 0s linear 0.3s;
    }
  </style>
</body>
</html>
```
