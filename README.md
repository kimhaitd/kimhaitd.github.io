<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy Birthday Nguyễn Hạ My 💖</title>

  <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

  <style>
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
    }

    body{
      font-family:'Poppins',sans-serif;
      overflow:hidden;
      height:100vh;
      background:black;
      color:white;
    }

    /* LOADING SCREEN */
    #loading{
      position:fixed;
      inset:0;
      background:black;
      display:flex;
      justify-content:center;
      align-items:center;
      flex-direction:column;
      z-index:9999;
      animation:fadeOut 2s forwards;
      animation-delay:3s;
    }

    #loading h1{
      font-size:3rem;
      font-family:'Pacifico',cursive;
      animation:pulse 1.5s infinite;
    }

    #loading p{
      margin-top:20px;
      opacity:0.8;
    }

    @keyframes pulse{
      0%,100%{transform:scale(1);}
      50%{transform:scale(1.1);}
    }

    @keyframes fadeOut{
      to{
        opacity:0;
        visibility:hidden;
      }
    }

    /* BACKGROUND */
    .background{
      position:fixed;
      inset:0;
      background:url('background.jpg') center/cover no-repeat;
      transform:scale(1.1);
      animation:zoomBg 20s infinite alternate;
      filter:brightness(0.45);
    }

    @keyframes zoomBg{
      from{transform:scale(1.1);}
      to{transform:scale(1.25);}
    }

    .overlay{
      position:fixed;
      inset:0;
      background:linear-gradient(to top, rgba(0,0,0,0.7), rgba(255,105,180,0.15));
    }

    /* RAINBOW LIGHT */
    .rainbow{
      position:fixed;
      width:200%;
      height:200%;
      background:conic-gradient(red,orange,yellow,green,blue,purple,red);
      opacity:0.08;
      animation:rotate 20s linear infinite;
      top:-50%;
      left:-50%;
      z-index:1;
    }

    @keyframes rotate{
      from{transform:rotate(0deg);}
      to{transform:rotate(360deg);}
    }

    /* MAIN CONTENT */
    .content{
      position:relative;
      z-index:5;
      width:100%;
      height:100vh;
      display:flex;
      flex-direction:column;
      justify-content:center;
      align-items:center;
      text-align:center;
      padding:20px;
      animation:cinematic 2s ease;
    }

    @keyframes cinematic{
      from{
        opacity:0;
        transform:translateY(50px) scale(0.9);
      }
      to{
        opacity:1;
        transform:translateY(0) scale(1);
      }
    }

    h1{
      font-size:5rem;
      font-family:'Pacifico',cursive;
      text-shadow:0 0 30px rgba(255,255,255,0.8);
      animation:floatTitle 3s ease-in-out infinite;
    }

    @keyframes floatTitle{
      0%,100%{transform:translateY(0);}
      50%{transform:translateY(-10px);}
    }

    .subtitle{
      font-size:1.4rem;
      margin-top:10px;
      opacity:0.9;
    }

    /* COUNTDOWN */
    .countdown{
      margin-top:25px;
      display:flex;
      gap:20px;
    }

    .time-box{
      background:rgba(255,255,255,0.12);
      backdrop-filter:blur(12px);
      padding:18px;
      border-radius:20px;
      min-width:100px;
      box-shadow:0 10px 25px rgba(0,0,0,0.25);
      transform-style:preserve-3d;
      animation:cardFloat 4s ease-in-out infinite;
    }

    @keyframes cardFloat{
      0%,100%{transform:translateY(0) rotateX(0deg);}
      50%{transform:translateY(-10px) rotateX(8deg);}
    }

    .time-box h2{
      font-size:2rem;
    }

    /* SLIDESHOW */
    .slideshow{
      margin-top:40px;
      width:320px;
      height:420px;
      position:relative;
      perspective:1000px;
    }

    .slide{
      position:absolute;
      width:100%;
      height:100%;
      border-radius:25px;
      overflow:hidden;
      box-shadow:0 15px 40px rgba(0,0,0,0.4);
      animation:slideShow 18s infinite;
      opacity:0;
      transform:rotateY(20deg) scale(0.9);
    }

    .slide img{
      width:100%;
      height:100%;
      object-fit:cover;
    }

    .slide:nth-child(1){animation-delay:0s;}
    .slide:nth-child(2){animation-delay:6s;}
    .slide:nth-child(3){animation-delay:12s;}

    @keyframes slideShow{
      0%{opacity:0;transform:translateX(100px) rotateY(30deg) scale(0.8);}
      10%,30%{opacity:1;transform:translateX(0) rotateY(0deg) scale(1);}
      40%{opacity:0;transform:translateX(-100px) rotateY(-30deg) scale(0.8);}
      100%{opacity:0;}
    }

    /* LETTER */
    .envelope{
      margin-top:40px;
      width:220px;
      height:140px;
      position:relative;
      cursor:pointer;
      transition:1s;
    }

    .envelope-body{
      position:absolute;
      width:100%;
      height:100%;
      background:#fff;
      border-radius:15px;
      overflow:hidden;
      box-shadow:0 15px 30px rgba(0,0,0,0.4);
    }

    .envelope-top{
      position:absolute;
      width:0;
      height:0;
      border-left:110px solid transparent;
      border-right:110px solid transparent;
      border-top:75px solid #ff6f91;
      top:0;
      transform-origin:top;
      transition:1s;
      z-index:2;
    }

    .letter{
      position:absolute;
      width:90%;
      height:90%;
      background:#fffafc;
      left:5%;
      top:5%;
      border-radius:12px;
      padding:15px;
      color:#ff4d79;
      overflow:auto;
      transform:translateY(50px);
      opacity:0;
      transition:1s;
      font-size:0.95rem;
    }

    .envelope.open .envelope-top{
      transform:rotateX(180deg);
    }

    .envelope.open .letter{
      transform:translateY(-120px);
      opacity:1;
    }

    /* HEARTS + SNOW */
    .particle{
      position:absolute;
      bottom:-50px;
      animation:rise linear infinite;
      opacity:0.8;
      z-index:2;
    }

    @keyframes rise{
      from{
        transform:translateY(0) rotate(0deg);
        opacity:0;
      }
      20%{opacity:1;}
      to{
        transform:translateY(-120vh) rotate(360deg);
        opacity:0;
      }
    }

    /* FIREWORK */
    .firework{
      position:absolute;
      width:6px;
      height:6px;
      border-radius:50%;
      background:white;
      animation:explode 1s ease-out infinite;
    }

    @keyframes explode{
      from{
        transform:scale(1);
        opacity:1;
      }
      to{
        transform:scale(15);
        opacity:0;
      }
    }

    @media(max-width:768px){
      h1{font-size:3rem;}

      .countdown{
        flex-wrap:wrap;
        justify-content:center;
      }

      .slideshow{
        width:260px;
        height:340px;
      }
    }
  </style>
