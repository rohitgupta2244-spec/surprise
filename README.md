<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Make it Special 💖</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(135deg, #ffd1dc, #ff9eb5);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    overflow: hidden;
}

/* Floating Hearts */
.heart {
    position: absolute;
    color: #ff4d6d;
    font-size: 22px;
    animation: floatUp 8s linear infinite;
    opacity: 0.7;
}

@keyframes floatUp {
    0% { transform: translateY(100vh) scale(0.5); }
    100% { transform: translateY(-10vh) scale(1.4); }
}

/* Card */
.card {
    background: #fff;
    width: 360px;
    padding: 25px;
    border-radius: 20px;
    box-shadow: 0 15px 35px rgba(0,0,0,0.15);
    text-align: center;
    position: relative;
    z-index: 2;
}

h1 {
    color: #ff4d6d;
    font-size: 34px;
    margin-bottom: 10px;
}

label {
    display: block;
    text-align: left;
    margin-top: 15px;
    font-size: 14px;
    color: #444;
}

input, textarea {
    width: 100%;
    padding: 12px;
    margin-top: 6px;
    border-radius: 10px;
    border: 1px solid #eee;
    font-size: 14px;
    background: #fafafa;
}

textarea {
    resize: none;
    height: 80px;
}

button {
    margin-top: 20px;
    width: 100%;
    padding: 14px;
    border: none;
    border-radius: 30px;
    background: linear-gradient(90deg, #ff4d6d, #ff758c);
    color: white;
    font-size: 16px;
    cursor: pointer;
    box-shadow: 0 8px 15px rgba(255,77,109,0.3);
}

button:hover {
    transform: scale(1.05);
}

/* Link Box */
#resultBox {
    display: none;
    margin-top: 20px;
    background: #fff0f6;
    padding: 15px;
    border-radius: 12px;
    font-size: 13px;
    word-wrap: break-word;
}
</style>
</head>

<body>

<!-- Floating Hearts -->
<script>
for (let i = 0; i < 20; i++) {
    let heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (5 + Math.random() * 5) + "s";
    heart.style.fontSize = (18 + Math.random() * 15) + "px";
    document.body.appendChild(heart);
}
</script>

<div class="card">
    <h1>Make it Special 💖</h1>

    <label>Who is this for?</label>
    <input type="text" id="name" placeholder="e.g. My Crush, Anjali">

    <label>Custom Message (Optional)</label>
    <textarea id="message">Will you be my Valentine? 💘</textarea>

    <button onclick="generateLink()">Generate Link 💌</button>

    <div id="resultBox"></div>
</div>

<script>
function generateLink() {
    const name = document.getElementById("name").value.trim();
    const msg = encodeURIComponent(document.getElementById("message").value.trim());

    if (name === "") {
        alert("Enter a name first 💖");
        return;
    }

    const link = `https://yourlink.com/valentine.html?to=${encodeURIComponent(name)}&msg=${msg}`;

    document.getElementById("resultBox").style.display = "block";
    document.getElementById("resultBox").innerHTML = 
        "Here is your magical link ✨<br><br>" + link;
}
</script>

</body>
</html>
