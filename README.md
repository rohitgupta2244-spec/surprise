<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love ❤️</title>

<style>
body {
    margin: 0;
    padding: 0;
    min-height: 100vh;
    min-height: 100dvh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4);
    font-family: Arial, sans-serif;
    overflow: hidden;
}

.box {
    text-align: center;
    background: white;
    padding: 40px;
    border-radius: 15px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    position: relative;
    z-index: 10;
}

h1 { margin-bottom: 30px; }

button {
    padding: 12px 25px;
    font-size: 18px;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    margin: 10px;
}

#yesBtn { background-color: #ff4d6d; color: white; }
#noBtn { background-color: #ccc; }

.heart {
    position: fixed;
    bottom: -10px;
    color: red;
    animation: floatUp linear infinite;
    opacity: 0.7;
}

@keyframes floatUp {
    0% { transform: translateY(0); opacity: 0.7; }
    100% { transform: translateY(-100vh); opacity: 0; }
}
</style>
</head>

<body>

<div class="box">
    <h1>Will you be my Valentine? ❤️</h1>
    <button id="yesBtn">YES 💖</button>
    <button id="noBtn">NO 🙈</button>
</div>

<audio id="bgMusic" loop>
    <source src="love.mp3" type="audio/mpeg">
</audio>

<script>
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");
const music = document.getElementById("bgMusic");

// Play music only after user clicks YES (mobile safe)
yesBtn.addEventListener("click", () => {
    music.play().catch(()=>{});
    document.body.innerHTML = `
        <div style="display:flex;justify-content:center;align-items:center;height:100vh;background:#ff4d6d;color:white;font-size:32px;text-align:center;padding:20px;">
            Yaaay!!! ❤️ I knew it! You're my Valentine forever 😍💍
        </div>
    `;
});

// Move NO button anywhere on screen (mobile friendly)
function moveButton() {
    const maxX = window.innerWidth - noBtn.offsetWidth - 20;
    const maxY = window.innerHeight - noBtn.offsetHeight - 20;

    const x = Math.random() * maxX;
    const y = Math.random() * maxY;

    noBtn.style.position = "fixed";
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
}

noBtn.addEventListener("mouseover", moveButton);
noBtn.addEventListener("touchstart", moveButton);

// Floating hearts
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "❤";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 15 + "px";
    heart.style.animationDuration = Math.random() * 3 + 3 + "s";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
}

setInterval(createHeart, 600);
</script>

</body>
</html>
