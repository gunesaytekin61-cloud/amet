[inditex.html](https://github.com/user-attachments/files/29433299/inditex.html)
# amet<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>amet</title>
  <style>
    body {
      margin: 0;
      font-family: Comic Sans MS, cursive;
      text-align: center;
      background: pink; /* Arka plan full pembe */
      overflow: hidden;
    }
    h1 { color: purple; }
    button {
      padding: 10px 20px;
      font-size: 18px;
      margin: 10px;
      cursor: pointer;
    }
    #evet { background: lightgreen; }
    #hayir { background: lightcoral; position: absolute; }
    #mesaj {
      margin-top: 20px;
      font-size: 24px;
      color: red;
      font-weight: bold;
    }
    .heart {
      position: absolute;
      font-size: 30px;
      color: red;
      animation: float 2s linear forwards;
    }
    @keyframes float {
      0% { transform: translateY(0); opacity: 1; }
      100% { transform: translateY(-200px); opacity: 0; }
    }
  </style>
</head>
<body>
  <h1>Beni ne kadar seviyorsun?</h1>
  <button id="evet">Evet ❤️</button>
  <button id="hayir">Hayır 💔</button>
  <p id="mesaj"></p>

  <script>
    const evetBtn = document.getElementById("evet");
    const hayirBtn = document.getElementById("hayir");
    const mesaj = document.getElementById("mesaj");

    // Evet butonuna tıklanınca mesaj + kalpler çıksın
    evetBtn.addEventListener("click", () => {
      mesaj.innerText = "Ben de seni çok seviyorum şapşik şey! ❤️";

      for(let i=0; i<15; i++) {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerText = ["❤️","💕","💜"][Math.floor(Math.random()*3)];
        heart.style.left = Math.random()*window.innerWidth + "px";
        heart.style.top = window.innerHeight + "px";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 2000);
      }
    });

    // Hayır butonu kaçsın
    hayirBtn.addEventListener("mouseover", () => {
      hayirBtn.style.left = Math.random()*(window.innerWidth-100) + "px";
      hayirBtn.style.top = Math.random()*(window.innerHeight-50) + "px";
    });
  </script>
</body>
</html>



     
