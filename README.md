<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>I'm Sorry 😢</title>
  <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@600&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Quicksand', sans-serif;
    }

    body {
      background-color: #ffe6f2;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      overflow: hidden;
      background-image: url('https://i.pinimg.com/originals/1f/40/c7/1f40c7ceab191388ffb9b36d6d3c2c72.gif');
      background-size: cover;
      background-position: center;
    }

    .container {
      background-color: rgba(255, 240, 245, 0.95);
      border-radius: 30px;
      padding: 30px;
      box-shadow: 0 10px 40px rgba(0,0,0,0.2);
      text-align: center;
      width: 90%;
      max-width: 400px;
      animation: floatIn 1s ease;
      position: relative;
      z-index: 2;
      transition: all 0.3s ease-in-out;
    }

    @keyframes floatIn {
      from { transform: scale(0.5); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    .gif {
      width: 100%;
      max-width: 180px;
      margin: 20px auto;
      border-radius: 20px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    h2 {
      color: #d63384;
      font-size: 1.5rem;
      margin-bottom: 10px;
      text-shadow: 1px 1px 2px #fff;
    }

    p {
      color: #555;
      font-size: 1rem;
      margin-top: 10px;
    }

    .btn {
      background: linear-gradient(to right, #f78fb3, #c77dff);
      border: none;
      color: white;
      padding: 12px 24px;
      margin: 10px 5px;
      border-radius: 30px;
      font-size: 16px;
      cursor: pointer;
      transition: transform 0.3s ease, background 0.3s;
    }

    .btn:hover {
      transform: scale(1.1);
      background: linear-gradient(to right, #f368e0, #9d4edd);
    }

    .hidden {
      display: none;
    }

    /* Flying hearts */
    .heart {
      width: 30px;
      height: 30px;
      background-image: url('https://cdn-icons-png.flaticon.com/512/833/833472.png');
      background-size: cover;
      position: absolute;
      animation: floatHeart 6s linear infinite;
      opacity: 0.6;
      pointer-events: none;
    }

    @keyframes floatHeart {
      0% {
        transform: translateY(100vh) scale(0.5);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1);
        opacity: 0;
      }
    }

    @media (max-width: 480px) {
      h2 {
        font-size: 1.2rem;
      }
      .btn {
        font-size: 14px;
        padding: 10px 18px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div id="step1">
      <h2>Step 1: My Love... Will You Forgive Me? 🥺</h2>
      <img class="gif" src="https://media.giphy.com/media/ya4eevXU490Iw/giphy.gif" alt="Cute dog with heart eyes">
      <p>I’m super sorry 😞 My heart feels empty without your smile 💔</p>
      <button class="btn" onclick="nextStep(2)">Yes,  Meri Jaan💖</button>
      <button class="btn" onclick="nextStep(3)">Still Mad😾</button>
    </div>

    <div id="step2" class="hidden">
      <h2>Step 2: Yay! You're the sweetest 💕</h2>
      <img class="gif" src="https://media.giphy.com/media/TdfyKrN7HGTIY/giphy.gif" alt="Cute happy bounce">
      <p>Thanks for making my world colorful again 🌈✨</p>
      <button class="btn" onclick="nextStep(4)">Next 💌</button>
    </div>

    <div id="step3" class="hidden">
      <h2>Step 2: Noooo... don't be angry 😭</h2>
      <img class="gif" src="https://media.giphy.com/media/L95W4wv8nnb9K/giphy.gif" alt="Sad cat">
      <p>I'll do anything! Cute dates, pizza nights, cuddles! 🧸</p>
      <button class="btn" onclick="nextStep(2)">Fineee 🥹</button>
    </div>

    <div id="step4" class="hidden">
      <h2>Final Step: You & Me = Forever 🫶</h2>
      <img class="gif" src="https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExdTB0bTF6MWZra2kyYTNtYnRyMG8zcjl1OGFsZW0yc2I4MHF1eWh4cyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/9d3LQ6TdV2Flo8ODTU/giphy.gif" alt="Bears hugging">
      <p>I pinky promise to love you better every day 💗</p>
    </div>
  </div>

  <script>
    function nextStep(step) {
      document.querySelectorAll('.container > div').forEach(div => div.classList.add('hidden'));
      document.getElementById('step' + step).classList.remove('hidden');
    }

    function spawnHearts() {
      for (let i = 0; i < 10; i++) {
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.style.left = Math.random() * window.innerWidth + 'px';
        heart.style.animationDuration = (Math.random() * 3 + 4) + 's';
        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 7000);
      }
    }

    setInterval(spawnHearts, 500);
  </script>
</body>
</html>
