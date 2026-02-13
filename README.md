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
    background:linear-gradient(135deg,#ff758c,#ff7eb3);
    font-family:'Poppins',sans-serif;
    text-align:center;
    overflow:hidden;
    color:white;
}
.container{
    position:relative;
    top:50%;
    transform:translateY(-50%);
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
.yes{
    background:white;
    color:#ff4e8a;
}
.no{
    background:transparent;
    border:2px solid white;
    color:white;
}
button:hover{
    transform:scale(1.1);
}
#countdown{
    font-size:2rem;
    margin:20px 0;
}
.hidden{
    display:none;
}
.heart{
    position:absolute;
    width:20px;
    height:20px;
    background:red;
    transform:rotate(45deg);
    animation:float 5s linear infinite;
}
.heart::before,.heart::after{
    content:'';
    position:absolute;
    width:20px;
    height:20px;
    background:red;
    border-radius:50%;
}
.heart::before{ top:-10px; left:0;}
.heart::after{ left:-10px; top:0;}
@keyframes float{
    0%{ bottom:-10px; opacity:1;}
    100%{ bottom:100%; opacity:0;}
}
#ring{
    font-size:4rem;
    animation:spin 2s infinite linear;
}
@keyframes spin{
    from{transform:rotate(0deg);}
    to{transform:rotate(360deg);}
}
.fade-img{
    width:200px;
    border-radius:20px;
    margin:10px;
    opacity:0;
    transition:1s;
}
.show{
    opacity:1;
}
</style>
</head>

<body>

<div class="container" id="main">
    <h1>Will you be my Valentine, <span id="name">Ayaa ♥️</span>?</h1>
    <div id="countdown">5</div>
    <button class="yes" onclick="accept()">Yes 💖</button>
    <button class="no" onclick="moveNo()">No 🙈</button>
</div>

<div id="celebration" class="hidden">
    <h1>She said YES 💍❤️</h1>
    <div id="ring">💍</div>
    <p style="font-size:1.5rem;">Emergency Resident… but permanently on call for You ♥️</p>
    <div>
        <img src="photo1.jpg" class="fade-img" id="img1">
        <img src="photo2.jpg" class="fade-img" id="img2">
    </div>
</div>

<audio id="music" src="your-music.mp3"></audio>

<script>
let count=5;
let countdownEl=document.getElementById("countdown");
let timer=setInterval(()=>{
    count--;
    countdownEl.innerText=count;
    if(count<=0){
        clearInterval(timer);
        countdownEl.innerText="Now choose wisely 😉";
    }
},1000);

function moveNo(){
    let btn=document.querySelector(".no");
    btn.style.position="absolute";
    btn.style.top=Math.random()*80+"%";
    btn.style.left=Math.random()*80+"%";
}

function accept(){
    document.getElementById("main").classList.add("hidden");
    document.getElementById("celebration").classList.remove("hidden");
    document.getElementById("music").play();
    createHearts();
    setTimeout(()=>{document.getElementById("img1").classList.add("show");},1000);
    setTimeout(()=>{document.getElementById("img2").classList.add("show");},2500);
}

function createHearts(){
    for(let i=0;i<30;i++){
        let heart=document.createElement("div");
        heart.classList.add("heart");
        heart.style.left=Math.random()*100+"%";
        heart.style.animationDuration=(3+Math.random()*2)+"s";
        document.body.appendChild(heart);
    }
}
</script>

</body>
</html>
