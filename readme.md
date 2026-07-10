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
    font-family:'Pretendard',sans-serif;
    height:100vh;
    background:
    radial-gradient(circle at top,#332b7d,#130f2d 40%,#04020d 90%);
}

/* 별 */
.stars{
    position:absolute;
    width:100%;
    height:100%;
}

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
    to{
        opacity:1;
        transform:scale(1.8);
    }
}

/* 행성 */

.planet{
    position:absolute;
    border-radius:50%;
    animation:float 10s ease-in-out infinite;
    box-shadow:0 0 40px rgba(255,255,255,.4);
}

.p1{
    width:180px;
    height:180px;
    background:linear-gradient(45deg,#ffb347,#ff5f6d);
    top:8%;
    left:10%;
}

.p2{
    width:120px;
    height:120px;
    background:linear-gradient(45deg,#42e695,#3bb2b8);
    bottom:12%;
    right:8%;
    animation-duration:14s;
}

.p3{
    width:90px;
    height:90px;
    background:linear-gradient(45deg,#8EC5FC,#E0C3FC);
    top:20%;
    right:20%;
    animation-duration:12s;
}

@keyframes float{
    0%{
        transform:translateY(0px);
    }
    50%{
        transform:translateY(-25px);
    }
    100%{
        transform:translateY(0px);
    }
}

/* 귀여운 외계인 */

.alien{
    position:absolute;
    font-size:70px;
    animation:alienFloat 8s ease-in-out infinite;
}

.a1{
    left:25%;
    top:60%;
}

.a2{
    right:28%;
    top:30%;
    animation-duration:11s;
}

@keyframes alienFloat{
    0%{
        transform:translateY(0px) rotate(-8deg);
    }
    50%{
        transform:translateY(-35px) rotate(8deg);
    }
    100%{
        transform:translateY(0px) rotate(-8deg);
    }
}

/* 중앙 */

.center{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    text-align:center;
    color:white;
    z-index:10;
}

h1{
    font-size:55px;
    text-shadow:
    0 0 20px #8cf,
    0 0 50px #8cf,
    0 0 80px white;
    margin-bottom:30px;
}

button{
    padding:18px 55px;
    font-size:22px;
    border:none;
    border-radius:50px;
    cursor:pointer;
    color:white;
    background:linear-gradient(45deg,#6a5cff,#00d4ff);
    transition:.3s;
    box-shadow:0 0 30px #66ccff;
}

button:hover{
    transform:scale(1.08);
    box-shadow:0 0 50px cyan;
}
</style>

</head>

<body>

<div class="stars"></div>

<div class="planet p1"></div>
<div class="planet p2"></div>
<div class="planet p3"></div>

<div class="alien a1">👽</div>
<div class="alien a2">🛸👽</div>

<div class="center">
<h1>안녕하세요.<br>이재경의 방에 오신 것을 환영합니다.</h1>

<button onclick="location.href='main.html'">
🚀 시작하기
</button>

</div>

<script>

const stars=document.querySelector(".stars");

for(let i=0;i<220;i++){

const star=document.createElement("div");

star.className="star";

star.style.left=Math.random()*100+"%";

star.style.top=Math.random()*100+"%";

star.style.animationDelay=Math.random()*3+"s";

star.style.width=Math.random()*4+1+"px";

star.style.height=star.style.width;

stars.appendChild(star);

}

</script>

</body>
</html>
