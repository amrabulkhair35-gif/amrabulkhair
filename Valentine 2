<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Ayaa ❤️</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;500&display=swap" rel="stylesheet">

<style>
body{
    margin:0;
    padding:0;
    font-family:'Poppins',sans-serif;
    text-align:center;
    overflow:hidden;
    color:white;
}

/* CINEMATIC INTRO */
#intro{
    position:fixed;
    width:100%;
    height:100vh;
    background:black;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    z-index:10;
}

#introText{
    font-size:1.8rem;
    width:80%;
    opacity:0;
    animation:fadeText 6s forwards;
}

@keyframes fadeText{
    0%{opacity:0;}
    20%{opacity:1;}
    80%{opacity:1;}
    100%{opacity:0;}
}

/* STARS */
.star{
    position:absolute;
    width:2px;
    height:2px;
    background:white;
    animation:twinkle 2s infinite alternate;
}
@keyframes twinkle{
    from{opacity:0.2;}
    to{opacity:1;}
}

/* LOCK SCREEN */
#locked{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    display:none;
    color:black;
}

/* MAIN */
.container{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    display:none;
    animation:fadeIn 2s forwards;
}

@keyframes fadeIn{
    from{opacity:0;}
    to{opacity:1;}
}

h1{
    font-family:'Great Vibes',cursive;
    font-size:3rem;
}

button{
    padding:12px 25px;
    font-size:18px;
    border:none;
    border-radius:30px;
    cursor:pointer;
    margin:10px;
    transition:0.3s;
}

.yes{ background:white; color:#ff4e8a;}
.no{ background:transparent; border:2px solid white; color:white;}
button:hover{ transform:scale(1.1);}

body.main-bg{
    background:linear-gradient(135deg,#ff4e8a,#ff9eb5);
}

/* HAND & RING */
.hand-container{
    position:relative;
    width:300px;
    margin:20px auto;
}
.hand{ width:100%; }
.ring{
    position:absolute;
    width:60px;
    top:0;
    left:-100px;
    transition:1.5s ease-in-out;
}
.ring.move{
    top:110px;
    left:130px;
}

.glow{
    font-size:2rem;
    font-weight:bold;
    animation:glow 1.5s infinite alternate;
}
@keyframes glow{
    from{text-shadow:0 0 10px white;}
    to{text-shadow:0 0 30px gold;}
}

.fade-img{
    width:200px;
    border-radius:20px;
    margin:10px;
    opacity:0;
    transition:1s;
}
.show{ opacity:1;}
</style>
</head>

<body>

<!-- INTRO -->
<div id="intro">
    <div id="introText">
        In a world full of chaos, trauma calls, and night shifts...<br><br>
        There was one constant vital sign in my life...<br><br>
        Ayaa ♥️
    </div>
</div>

<!-- LOCK -->
<div id="locked">
    <h1>Counting down to midnight...</h1>
    <p id="timer"></p>
</div>

<!-- MAIN -->
<div class="container" id="main">
    <h1>Will you be my Valentine, Ayaa ♥️?</h1>
    <button class="yes" onclick="accept()">Yes 💖</button>
    <button class="no" onclick="moveNo()">No 🙈</button>
</div>

<!-- CELEBRATION -->
<div id="celebration" style="display:none;">
    <h1>She said YES ❤️</h1>
    <div class="hand-container">
        <img src="hand.png" class="hand">
        <img src="ring.png" class="ring" id="ringAnim">
    </div>
    <div class="glow">Future Mrs. Dr. Amr 💍</div>
</div>

<audio id="music" src="love.mp3"></audio>
<audio id="ringSound" src="ring.mp3"></audio>

<script>

/* CREATE STARS */
for(let i=0;i<100;i++){
    let star=document.createElement("div");
    star.classList.add("star");
    star.style.left=Math.random()*100+"%";
    star.style.top=Math.random()*100+"%";
    document.body.appendChild(star);
}

/* INTRO TRANSITION */
setTimeout(()=>{
    document.getElementById("intro").style.display="none";
    document.getElementById("locked").style.display="block";
},6000);

/* COUNTDOWN */
const target=new Date();
target.setHours(24,0,0,0);

function updateTimer(){
    const now=new Date();
    const diff=target-now;

    if(diff<=0){
        document.getElementById("locked").style.display="none";
        document.getElementById("main").style.display="block";
        document.body.classList.add("main-bg");
        return;
    }

    const h=Math.floor(diff/(1000*60*60));
    const m=Math.floor((diff%(1000*60*60))/(1000*60));
    const s=Math.floor((diff%(1000*60))/1000);

    document.getElementById("timer").innerHTML=h+"h "+m+"m "+s+"s";
}
setInterval(updateTimer,1000);

/* BUTTONS */
function moveNo(){
    let btn=document.querySelector(".no");
    btn.style.position="absolute";
    btn.style.top=Math.random()*80+"%";
    btn.style.left=Math.random()*80+"%";
}

function accept(){
    document.getElementById("main").style.display="none";
    document.getElementById("celebration").style.display="block";
    document.getElementById("music").play();

    setTimeout(()=>{
        document.getElementById("ringAnim").classList.add("move");
        document.getElementById("ringSound").play();
    },800);
}
</script>

</body>
</html>