</head>
<body>

<div id="loading">
  <h1>Loading Love... 💖</h1>
  <p>Đang chuẩn bị điều bất ngờ cho Nguyễn Hạ My ✨</p>
</div>

<div class="background"></div>
<div class="overlay"></div>
<div class="rainbow"></div>

<div id="introCinematic">
  <video autoplay muted loop id="bgVideo" style="position:fixed; inset:0; width:100%; height:100%; object-fit:cover; z-index:-2; opacity:0.25;">
    <source src="cinematic.mp4" type="video/mp4">
  </video>

  <div id="introText" style="position:fixed; inset:0; display:flex; justify-content:center; align-items:center; flex-direction:column; z-index:10; background:rgba(0,0,0,0.6); animation:introFade 8s forwards;">
    <h1 style="font-size:6rem;">For Nguyễn Hạ My ✨</h1>
    <p style="margin-top:20px; font-size:1.5rem; letter-spacing:3px;">A little universe made just for you 💖</p>
  </div>
</div>

<style>
@keyframes introFade{
  0%{opacity:1;}
  70%{opacity:1;}
  100%{opacity:0; visibility:hidden;}
}

.floating-memory{
  position:absolute;
  width:180px;
  height:220px;
  border-radius:25px;
  overflow:hidden;
  box-shadow:0 20px 40px rgba(0,0,0,0.35);
  animation:memoryFloat 10s ease-in-out infinite;
  backdrop-filter:blur(10px);
}

