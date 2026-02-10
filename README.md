<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<title>For Hasini ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:ital@0;1&display=swap" rel="stylesheet">

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Playfair Display', serif;
  background: linear-gradient(#fde2e4, #fff6ea);
  color: #5a2a2a;
  overflow: hidden;
}

.page {
  width: 100vw;
  height: 100vh;
  display: none;
  padding: 40px;
  text-align: center;
}

.page.active {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h1 {
  font-size: 2.2rem;
  margin-bottom: 20px;
}

button {
  margin-top: 30px;
  padding: 12px 30px;
  border: none;
  border-radius: 30px;
  background: #f4a7b9;
  color: white;
  font-size: 1rem;
  cursor: pointer;
}

button:hover {
  background: #e38fa3;
}

/* Letter */
.letter {
  max-width: 700px;
  font-family: 'Great Vibes', cursive;
  font-size: 1.5rem;
  line-height: 1.8;
}

/* Page 3 */
.poem {
  max-width: 750px;
  font-size: 1.2rem;
  line-height: 1.9;
}

.emoji {
  font-size: 1.5rem;
}

/* Page 4 */
.surprises {
  display: flex;
  gap: 40px;
  margin-top: 30px;
}

.icon {
  font-size: 3rem;
  cursor: pointer;
}

.hidden {
  display: none;
}

/* Petals */
.petal {
  position: fixed;
  top: -10px;
  font-size: 18px;
  opacity: 0.4;
  animation: fall linear infinite;
}

@keyframes fall {
  to {
    transform: translateY(110vh) translateX(50px);
  }
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<div class="page active">
  <h1>THE MOST BEAUTIFUL GIRL I HAVE EVER MET</h1>
  <button onclick="nextPage()">OK</button>
</div>

<!-- PAGE 2 -->
<div class="page">
  <div class="letter">
    <p>Dear Hasini,</p><br>

    <p>Happy Valentine’s Day ❤️</p><br>

    <p>
      We may not get to meet every day, but somehow you live with me in every moment.
      No matter what I’m doing or where I am, my mind always finds its way back to you—
      like that’s where it belongs.
    </p><br>

    <p>
      You are my better half. The calm version of me.
      When my thoughts are loud and life feels heavy,
      thinking of you makes everything softer.
    </p><br>

    <p>
      You are the light of my life, Hasini —
      the quiet kind that makes me feel at home.
    </p><br>

    <p>Yours,<br>Forever yours 💙</p>
  </div>

  <button onclick="nextPage()">Next</button>
</div>

<!-- PAGE 3 -->
<div class="page">
  <div class="poem">
    <p class="emoji">🌹 ❤️ 🌹</p>
    <p>
      You matter to me more than words ever could.<br>
      You are the calm in my chaos,<br>
      the softer thought in my restless mind.
    </p><br>

    <p>
      You are the better version of me,<br>
      the understanding heart,<br>
      the innocent smile that makes life gentle.
    </p><br>

    <p>
      In a loud world,<br>
      you are my quiet peace.
    </p>
    <p class="emoji">❤️ 🌹 ❤️</p>
  </div>

  <button onclick="nextPage()">Next</button>
</div>

<!-- PAGE 4 -->
<div class="page" id="lastPage">
  <h1>Click to see the surprise</h1>

  <div class="surprises">
    <div class="icon" onclick="showSurprise('one')">🌹</div>
    <div class="icon" onclick="showSurprise('two')">🍫</div>
    <div class="icon" onclick="showSurprise('three')">💖</div>
  </div>

  <div id="one" class="hidden">
    <p>I LOVE YOU A LOT ❤️</p>
  </div>

  <div id="two" class="hidden">
    <p>These chocolates are for you 🍫</p>
  </div>

  <div id="three" class="hidden">
    <p>HAPPY VALENTINE’S DAY MY DEAR LOVE 💕</p>
    <small>
      Even though I could not wish you in real,<br>
      my love stays the same.
    </small>
  </div>

  <audio id="song">
    <source src="Un-Vizhigalil.mp3" type="audio/mpeg">
  </audio>
</div>

<script>
let current = 0;
const pages = document.querySelectorAll('.page');

function nextPage() {
  pages[current].classList.remove('active');
  current++;
  pages[current].classList.add('active');

  if (pages[current].id === "lastPage") {
    startMusic();
    startPetals();
  }
}

function showSurprise(id) {
  document.querySelectorAll('#one, #two, #three').forEach(e => e.classList.add('hidden'));
  document.getElementById(id).classList.remove('hidden');
}

function startMusic() {
  const audio = document.getElementById("song");
  audio.currentTime = 60;
  audio.volume = 0.6;
  audio.play();
  setTimeout(() => audio.pause(), 48000);
}

function startPetals() {
  for (let i = 0; i < 20; i++) {
    let petal = document.createElement("div");
    petal.className = "petal";
    petal.innerText = "🌸";
    petal.style.left = Math.random() * 100 + "vw";
    petal.style.animationDuration = 6 + Math.random() * 6 + "s";
    document.body.appendChild(petal);
  }
}
</script>

</body>
</html>
