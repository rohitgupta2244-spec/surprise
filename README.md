<!DOCTYPE html>
<html>
<head>
  <title>Valentine Surprise ❤️</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background: linear-gradient(135deg, #ff4e8a, #ff9a9e);
      color: white;
      padding: 30px;
    }
    .box {
      background: white;
      color: #333;
      padding: 20px;
      border-radius: 15px;
      max-width: 400px;
      margin: auto;
    }
    input {
      padding: 10px;
      width: 90%;
      margin: 10px 0;
      border-radius: 8px;
      border: 1px solid #ccc;
    }
    button {
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      background: #ff4e8a;
      color: white;
      font-size: 16px;
    }
    a {
      color: #ff4e8a;
      word-break: break-all;
    }
  </style>
</head>
<body>

  <h1>💖 Valentine Surprise Link 💖</h1>

  <div class="box">
    <p>Enter Your Love's Name</p>
    <input type="text" id="name" placeholder="Enter Name">
    <button onclick="generateLink()">Generate Link</button>
    <p id="output"></p>
  </div>

  <script>
    function generateLink() {
      var name = document.getElementById("name").value;
      if(name === "") {
        alert("Please enter a name!");
        return;
      }
      var link = window.location.href + "?name=" + encodeURIComponent(name);
      document.getElementById("output").innerHTML =
        "Share this link:<br><a href='" + link + "'>" + link + "</a>";
    }

    const urlParams = new URLSearchParams(window.location.search);
    const person = urlParams.get('name');

    if(person) {
      document.body.innerHTML = "<h1>❤️ Happy Valentine’s Day " + person + " ❤️</h1><p>You are my favorite person in the world 💕</p>";
    }
  </script>

</body>
</html>