.floating-memory img{
  width:100%;
  height:100%;
  object-fit:cover;
}

@keyframes memoryFloat{
  0%,100%{transform:translateY(0) rotate(-3deg);}
  50%{transform:translateY(-25px) rotate(3deg);}
}

.music-disc{
  position:fixed;
  top:20px;
  right:20px;
  width:90px;
  height:90px;
  border-radius:50%;
  background:rgba(255,255,255,0.15);
  backdrop-filter:blur(10px);
  display:flex;
  justify-content:center;
  align-items:center;
  font-size:2rem;
  animation:spin 5s linear infinite;
  z-index:999;
}

@keyframes spin{
  from{transform:rotate(0deg);}
  to{transform:rotate(360deg);}
}

.story-box{
  margin-top:30px;
  max-width:850px;
  padding:25px;
  background:rgba(255,255,255,0.12);
  border:1px solid rgba(255,255,255,0.2);
  border-radius:30px;
  backdrop-filter:blur(15px);
  line-height:2;
  animation:storyGlow 4s ease-in-out infinite;
}

@keyframes storyGlow{
  0%,100%{box-shadow:0 0 20px rgba(255,255,255,0.15);}
  50%{box-shadow:0 0 50px rgba(255,105,180,0.4);}
}

.typing-cursor::after{
  content:'|';
  animation:blink 0.8s infinite;
}

@keyframes blink{
  50%{opacity:0;}
}

.star-layer{
  position:fixed;
  inset:0;
  overflow:hidden;
  z-index:0;
}

.star{
  position:absolute;
  width:3px;
  height:3px;
  border-radius:50%;
  background:white;
  animation:twinkle 3s infinite;
}

@keyframes twinkle{
  0%,100%{opacity:0.2; transform:scale(1);}
  50%{opacity:1; transform:scale(2);}
}

.love-line{
  position:fixed;
  bottom:30px;
  left:50%;
  transform:translateX(-50%);
  font-size:1rem;
  letter-spacing:4px;
  opacity:0.75;
  animation:pulse 3s infinite;
}
</style>

<div class="star-layer" id="stars"></div>
<div class="music-disc">🎵</div>

<div class="floating-memory" style="top:15%; left:8%; animation-delay:0s;">
  <img src="photo4.jpg">
</div>

<div class="floating-memory" style="top:20%; right:8%; animation-delay:2s;">
  <img src="photo5.jpg">
</div>

<div class="floating-memory" style="bottom:10%; left:12%; animation-delay:4s; width:150px; height:190px;">
  <img src="photo6.jpg">
</div>

<div class="content">
  <h1>Happy Birthday</h1>
  <div class="subtitle">Nguyễn Hạ My — 24/05/2006 🎂</div>

  <div class="story-box">
    <div id="storyTyping" class="typing-cursor"></div>
  </div>

  <div class="countdown">
    <div class="time-box">
      <h2 id="days">00</h2>
      <p>Ngày</p>
    </div>

    <div class="time-box">
      <h2 id="hours">00</h2>
      <p>Giờ</p>
    </div>

    <div class="time-box">
      <h2 id="minutes">00</h2>
      <p>Phút</p>
    </div>

    <div class="time-box">
      <h2 id="seconds">00</h2>
      <p>Giây</p>
    </div>
  </div>

  <div class="slideshow">
    <div class="slide"><img src="photo1.jpg"></div>
    <div class="slide"><img src="photo2.jpg"></div>
    <div class="slide"><img src="photo3.jpg"></div>
  </div>

  <div class="envelope" id="envelope">
    <div class="envelope-top"></div>

    <div class="envelope-body">
      <div class="letter">
        Gửi Nguyễn Hạ My 💌<br><br>
        Chúc cậu có một tuổi mới thật hạnh phúc,
        luôn xinh đẹp, vui vẻ và gặp thật nhiều điều may mắn ✨
        <br><br>
        Mong rằng mọi điều tốt đẹp nhất sẽ đến với cậu trong tuổi mới.
        <br><br>
        Và cảm ơn vì đã xuất hiện trên thế giới này ❤️
      </div>
    </div>
  </div>
