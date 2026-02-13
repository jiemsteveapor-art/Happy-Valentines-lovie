<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>For You ❤️</title>

<style>
body{
margin:0;
overflow:hidden;
background:linear-gradient(to bottom right,#ff7eb3,#ff758c);
font-family:Arial;
}

/* Floating Hearts */
.heart{
position:absolute;
color:rgba(255,255,255,0.7);
font-size:20px;
animation:float 10s linear infinite;
}
@keyframes float{
from{transform:translateY(100vh);}
to{transform:translateY(-10vh);}
}

/* Popup */
.popup{
position:fixed;
top:50%;
left:50%;
transform:translate(-50%,-50%);
background:white;
width:85%;
max-width:500px;
padding:30px;
border-radius:20px;
box-shadow:0 15px 40px rgba(0,0,0,0.3);
text-align:center;
animation:fadeIn 1.5s ease-in-out;
z-index:10;
}
@keyframes fadeIn{
from{opacity:0;transform:translate(-50%,-60%);}
to{opacity:1;transform:translate(-50%,-50%);}
}
.popup button{
margin-top:20px;
padding:10px 25px;
border:none;
border-radius:25px;
background-color:#ff4e78;
color:white;
cursor:pointer;
}
.popup button:hover{
background-color:#ff1e56;
transform:scale(1.1);
}

/* Surprise Main */
.main{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);
color:white;
text-align:center;
display:none;
}

/* Glowing Sunflower */
.sunflower{
font-size:90px;
animation:glow 2s ease-in-out infinite alternate;
}
@keyframes glow{
from{
text-shadow:0 0 10px #fff,0 0 20px #ffd700,0 0 30px #ffea00;
transform:scale(1);
}
to{
text-shadow:0 0 20px #fff,0 0 40px #ffd700,0 0 60px #ffea00;
transform:scale(1.2);
}
}

/* Gallery */
.gallery{
display:flex;
flex-wrap:wrap;
justify-content:center;
gap:15px;
margin-top:20px;
}
.gallery img{
width:120px;
height:120px;
object-fit:cover;
border-radius:15px;
opacity:0;
transform:scale(0.5);
animation:fadeIn 1s forwards;
}

/* Fade One by One */
.gallery img:nth-child(1){animation-delay:0s;}
.gallery img:nth-child(2){animation-delay:1s;}
.gallery img:nth-child(3){animation-delay:2s;}
.gallery img:nth-child(4){animation-delay:3s;}
.gallery img:nth-child(5){animation-delay:4s;}

@keyframes fadeIn{
to{
opacity:1;
transform:scale(1);
}
}
  
}
@keyframes pop{
to{
opacity:1;
transform:scale(1);
}
}
</style>

</head>

<body>

<!-- MUSIC -->
<audio id="bgMusic" loop>
<source src="music.mp3" type="audio/mpeg">
</audio>

<!-- POPUP -->
<div class="popup" id="popup">
<h2>Click Me ❤️</h2>
<p>I have a surprise for you 🌻</p>
<button onclick="closePopup()">Open</button>
</div>

<!-- SURPRISE -->
<div class="main" id="main">

<div class="sunflower">🌻</div>

<h1 id="typingText"></h1>

<div class="gallery">
<img src="626474170_1917435798866190_7360438315416646286_n.jpg">
<img src="628462705_876223445242877_4005428426257665027_n.jpg">
<img src="631265316_773878738712204_6934332184240382434_n.jpg">
<img src="631079412_1233055554890720_254445144777351985_n.jpg">
<img src="626755290_1304506508151559_4620056559209312483_n.jpg">
</div>

</div>

<script>

/* Floating Hearts */
for(let i=0;i<25;i++){
const heart=document.createElement("div");
heart.classList.add("heart");
heart.innerHTML="❤";
heart.style.left=Math.random()*100+"vw";
heart.style.animationDuration=(5+Math.random()*5)+"s";
document.body.appendChild(heart);
}

/* Popup Open */
function closePopup(){
document.getElementById("popup").style.display="none";
document.getElementById("main").style.display="block";
document.getElementById("bgMusic").play();
typeWriter();
}

/* Typing Text */
let i=0;
let text="You are my sunshine 🌻 Thank you for making my life beautiful ❤️";
let speed=60;

function typeWriter(){
if(i<text.length){
document.getElementById("typingText").innerHTML+=text.charAt(i);
i++;
setTimeout(typeWriter,speed);
}
}

</script>

</body>
</html>
