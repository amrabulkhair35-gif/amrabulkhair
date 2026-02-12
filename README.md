<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Ayaa ❤️</title>

<style>
body {
    margin: 0;
    padding: 0;
    background: linear-gradient(135deg, #ff4e75, #ff8fa3);
    font-family: 'Segoe UI', sans-serif;
    overflow: hidden;
    text-align: center;
    color: white;
}

.container {
    position: relative;
    top: 18vh;
}

h1 {
    font-size: 48px;
}

#name {
    font-size: 28px;
    margin-bottom: 15px;
}

#countdown {
    font-size: 40px;
    margin: 20px;
}

button {
    padding: 15px 35px;
    font-size: 20px;
    border: none;
    border-radius: 30px;
    margin: 15px;
    cursor: pointer;
    transition: 0.3s;
}

#yes {
    background: white;
    color: #ff4e75;
}

#yes:hover {
    transform: scale(1.1);
}

#no {
    background: #444;
    color: white;
    position: absolute;
}

/* Floating Hearts */
.heart {
    position: absolute;
    animation: float 6s linear infinite;
}

@keyframes float {
    from {
        transform: translateY(100vh) scale(1);
        opacity: 1;
    }
    to {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
    }
}

/* Ring animation */
#ring {
    position: absolute;
    width: 150px;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0);
    transition: 1s ease;
}

.show-ring {
    transform: translate(-50%, -50%) scale(1.2);
}

/* Photos */
.photo {
    width: 200px;
    border-radius: 20px;
    margin: 15px;
    opacity: 0;
    transition: opacity 2s ease;
}

.show-photo {
    opacity: 1;
}
</style>
</head>

<body>

<audio id="bgMusic" autoplay loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

<div class="container">
    <div id="name"></div>
    <h1>Will You Be My Valentine? 💖</h1>
    <div id="countdown">3</div>

    <button id="yes" onclick="sayYes()">Yes 💍</button>
    <button id="no" onmouseover="moveNo()">No 😢</button>
</div>

<img src="ring.png" id="ring">

<div id="photos" style="position:absolute; bottom:10%; width:100%;">
    <img src="photo1.jpg" class="photo" id="p1">
    <img src="photo2.jpg" class="photo" id="p2">
</div>

<script>

// Dynamic Name
let girlName = "Ayaa ♥️";
document.getElementById("name").innerHTML = "For " + girlName;

// Countdown
let count = 3;
let countdownElement = document.getElementById("countdown");

let interval = setInterval(() => {
    count--;
    if (count > 0) {
        countdownElement.innerHTML = count;
    } else {
        countdownElement.innerHTML = "💖";
        clearInterval(interval);
    }
}, 1000);

// YES action
function sayYes() {
    document.getElementById("ring").classList.add("show-ring");

    setTimeout(() => {
        document.getElementById("p1").classList.add("show-photo");
    }, 800);

    setTimeout(() => {
        document.getElementById("p2").classList.add("show-photo");
    }, 1500);

    document.querySelector(".container").innerHTML = `
        <h1>You Said YES!!! 💍❤️</h1>
        <h2>I Promise To Make You The Happiest, ${girlName} 😍</h2>
    `;
}

// NO button escape
function moveNo() {
    const button = document.getElementById("no");
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 50);
    button.style.left = x + "px";
    button.style.top = y + "px";
}

// Floating Hearts Generator
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = (Math.random() * 20 + 20) + "px";
    heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 6000);
}

setInterval(createHeart, 300);

</script>

</body>
</html>