</div>

<audio autoplay loop controls style="position:fixed;bottom:10px;right:10px;z-index:999;opacity:0.7;">
  <source src="music.mp3" type="audio/mp3">
</audio>

<script>
  // COUNTDOWN
  const targetDate = new Date('May 24, 2026 00:00:00').getTime();

  setInterval(()=>{
    const now = new Date().getTime();
    const distance = targetDate - now;

    const days = Math.floor(distance / (1000*60*60*24));
    const hours = Math.floor((distance % (1000*60*60*24)) / (1000*60*60));
    const minutes = Math.floor((distance % (1000*60*60)) / (1000*60));
    const seconds = Math.floor((distance % (1000*60)) / 1000);

    document.getElementById('days').innerHTML = days;
    document.getElementById('hours').innerHTML = hours;
    document.getElementById('minutes').innerHTML = minutes;
    document.getElementById('seconds').innerHTML = seconds;
  },1000);

  // ENVELOPE
  document.getElementById('envelope').addEventListener('click', function(){
    this.classList.toggle('open');
  });

  // PARTICLES
  function createParticle(){
    const particle = document.createElement('div');
    particle.classList.add('particle');

    const icons = ['❤','✨','❄','💖','⭐'];
    particle.innerHTML = icons[Math.floor(Math.random()*icons.length)];

    particle.style.left = Math.random()*100 + 'vw';
    particle.style.fontSize = Math.random()*30 + 15 + 'px';
    particle.style.animationDuration = Math.random()*5 + 4 + 's';

    document.body.appendChild(particle);

    setTimeout(()=>{
      particle.remove();
    },9000);
  }

  setInterval(createParticle,250);

  // FIREWORKS
  function createFirework(){
    const firework = document.createElement('div');
    firework.classList.add('firework');

    firework.style.left = Math.random()*100 + 'vw';
    firework.style.top = Math.random()*60 + 'vh';

    document.body.appendChild(firework);

    setTimeout(()=>{
      firework.remove();
    },1000);
  }

  setInterval(createFirework,700);
</script>

<div class="love-line">MADE WITH LOVE FOR HẠ MY ✨</div>

<script>
const storyMessage = `Có những người xuất hiện giống như một vì sao nhỏ trong cuộc đời người khác ✨

Và có lẽ Nguyễn Hạ My chính là một người như vậy.

Ngày hôm nay không chỉ là sinh nhật của cậu, mà còn là ngày thế giới có thêm một người tuyệt vời để yêu thương 💖

Hy vọng tuổi mới sẽ mang đến cho cậu thật nhiều niềm vui, thật nhiều nụ cười và những điều đẹp đẽ nhất.`;

let storyIndex = 0;

function typeStory(){
  if(storyIndex < storyMessage.length){
    document.getElementById('storyTyping').innerHTML += storyMessage.charAt(storyIndex);
    storyIndex++;
    setTimeout(typeStory,35);
  }
}

setTimeout(typeStory,4000);

for(let i=0;i<120;i++){
  const star = document.createElement('div');
  star.classList.add('star');
  star.style.left = Math.random()*100 + 'vw';
  star.style.top = Math.random()*100 + 'vh';
  star.style.animationDelay = Math.random()*3 + 's';
  document.getElementById('stars').appendChild(star);
}
</script>

</body>
</html>
