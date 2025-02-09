<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For My BABY DINO</title>
  <style>
    body {
      font-family: 'Ophelia Lark';
      text-align: center;
      background-color: #FFa07a;
      color: #8B0000;
      margin: 0;
      padding: 0;
      overflow: hidden;
      position: relative;
    }
    .slide {
      display: none;
      padding: 50px;
    }
    .slide.active {
      display: block;
    }
    h1 {
      font-size: 3rem;
      margin-bottom: 20px;
    }
    p {
      font-size: 1.5rem;
      margin-bottom: 30px;
    }
    img {
      width: 150px;
      height: 150px;
      border-radius: 0%;
      object-fit: cover;
      margin-bottom: 30px;
      border: 5px solid #c62828;
    }
    .button {
      background-color: #c62828;
      color: white;
      padding: 15px 30px;
      font-size: 1.2rem;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      margin: 10px;
    }
    .button:hover {
      background-color: #ff5252;
    }
    .footer {
      margin-top: 50px;
      font-size: 1rem;
      color: #666;
    }
    #noButton {
      position: absolute;
    }
    .flower {
      position: absolute;
      width: 20px;
      height: 20px;
      background-image: url('https://www.transparentpng.com/thumb/flower/flower-png-14.png'); /* Flower image */
      background-size: cover;
      animation: fall linear infinite;
    }
    @keyframes fall {
      0% { top: -20px; transform: rotate(0deg); }
      100% { top: 100vh; transform: rotate(360deg); }
    }
  </style>
</head>
<body>
  <!-- Slide 1: Romantic Opening -->
  <div class="slide active">
    <h1>For My BABY DINO 🦖</h1>
    <p>Hey love, I have made something for you.
 Click "Next" to see what it is! </p>
    <button class="button" onclick="nextSlide()">Next</button>
  </div>

  <!-- Slide 2: Funny Memory -->
  <div class="slide">
    <h1>See?</h1>
    <p>Our first date, even though our friends tagged along with us lol.
    <br> 
    But you were looking sooo CUTE!</p>
    <img src="pictwo.jpg" alt="Funny Memory">
    <br>
    <button class="button" onclick="nextSlide()">Next</button>
  </div>

  <!-- Slide 3: Heartfelt Message -->
  <div class="slide">
    <h1>You Mean Everything to Me Re</h1>
    <p>Infact, i think our fate ends with us, 
    since no matter how many arguments we went through, 
    our love for eachother did remain the same right?</p>
    <img src="picone.jpg" alt="Our Photo">
    <br>
    <button class="button" onclick="nextSlide()">Next</button>
  </div>

  <!-- Slide 4: Valentine's Question -->
  <div class="slide">
    <h1>So Jaan, Will You Be My Valentine? 💌</h1>
    <p>I know I cannot do this in person right now, but i will someday for sure.
    <br> 
    So, Mr Rastogi, are you willing to claim me as your wife this valentine?</p>
    <button class="button" onclick="celebrate()">Yes, I'll be your Valentine!</button>
    <button id="noButton" class="button" onmouseover="moveNoButton()">No</button>
  </div>

  <!-- Audio for clapping sound -->
  <audio id="clappingSound" src="https://assets.mixkit.co/active_storage/sfx/3007/3007-preview.mp3"></audio>

  <script>
    let currentSlide = 0;
    const slides = document.querySelectorAll('.slide');

    function nextSlide() {
      slides[currentSlide].classList.remove('active');
      currentSlide = (currentSlide + 1) % slides.length;
      slides[currentSlide].classList.add('active');
    }

    function moveNoButton() {
      const noButton = document.getElementById('noButton');
      const x = Math.random() * (window.innerWidth - noButton.offsetWidth);
      const y = Math.random() * (window.innerHeight - noButton.offsetHeight);
      noButton.style.left = `${x}px`;
      noButton.style.top = `${y}px`;
    }

    function celebrate() {
      // Play clapping sound
      const clappingSound = document.getElementById('clappingSound');
      clappingSound.play();

      // Show flower animation
      for (let i = 0; i < 50; i++) {
        createFlower();
      }

      // Show alert
      alert('I LOVE YOU BOHOT ZADAAA BABY❤️');
    }

    function createFlower() {
      const flower = document.createElement('div');
      flower.classList.add('flower');
      flower.style.left = Math.random() * window.innerWidth + 'px';
      flower.style.animationDuration = Math.random() * 3 + 2 + 's'; // Random fall speed
      document.body.appendChild(flower);

      // Remove flower after animation ends
      setTimeout(() => {
        flower.remove();
      }, 5000);
    }
  </script>
</body>
</html>
