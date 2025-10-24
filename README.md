<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>YourGoatViper — Official</title>
<style>
/* ===== RESET ===== */
*{margin:0;padding:0;box-sizing:border-box;}
body{
  font-family:"Orbitron",sans-serif;
  background:url('IMG_1703.jpeg') no-repeat center center/cover;
  overflow-x:hidden;color:#fff;
}

/* ===== Overlay ===== */
body::before{
  content:"";
  position:fixed;inset:0;
  background:rgba(30,0,50,0.75);
  backdrop-filter:blur(10px);
  z-index:-1;
}

/* ===== Header ===== */
header{
  display:flex;justify-content:space-between;align-items:center;
  padding:20px 60px;position:fixed;width:100%;top:0;z-index:10;
  background:rgba(0,0,0,0.5);backdrop-filter:blur(8px);
}
.logo{
  font-size:1.8rem;font-weight:800;color:#b366ff;text-shadow:0 0 10px #b366ff;
}
nav a{
  margin:0 15px;color:#fff;text-decoration:none;
  font-weight:600;transition:.3s;
}
nav a:hover{color:#b366ff;text-shadow:0 0 10px #b366ff;}

/* ===== Hero ===== */
.hero{
  height:100vh;display:flex;flex-direction:column;
  justify-content:center;align-items:center;text-align:center;
}
.hero h1{
  font-size:4rem;color:#b366ff;text-shadow:0 0 25px #b366ff;
}
.hero p{
  font-size:1.2rem;margin-top:10px;color:#eee;
}
.hero button{
  margin-top:25px;padding:12px 40px;border:none;
  border-radius:8px;background:linear-gradient(135deg,#b366ff,#6e00ff);
  color:#fff;font-weight:700;cursor:pointer;font-size:1.1rem;
  box-shadow:0 0 15px #b366ff;transition:.3s;
}
.hero button:hover{transform:scale(1.05);}

/* ===== Modal ===== */
.modal{
  display:none;position:fixed;inset:0;background:rgba(0,0,0,0.7);
  justify-content:center;align-items:center;backdrop-filter:blur(6px);z-index:200;
}
.modal.active{display:flex;}
.form-box{
  width:380px;padding:30px;border-radius:12px;
  background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.2);
  box-shadow:0 0 30px #6e00ff;
}
.form-box h2{text-align:center;margin-bottom:15px;color:#b366ff;}
.form-box input{
  width:100%;padding:10px;margin-bottom:15px;
  background:rgba(255,255,255,0.1);border:none;border-radius:6px;
  color:#fff;
}
.form-box button{
  width:100%;padding:10px;background:linear-gradient(135deg,#b366ff,#6e00ff);
  border:none;border-radius:6px;color:#fff;font-weight:700;cursor:pointer;
}
.form-box .switch{text-align:center;margin-top:10px;font-size:.9rem;}
.form-box .switch a{color:#b366ff;text-decoration:none;}
.form-box .switch a:hover{text-decoration:underline;}

/* ===== Dashboard ===== */
.dashboard{display:none;text-align:center;padding:120px 20px;}
.dashboard.active{display:block;}
.dashboard h2{color:#b366ff;text-shadow:0 0 15px #b366ff;}
.section{
  background:rgba(255,255,255,0.05);
  padding:20px;margin:25px auto;max-width:700px;
  border-radius:10px;text-align:left;
  box-shadow:0 0 15px rgba(179,102,255,0.3);
}

/* ===== Tournament List ===== */
.tournament-list li{
  list-style:none;margin:8px 0;padding:8px;
  background:rgba(255,255,255,0.05);border-radius:8px;
}

/* ===== Contact & About ===== */
#about,#contact{display:none;padding:120px 20px;max-width:700px;margin:auto;}
#about.active,#contact.active{display:block;}
.link-list a{
  display:flex;align-items:center;gap:10px;
  margin:10px 0;text-decoration:none;color:#b366ff;
}
.link-list a:hover{text-decoration:underline;}

/* ===== Footer ===== */
footer{text-align:center;padding:20px;color:#aaa;}

/* ===== Glow Animation ===== */
@keyframes pulse{
  0%{text-shadow:0 0 5px #b366ff;}
  50%{text-shadow:0 0 25px #b366ff;}
  100%{text-shadow:0 0 5px #b366ff;}
}
.logo, .hero h1{animation:pulse 3s infinite;}
</style>
</head>
<body>

<header>
  <div class="logo">YourGoatViper</div>
  <nav>
    <a href="#" id="nav-home">Home</a>
    <a href="#" id="nav-about">About</a>
    <a href="#" id="nav-contact">Contact</a>
    <a href="#" id="nav-login">Login</a>
  </nav>
</header>

<section class="hero" id="home">
  <h1>Welcome to YourGoatViper</h1>
  <p>Official Website of the PUBG Creator, Editor & Tournament Organizer</p>
  <button id="openLogin">Enter Arena</button>
</section>

<!-- LOGIN / REGISTER -->
<div class="modal" id="authModal">
  <div class="form-box" id="registerForm">
    <h2>Create Account</h2>
    <input type="text" id="regUsername" placeholder="Username">
    <input type="email" id="regEmail" placeholder="Email">
    <input type="password" id="regPasscode" placeholder="Enter Passcode">
    <button id="createBtn">Register</button>
    <div class="switch">Already have an account? <a href="#" id="showLogin">Login</a></div>
    <div class="switch"><a href="#" id="buyPass">Buy Passcode 🔥</a></div>
  </div>

  <div class="form-box" id="loginForm" style="display:none;">
    <h2>Login</h2>
    <input type="email" id="loginEmail" placeholder="Email">
    <input type="text" id="loginUsername" placeholder="Username">
    <input type="password" id="loginPasscode" placeholder="Enter Passcode">
    <button id="loginBtn">Login</button>
    <div class="switch"><a href="#" id="backRegister">Create New Account</a></div>
  </div>
</div>

<!-- DASHBOARD -->
<section class="dashboard" id="dashboard">
  <h2>Welcome, <span id="userName"></span> 👑</h2>
  <p>Entry Date: 24 Oct – 30 Oct</p>

  <div class="section">
    <h3>🏆 Tournament List</h3>
    <ul class="tournament-list">
      <li><strong>International Tournament:</strong> 4 Nov – 7 Nov</li>
      <li>Entry Fee: 200 PKR</li>
      <li>Prize Pool: 5K + International Entry</li>
    </ul>
  </div>
  <button id="logoutBtn" style="padding:10px 30px;border:none;background:#b366ff;color:#fff;border-radius:6px;font-weight:700;">Logout</button>
</section>

<!-- ABOUT -->
<section id="about">
  <h2>About</h2>
  <p>
  Meet <strong>YourGoatViper</strong>, a force to be reckoned with in the PUBG universe!  
  As a talented content creator, professional TDM player, live streamer, and skilled editor,  
  YourGoatViper brings the heat with every match and edit.  
  With a keen eye for detail and a knack for entertaining gameplay,  
  YourGoatViper has built a loyal following across platforms.  
  Get ready to join the action-packed world of <strong>YourGoatViper</strong>!
  </p>
</section>

<!-- CONTACT -->
<section id="contact">
  <h2>Contact</h2>
  <div class="link-list">
    <a href="https://www.instagram.com/arham_arain333" target="_blank">📸 Instagram</a>
    <a href="https://www.tiktok.com/@yourgoatviper" target="_blank">🎵 TikTok</a>
    <a href="https://www.youtube.com/@YourGoatViper" target="_blank">▶️ YouTube</a>
    <a href="https://www.snapchat.com/add/aarain21553" target="_blank">👻 Snapchat</a>
    <a href="https://wa.me/923348666640" target="_blank">💬 WhatsApp</a>
    <a href="mailto:arhamarain060@gmail.com">📧 Email: arhamarain060@gmail.com</a>
  </div>
</section>

<footer>© 2025 YourGoatViper | All Rights Reserved</footer>

<!-- ===== SOUND & SCRIPT ===== -->
<script>
// ===== SOUNDS =====
// Replace with your own .mp3 or .wav files if needed
const clickSound = new Audio('https://cdn.pixabay.com/download/audio/2022/03/15/audio_5865cf93f5.mp3?filename=click.mp3');
const hoverSound = new Audio('https://cdn.pixabay.com/download/audio/2022/03/15/audio_1f6a63b3f8.mp3?filename=hover.mp3');
const bgMusic = new Audio('https://cdn.pixabay.com/download/audio/2023/02/23/audio_c3f6a62b6b.mp3?filename=cyberpunk-2077-style-intro-music-14099.mp3');
bgMusic.loop = true;
bgMusic.volume = 0.4;

// ===== Elements =====
const modal=document.getElementById('authModal');
const registerForm=document.getElementById('registerForm');
const loginForm=document.getElementById('loginForm');
const dashboard=document.getElementById('dashboard');
const home=document.getElementById('home');
const about=document.getElementById('about');
const contact=document.getElementById('contact');
const userName=document.getElementById('userName');

// ===== Sounds Trigger =====
document.querySelectorAll('button,a').forEach(el=>{
  el.addEventListener('mouseenter',()=>hoverSound.play());
  el.addEventListener('click',()=>clickSound.play());
});

// ===== Open Modal =====
document.getElementById('openLogin').onclick=()=>{modal.classList.add('active');bgMusic.play();}
document.getElementById('nav-login').onclick=()=>modal.classList.add('active');
window.onclick=e=>{if(e.target===modal)modal.classList.remove('active');}

// ===== Switch =====
document.getElementById('showLogin').onclick=()=>{registerForm.style.display="none";loginForm.style.display="block";}
document.getElementById('backRegister').onclick=()=>{loginForm.style.display="none";registerForm.style.display="block";}

// ===== Buy Pass =====
document.getElementById('buyPass').onclick=()=>{
  window.open("https://wa.me/923348666640","_blank");
  window.open("https://www.instagram.com/arham_arain333","_blank");
};

// ===== Create Account =====
document.getElementById('createBtn').onclick=()=>{
  const u=document.getElementById('regUsername').value.trim();
  const e=document.getElementById('regEmail').value.trim();
  const p=document.getElementById('regPasscode').value.trim();
  if(!u||!e||!p)return alert("Fill all fields!");
  if(p!=="YourGoatViper-Tournament-2n7RHJL3X0mHrbpF" && p!=="YoutGoatViper-Tour-pass-2n7RHJL3X0mHrbpF") return alert("Invalid Passcode!");
  localStorage.setItem(e,JSON.stringify({username:u,passcode:p}));
  alert("Account created! You can now login.");
  registerForm.style.display="none";
  loginForm.style.display="block";
};

// ===== Login =====
document.getElementById('loginBtn').onclick=()=>{
  const e=document.getElementById('loginEmail').value.trim();
  const u=document.getElementById('loginUsername').value.trim();
  const p=document.getElementById('loginPasscode').value.trim();
  const data=JSON.parse(localStorage.getItem(e));
  if(data && data.username===u && data.passcode===p){
    modal.classList.remove('active');
    home.style.display="none";
    dashboard.classList.add('active');
    userName.textContent=u;
    bgMusic.play();
  }else alert("Invalid details!");
};

// ===== Logout =====
document.getElementById('logoutBtn').onclick=()=>{
  dashboard.classList.remove('active');
  home.style.display="flex";
};

// ===== Navigation =====
document.getElementById('nav-home').onclick=()=>{
  home.style.display="flex";about.classList.remove('active');contact.classList.remove('active');dashboard.classList.remove('active');
};
document.getElementById('nav-about').onclick=()=>{
  about.classList.add('active');contact.classList.remove('active');home.style.display="none";dashboard.classList.remove('active');
};
document.getElementById('nav-contact').onclick=()=>{
  contact.classList.add('active');about.classList.remove('active');home.style.display="none";dashboard.classList.remove('active');
};
</script>

</body>
</html>
