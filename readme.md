<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>재경이의 방</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:"Comic Sans MS", "맑은 고딕", sans-serif;
}

body{
    overflow:hidden;
    height:100vh;
    background:linear-gradient(#000010,#06002e,#13003d);
}

/* 별 */
.star{
    position:absolute;
    width:3px;
    height:3px;
    background:white;
    border-radius:50%;
    animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
    from{opacity:.2;}
    to{opacity:1;}
}

/* 행성 */
.planet{
    position:absolute;
    font-size:80px;
    animation:floatPlanet 9s ease-in-out infinite;
}

/* 외계인 */
.alien{
    position:absolute;
    font-size:60px;
    animation:floatAlien 6s ease-in-out infinite;
}

@keyframes floatPlanet{
    0%{transform:translateY(0px) rotate(0deg);}
    50%{transform:translateY(-25px) rotate(8deg);}
    100%{transform:translateY(0px) rotate(0deg);}
}

@keyframes floatAlien{
    0%{transform:translate(0,0);}
    25%{transform:translate(20px,-20px);}
    50%{transform:translate(-20px,-40px);}
    75%{transform:translate(15px,-20px);}
    100%{transform:translate(0,0);}
}

/* 가운데 */
.center{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    text-align:center;
}

h1{
    color:white;
    font-size:42px;
    text-shadow:4px 4px hotpink;
    animation:shake 2s infinite;
}

@keyframes shake{
    0%{transform:rotate(-1deg);}
    50%{transform:rotate(1deg);}
    100%{transform:rotate(-1deg);}
}

button{
    margin-top:35px;
    padding:18px 40px;
    font-size:22px;
    border:none;
    border-radius:40px;
    cursor:pointer;
    background:yellow;
    color:black;
    box-shadow:5px 5px 0 orange;
    transition:.2s;
}

button:hover{
    transform:rotate(-3deg) scale(1.1);
    background:pink;
}

/* 위치 */
#p1{top:10%;left:10%;}
#p2{top:70%;left:80%;animation-delay:2s;}
#p3{top:20%;left:75%;animation-delay:1s;}

#a1{top:65%;left:15%;}
#a2{top:15%;left:45%;animation-delay:2s;}
#a3{top:80%;left:50%;animation-delay:1s;}
</style>

</head>
<body>

<!-- 별 생성 -->
<script>
for(let i=0;i<120;i++){
    const star=document.createElement("div");
    star.className="star";
    star.style.left=Math.random()*100+"vw";
    star.style.top=Math.random()*100+"vh";
    star.style.animationDuration=(Math.random()*3+1)+"s";
    document.body.appendChild(star);
}
</script>

<div class="planet" id="p1">🪐</div>
<div class="planet" id="p2">🌍</div>
<div class="planet" id="p3">🌕</div>

<div class="alien" id="a1">👽</div>
<div class="alien" id="a2">🛸👽</div>
<div class="alien" id="a3">👾</div>

<div class="center">
    <h1>
        안녕하세요!<br>
        재경이의 방에 오신 걸 환영합니다
    </h1>

    <button onclick="startRoom()">🚀 시작하기</button>
</div>

<script>
function startRoom(){
    alert("👽 환영합니다! 재경이의 방으로 출발~");
}
</script>

</body>
</html>// 외계인 도망가기
const alien = document.getElementById("alien");

alien.onclick = () => {
    alien.style.transition="1s";
    alien.style.transform="translate(1800px,-800px) rotate(720deg)";
};// 행성이 마우스 따라오기
document.addEventListener("mousemove",(e)=>{

const planet=document.getElementById("planet");

planet.style.left=e.clientX/12+"px";
planet.style.top=e.clientY/12+"px";

});// XP 로딩창
function startRoom(){

document.getElementById("loading").style.display="flex";

setTimeout(()=>{
alert("👽 접속 성공!");
document.getElementById("loading").style.display="none";
},3000);

}<div id="loading">

<div class="xp">

<div class="title">
Windows XP
</div>

<div class="body">

📡 삐빅... 접속 중...

<br><br>

<progress></progress>

</div>

</div>

</div>#loading{
display:none;
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:rgba(0,0,0,.6);
justify-content:center;
align-items:center;
}

.xp{
width:330px;
background:#ece9d8;
border:3px solid #245edb;
font-family:Tahoma;
}

.title{
background:#245edb;
color:white;
padding:8px;
font-weight:bold;
}

.body{
padding:25px;
text-align:center;
}body{
cursor:url("star.cur"),auto;
}body{
cursor:url("star.png") 16 16,auto;
}function beep(){

const ctx=new AudioContext();

const osc=ctx.createOscillator();

osc.type="triangle";

osc.frequency.value=850;

osc.connect(ctx.destination);

osc.start();

osc.stop(ctx.currentTime+0.15);

}<button onclick="beep();startRoom();">
🚀 시작하기
</button>
