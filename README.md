<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Siddhi 💌</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      height: 100vh;
      background: linear-gradient(135deg, #ff5f9e, #ffc371);
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 30px;
      width: 90%;
      max-width: 420px;
      border-radius: 25px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
      animation: pop 0.8s ease;
    }

    @keyframes pop {
      0% { transform: scale(0.6); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    h1 {
      font-size: 1.8rem;
      margin-bottom: 10px;
    }

    p {
      font-size: 1rem;
      margin-bottom: 20px;
      color: #444;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 15px;
    }

    button {
      padding: 12px 22px;
      border-radius: 50px;
      border: none;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: 0.3s;
    }

    #yes {
      background: #ff4081;
      color: white;
    }

    #yes:hover {
      transform: scale(1.1);
      box-shadow: 0 10px 20px rgba(255,64,129,0.5);
    }

    #no {
      background: #e0e0e0;
      color: #333;
      position: relative;
    }

    .hidden {
      display: none;
    }

    .celebrate {
      font-size: 1.5rem;
      animation: float 1.5s infinite alternate;
    }

    @keyframes float {
      from { transform: translateY(0); }
      to { transform: translateY(-10px); }
    }

    .heart {
      position: absolute;
      font-size: 24px;
      animation: fly 3s linear forwards;
    }

    @keyframes fly {
      0% { opacity: 1; transform: translateY(0) scale(1); }
      100% { opacity: 0; transform: translateY(-200px) scale(1.5); }
    }
  </style>
</head>
<body>

  <div class="card" id="card">
    <h1>Hey Siddhi 💖</h1>
    <p>
      Quick question before the universe collapses,<br>
      my heart beats faster, and destiny refreshes the page…
    </p>

    <h1>Will you be my Valentine? 🌹</h1>

    <div class="buttons">
      <button id="yes">YES 💘</button>
      <button id="no">NO 🙃</button>
    </div>
  </div>

  <div class="card hidden" id="success">
    <h1 class="celebrate">SHE SAID YES 😭💖</h1>
    <p>
      This moment is officially living rent-free in my head.<br>
      Valentine’s Day = unlocked 🔓
    </p>
    <p>
      Screenshot this.<br>
      Because history was made.
    </p>
  </div>

  <script>
    const yesBtn = document.getElementById("yes");
    const noBtn = document.getElementById("no");
    const card = document.getElementById("card");
    const success = document.getElementById("success");

    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 200 - 100;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    });

    yesBtn.addEventListener("click", () => {
      card.classList.add("hidden");
      success.classList.remove("hidden");
      hearts();
    });

    function hearts() {
      for (let i = 0; i < 20; i++) {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerText = "💖";
        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.top = window.innerHeight + "px";
        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 3000);
      }
    }
  </script>

</body>
</html>
