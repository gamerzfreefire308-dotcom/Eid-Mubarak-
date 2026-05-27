# Eid-Mubarak-
Eid Wishes For Special Friend 
<!DOCTYPE html>
<html>
<head>
  <title>Eid Surprise 🌙</title>

  <style>
    body{
      margin:0;
      height:100vh;
      overflow:hidden;
      background:black;
      font-family:Arial;
      display:flex;
      justify-content:center;
      align-items:center;
      color:white;
      text-align:center;
    }

    #startScreen{
      position:absolute;
      width:100%;
      height:100%;
      background:black;
      display:flex;
      justify-content:center;
      align-items:center;
      flex-direction:column;
      cursor:pointer;
    }

    #startScreen h1{
      color:gold;
      font-size:30px;
    }

    .box{
      display:none;
      z-index:2;
    }

    h1{
      font-size:55px;
      color:gold;
    }

    p{
      font-size:20px;
      margin-top:20px;
    }

    /* stars */
    .star{
      position:absolute;
      width:3px;
      height:3px;
      background:white;
      border-radius:50%;
      animation:blink 2s infinite;
    }

    @keyframes blink{
      0%{opacity:0.2;}
      100%{opacity:1;}
    }

    /* hearts */
    .heart{
      position:absolute;
      font-size:20px;
      animation: floatUp 5s linear infinite;
    }

    @keyframes floatUp{
      0%{transform:translateY(100vh); opacity:1;}
      100%{transform:translateY(-10vh); opacity:0;}
    }

  </style>
</head>

<body>

<!-- 🎬 START SCREEN -->
<div id="startScreen" onclick="start()">
  <h1>🎁 Click to open your Eid surprise</h1>
</div>

<!-- 🌙 MAIN CONTENT -->
<div class="box" id="mainBox">
  <h1>🌙 Eid Mubarak</h1>
  <p id="msg"></p>
</div>

<!-- 🎵 music -->
<audio id="music" loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<script>

function start(){
  document.getElementById("startScreen").style.display = "none";
  document.getElementById("mainBox").style.display = "block";

  document.getElementById("music").play();

  typing();
  stars();
  hearts();
}

/* typing effect */
let text = "Tum naraz ho sakti ho... lekin meri dua hamesha tumhare sath hai ✨ Eid Mubarak!";
let i = 0;

function typing(){
  if(i < text.length){
    document.getElementById("msg").innerHTML += text.charAt(i);
    i++;
    setTimeout(typing, 50);
  }
}

/* stars */
function stars(){
  for(let i=0;i<80;i++){
    let s = document.createElement("div");
    s.className = "star";
    s.style.top = Math.random()*100 + "vh";
    s.style.left = Math.random()*100 + "vw";
    document.body.appendChild(s);
  }
}

/* hearts */
function hearts(){
  setInterval(()=>{
    let h = document.createElement("div");
    h.className = "heart";
    h.innerHTML = "💖";
    h.style.left = Math.random()*100 + "vw";
    h.style.fontSize = (Math.random()*20+10)+"px";
    document.body.appendChild(h);

    setTimeout(()=>{h.remove();},5000);
  },300);
}

</script>

</body>
</html>
