<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500&family=Great+Vibes&display=swap" rel="stylesheet">

<style>

body{
margin:0;
font-family:'Poppins',sans-serif;
background:linear-gradient(135deg,#ff5f9e,#ffc371,#ff9a9e);
height:100vh;
display:flex;
justify-content:center;
align-items:center;
overflow:hidden;
color:white;
text-align:center;
}

.container{
background:rgba(255,255,255,0.15);
backdrop-filter:blur(10px);
padding:30px;
border-radius:20px;
width:90%;
max-width:420px;
box-shadow:0 0 25px rgba(0,0,0,0.2);
}

h1{
font-family:'Great Vibes',cursive;
font-size:2.8rem;
}

button{
padding:12px 25px;
border:none;
border-radius:25px;
font-size:1rem;
cursor:pointer;
margin:10px;
transition:0.3s;
}

.yes{
background:#ff3366;
color:white;
}

.no{
background:white;
color:#ff3366;
position:absolute;
}

.popup{
position:fixed;
top:0;left:0;
width:100%;
height:100%;
background:rgba(0,0,0,0.7);
display:none;
justify-content:center;
align-items:center;
z-index:999;
}

.popup-box{
background:white;
color:#ff3366;
padding:25px;
border-radius:15px;
width:80%;
max-width:300px;
font-weight:bold;
}

input{
transform:scale(1.2);
}

.shake{
animation:shake 0.5s;
}

@keyframes shake{
0%{transform:translateX(0)}
25%{transform:translateX(-10px)}
50%{transform:translateX(10px)}
75%{transform:translateX(-10px)}
100%{transform:translateX(0)}
}

.firework{
position:absolute;
font-size:25px;
animation:explode 2s linear;
}

@keyframes explode{
0%{opacity:1;transform:translateY(0)}
100%{opacity:0;transform:translateY(-200px)}
}

</style>
</head>

<body>

<audio id="music" autoplay loop>
<source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_9b90c2b2c5.mp3?filename=romantic-piano-112194.mp3">
</audio>

<!-- LEVEL 1 -->
<div class="container" id="level1">

<h1>My Love ❤️</h1>

<p>Are you willing to take this risk with me?</p>

<button class="yes" onclick="level1Pass()">Yes 💕</button>

<button class="no" id="no1">No 🙈</button>

</div>


<!-- LEVEL 2 -->
<div class="container" id="level2" style="display:none">

<h2>This is gonna be a long journey…</h2>

<p>
Full of ups and downs…<br>
Don't you leave my side baby 💖<br><br>

We will get through everything if our love is strong.<br>
I will be there for you always.<br><br>

Maybe you be there for me,<br>
Choose me over everyone like I do ❤️
</p>

<br>

<label>
<input type="checkbox" id="agree">
 I agree to love you forever 💍
</label>

<br><br>

<button class="yes" onclick="level2Pass()">Continue 💘</button>

</div>


<!-- LEVEL 3 -->
<div class="container" id="level3" style="display:none">

<h1>Will You Be My Valentine? 💖</h1>

<button class="yes" onclick="finalYes()">Yes 😍</button>

<button class="no" id="no2">No 😜</button>

</div>


<!-- POPUP -->
<div class="popup" id="popup">
<div class="popup-box" id="popupText"></div>
</div>


<script>

// LEVEL 1 NO BUTTON
const no1 = document.getElementById("no1");
no1.addEventListener("click", ()=>{
no1.style.top = Math.random()*80+"%";
no1.style.left = Math.random()*80+"%";
});

// LEVEL 3 NO BUTTON
const no2 = document.getElementById("no2");
no2.addEventListener("click", ()=>{
document.body.classList.add("shake");
showPopup("💥 WASTED 💥<br><br>Do you want to try again?<br><br><button onclick='resetGame()'>Try Again</button>");

setTimeout(()=>{
document.body.classList.remove("shake");
},500);
});

function level1Pass(){
showPopup("🎉 Level 1 Cleared! 🎉");
setTimeout(()=>{
closePopup();
document.getElementById("level1").style.display="none";
document.getElementById("level2").style.display="block";
},1500);
}

function level2Pass(){
if(!document.getElementById("agree").checked){
alert("Please accept the terms first 😘");
return;
}

document.getElementById("level2").style.display="none";
document.getElementById("level3").style.display="block";
}

function finalYes(){
createFireworks();
showPopup("💖 You Successfully Signed Up For Life With Me 💖<br><br>No Cancellation. No Return. Only Love 😘🔥");
}

function showPopup(text){
document.getElementById("popup").style.display="flex";
document.getElementById("popupText").innerHTML=text;
}

function closePopup(){
document.getElementById("popup").style.display="none";
}

function resetGame(){
closePopup();
document.getElementById("level3").style.display="none";
document.getElementById("level1").style.display="block";
}

// FIREWORKS
function createFireworks(){
for(let i=0;i<30;i++){
let fw=document.createElement("div");
fw.className="firework";
fw.innerHTML="✨🎆💖";
fw.style.left=Math.random()*100+"vw";
fw.style.bottom="0px";

document.body.appendChild(fw);

setTimeout(()=>{fw.remove()},2000);
}
}

</script>

</body>
</html>
