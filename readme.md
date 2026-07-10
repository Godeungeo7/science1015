# science1015
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>이재경의 방</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    overflow:hidden;
    font-family:'Malgun Gothic',sans-serif;
    background:radial-gradient(circle at bottom,#090b2f,#000);
}

.space{
    position:fixed;
    width:100%;
    height:100%;
    overflow:hidden;
}

/* 별 */
.star{
    position:absolute;
    width:2px;
    height:2px;
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
    border-radius:50%;
    animation:movePlanet linear infinite;
}

@keyframes movePlanet{
    from{
        transform:translateX(-250px);
    }
    to{
        transform:translateX(calc(100vw + 250px));
    }
}

/* 가운데 */
.center{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    text-align:center;
    color:white;
}

h1{
    font-size:52px;
    text-shadow:0 0 20px cyan;
    margin-bottom:40px;
}

button{
    padding:18px 50px;
    font-size:24px;
    border:none;
    border-radius:40px;
    cursor:pointer;
    background:linear-gradient(45deg,#00d2ff,#3a7bd5);
    color:white;
    transition:.3s;
}

button:hover{
    transform:scale(1.08);
    box-shadow:0 0 25px cyan;
}
</style>
</head>

<body>

<div class="space" id="space"></div>

<div class="center">
    <h1>안녕하세요<br>이재경의 방입니다</h1>

    <button onclick="startApp()">
        시작하기
    </button>
</div>

<script>

const space=document.getElementById("space");

// 별 생성
for(let i=0;i<250;i++){

    let star=document.createElement("div");

    star.className="star";

    star.style.left=Math.random()*100+"%";
    star.style.top=Math.random()*100+"%";
    star.style.animationDuration=(Math.random()*3+1)+"s";

    space.appendChild(star);
}

// 행성 색상
const colors=[
"#4fc3f7",
"#ff9800",
"#8bc34a",
"#ab47bc",
"#ff5252",
"#ffee58",
"#90caf9"
];

// 행성 생성
for(let i=0;i<8;i++){

    let p=document.createElement("div");

    let size=Math.random()*90+40;

    p.className="planet";

    p.style.width=size+"px";
    p.style.height=size+"px";

    p.style.background=colors[Math.floor(Math.random()*colors.length)];

    p.style.top=Math.random()*80+"%";

    p.style.animationDuration=(20+Math.random()*25)+"s";

    p.style.animationDelay=(-Math.random()*30)+"s";

    space.appendChild(p);
}

function startApp(){
    alert("이재경의 방에 오신 것을 환영합니다!");
}

</script>

</body>
</html>
