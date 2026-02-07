<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine Love Book ❤️</title>

<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #ff758c, #ff7eb3);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

/* Login Box */
#loginBox {
    background: white;
    padding: 30px;
    border-radius: 15px;
    text-align: center;
    box-shadow: 0 10px 25px rgba(0,0,0,0.2);
}

input {
    padding: 10px;
    margin-top: 10px;
    border-radius: 8px;
    border: 1px solid #ccc;
    font-size: 16px;
}

button {
    margin-top: 15px;
    padding: 10px 20px;
    border: none;
    border-radius: 8px;
    background: #ff4d6d;
    color: white;
    font-size: 16px;
    cursor: pointer;
}

button:hover {
    background: #e63956;
}

/* Book */
#book {
    display: none;
    width: 330px;
    height: 430px;
    background: #fff0f6;
    border-radius: 12px;
    box-shadow: 0 15px 30px rgba(0,0,0,0.3);
    padding: 25px;
    text-align: center;
    position: relative;
    animation: openBook 1s ease forwards;
}

@keyframes openBook {
    from { transform: scale(0.5) rotateY(90deg); opacity: 0; }
    to { transform: scale(1) rotateY(0); opacity: 1; }
}

.dayTitle {
    font-size: 22px;
    color: #c9184a;
    font-weight: bold;
    margin-top: 10px;
}

.pageText {
    font-size: 17px;
    color: #d6336c;
    margin-top: 60px;
    min-height: 120px;
}

.pageNumber {
    position: absolute;
    bottom: 15px;
    right: 20px;
    font-size: 14px;
    color: #888;
}
</style>
</head>

<body>

<div id="loginBox">
    <h2>Enter Your Date of Birth 💌</h2>
    <input type="date" id="dobInput">
    <br>
    <button onclick="checkDOB()">Open My Valentine Gift 🎁</button>
    <p id="error" style="color:red;"></p>
</div>

<div id="book">
    <div class="dayTitle" id="dayTitle"></div>
    <div class="pageText" id="pageText"></div>
    <div class="pageNumber" id="pageNumber"></div>
    <button onclick="nextPage()">Next Page ➡️</button>
</div>

<script>
// 🔒 Yahan apni Valentine ka DOB daalo
const correctDOB = "2003-05-14";

const pages = [
    {day:"🌹 Rose Day", text:"A rose for you, because your smile makes my world bloom."},
    {day:"💍 Propose Day", text:"If loving you is a dream, I never want to wake up."},
    {day:"🍫 Chocolate Day", text:"Life with you is sweeter than any chocolate in the world."},
    {day:"🧸 Teddy Day", text:"I wish I could hug you right now like a soft teddy bear."},
    {day:"🤝 Promise Day", text:"I promise to stand by you, today, tomorrow, forever."},
    {day:"🤗 Hug Day", text:"One hug from you can fix my worst days."},
    {day:"💋 Kiss Day", text:"A kiss from you is my favorite kind of magic."},
    {day:"❤️ Valentine’s Day", text:"You are my today, my tomorrow, and my forever love."}
];

let currentPage = 0;

function checkDOB() {
    const input = document.getElementById("dobInput").value;
    if (input === correctDOB) {
        document.getElementById("loginBox").style.display = "none";
        document.getElementById("book").style.display = "block";
        showPage();
    } else {
        document.getElementById("error").innerText = "Wrong DOB 😢 Try again my love.";
    }
}

function showPage() {
    document.getElementById("dayTitle").innerText = pages[currentPage].day;
    document.getElementById("pageText").innerText = pages[currentPage].text;
    document.getElementById("pageNumber").innerText = "Page " + (currentPage + 1) + " / " + pages.length;
}

function nextPage() {
    if (currentPage < pages.length - 1) {
        currentPage++;
        showPage();
    } else {
        document.getElementById("dayTitle").innerText = "💖 The End";
        document.getElementById("pageText").innerText = "Valentine Week ends… but my love for you never will ❤️";
        document.getElementById("pageNumber").innerText = "";
    }
}
</script>

</body>
</html>
