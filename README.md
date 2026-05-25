<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<title>SocialVertise Official</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
}

body{
    background:#060b1a;
    min-height:100vh;
    overflow:hidden;
    display:flex;
    align-items:center;
    justify-content:center;
    position:relative;
}

/* Animated Background */

.bg{
    position:absolute;
    width:100%;
    height:100%;
    overflow:hidden;
    z-index:0;
}

.circle{
    position:absolute;
    border-radius:50%;
    filter:blur(90px);
    animation:float 10s infinite ease-in-out;
}

.circle:nth-child(1){
    width:300px;
    height:300px;
    background:#00d9ff;
    top:-80px;
    left:-100px;
}

.circle:nth-child(2){
    width:350px;
    height:350px;
    background:#ff006a;
    bottom:-120px;
    right:-100px;
    animation-delay:2s;
}

.circle:nth-child(3){
    width:250px;
    height:250px;
    background:#ffae00;
    top:40%;
    left:50%;
    transform:translate(-50%,-50%);
    animation-delay:4s;
}

@keyframes float{
    0%{transform:translateY(0px);}
    50%{transform:translateY(30px);}
    100%{transform:translateY(0px);}
}

/* Main Card */

.container{
    width:92%;
    max-width:430px;
    padding:38px 28px;
    border-radius:30px;
    background:rgba(255,255,255,0.07);
    border:1px solid rgba(255,255,255,0.1);
    backdrop-filter:blur(22px);
    box-shadow:0 20px 60px rgba(0,0,0,0.55);
    text-align:center;
    position:relative;
    z-index:10;
}

/* Logo */

.logo-wrap{
    width:140px;
    height:140px;
    margin:auto;
    border-radius:50%;
    background:rgba(255,255,255,0.06);
    display:flex;
    align-items:center;
    justify-content:center;
    border:2px solid rgba(255,255,255,0.1);
    box-shadow:0 10px 30px rgba(0,0,0,0.45);
    margin-bottom:22px;
}

.logo{
    width:105px;
    object-fit:contain;
}

/* Heading */

h1{
    color:#fff;
    font-size:34px;
    font-weight:800;
    line-height:1.2;
}

.gradient{
    background:linear-gradient(90deg,#00d9ff,#ff3c7e,#ffb300);
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
}

.desc{
    color:#c7c7c7;
    font-size:15px;
    line-height:1.8;
    margin-top:16px;
    margin-bottom:30px;
}

/* Countdown */

.timer-box{
    width:120px;
    height:120px;
    margin:auto;
    border-radius:50%;
    background:linear-gradient(135deg,#00d9ff,#6f00ff,#ff006a);
    padding:5px;
    animation:pulse 1.4s infinite;
    margin-bottom:28px;
}

.timer-inner{
    width:100%;
    height:100%;
    background:#0c1224;
    border-radius:50%;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
}

#count{
    color:#fff;
    font-size:42px;
    font-weight:800;
}

.small{
    color:#b8b8b8;
    font-size:12px;
    letter-spacing:2px;
}

@keyframes pulse{
    0%{transform:scale(1);}
    50%{transform:scale(1.06);}
    100%{transform:scale(1);}
}

/* Button */

.join-btn{
    width:100%;
    display:inline-block;
    padding:17px;
    border-radius:18px;
    text-decoration:none;
    color:#fff;
    font-size:17px;
    font-weight:700;
    background:linear-gradient(90deg,#0088cc,#00c3ff);
    box-shadow:0 12px 30px rgba(0,195,255,0.4);
    transition:0.3s;
}

.join-btn:hover{
    transform:translateY(-3px);
}

.secure{
    margin-top:18px;
    color:#9f9f9f;
    font-size:13px;
}

/* Mobile */

@media(max-width:480px){

    .container{
        padding:30px 22px;
    }

    .logo-wrap{
        width:120px;
        height:120px;
    }

    .logo{
        width:90px;
    }

    h1{
        font-size:28px;
    }

    .desc{
        font-size:14px;
    }

    .timer-box{
        width:105px;
        height:105px;
    }

    #count{
        font-size:36px;
    }

    .join-btn{
        padding:15px;
        font-size:16px;
    }
}

</style>
</head>

<body>

<div class="bg">
    <div class="circle"></div>
    <div class="circle"></div>
    <div class="circle"></div>
</div>

<div class="container">

    <!-- Logo -->
    <div class="logo-wrap">
        <img src="logo.png" class="logo">
    </div>

    <!-- Heading -->
    <h1>
        Join <span class="gradient">SocialVertise</span>
    </h1>

    <!-- Description -->
    <div class="desc">
        Unlock premium Telegram resources, latest earning tricks,
        social growth methods & exclusive updates instantly.
    </div>

    <!-- Countdown -->
    <div class="timer-box">
        <div class="timer-inner">
            <div id="count">5</div>
            <div class="small">SECONDS</div>
        </div>
    </div>

    <!-- Join Button -->
    <a href="tg://resolve?domain=sociel_vertise"
       class="join-btn"
       id="joinBtn">
       JOIN TELEGRAM NOW
    </a>

    <div class="secure">
        Auto redirecting to Telegram App...
    </div>

</div>

<script>

let timeLeft = 5;

const count = document.getElementById("count");

const timer = setInterval(() => {

    timeLeft--;

    count.innerHTML = timeLeft;

    if(timeLeft <= 0){

        clearInterval(timer);

        // Open Telegram App
        window.location.href = "tg://resolve?domain=sociel_vertise";

        // Fallback if app not installed
        setTimeout(() => {
            window.location.href = "https://t.me/sociel_vertise";
        },2000);
    }

},1000);

</script>

</body>
</html>
