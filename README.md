<script>
// ✅ Sahi DOB format (YYYY-MM-DD)
const correctDOB = "1994-07-29";

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
    const input = document.getElementById("dobInput").value.trim();

    if (input === correctDOB) {
        document.getElementById("loginBox").style.display = "none";
        document.getElementById("book").style.display = "block";
        showPage();
    } else {
        document.getElementById("error").innerText =
            "Wrong DOB 😢 Hint: Try 29 July 1994";
    }
}

function showPage() {
    document.getElementById("dayTitle").innerText = pages[currentPage].day;
    document.getElementById("pageText").innerText = pages[currentPage].text;
    document.getElementById("pageNumber").innerText =
        "Page " + (currentPage + 1) + " / " + pages.length;
}

function nextPage() {
    if (currentPage < pages.length - 1) {
        currentPage++;
        showPage();
    } else {
        document.getElementById("dayTitle").innerText = "💖 The End";
        document.getElementById("pageText").innerText =
            "Valentine Week ends… but my love for you never will ❤️";
        document.getElementById("pageNumber").innerText = "";
    }
}
</script>
