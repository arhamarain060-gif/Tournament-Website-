<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>YourGoatViper — Official</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;}
body{
  font-family:"Poppins",sans-serif;
  background:url('IMG_1750.png') no-repeat center center/cover;
  color:#fff;overflow-x:hidden;
}
body::before{
  content:"";
  position:fixed;inset:0;
  background:rgba(45,0,85,0.65);
  backdrop-filter:blur(10px);
  z-index:-1;
}
header{
  width:100%;
  padding:20px 60px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:rgba(0,0,0,0.4);
  backdrop-filter:blur(10px);
  position:fixed;
  top:0;left:0;z-index:10;
}
.logo{font-size:1.5rem;font-weight:700;color:#b365ff;}
nav a{
  margin:0 15px;
  text-decoration:none;
  color:#fff;
  font-weight:500;
  transition:.3s;
}
nav a:hover{color:#b365ff;}
.hero{
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  height:100vh;
  text-align:center;
  padding-top:60px;
}
.hero h1{font-size:4rem;color:#b365ff;margin-bottom:10px;}
.hero p{font-size:1.2rem;color:#eee;}
.hero button{
  margin-top:20px;padding:10px 30px;border:none;
  background:linear-gradient(135deg,#b365ff,#6e00ff);
  color:#fff;border-radius:6px;font-weight:600;cursor:pointer;transition:.3s;
}
.hero button:hover{transform:scale(1.05);}
.modal{
  display:none;position:fixed;inset:0;background:rgba(0,0,0,0.7);
  backdrop-filter:blur(6px);justify-content:center;align-items:center;z-index:100;
}
.modal.active{display:flex;}
.form-box{
  width:380px;background:rgba(255,255,255,0.07);
  border:1px solid rgba(255,255,255,0.2);border-radius:12px;padding:30px;
  box-shadow:0 0 30px rgba(0,0,0,0.6);text-align:center;
}
.form-box h2{color:#fff;margin-bottom:20px;}
.form-box input{
  width:100%;padding:10px;margin-bottom:15px;border:none;border-radius:6px;
  background:rgba(255,255,255,0.1);color:#fff;
}
.form-box input::placeholder{color:#ccc;}
.form-box button{
  width:100%;padding:10px;background:linear-gradient(135deg,#b365ff,#6e00ff);
  border:none;border-radius:6px;font-weight:600;color:#fff;cursor:pointer;
}
.form-box .switch{margin-top:15px;font-size:0.9rem;color:#b365ff;cursor:pointer;}
.whatsapp-links{
  display:none;margin-top:15px;
}
.whatsapp-links a{
  margin:0 10px;display:inline-block;
}
.whatsapp-links img{
  width:40px;height:40px;border-radius:50%;transition:transform .3s;
}
.whatsapp-links img:hover{transform:scale(1.1);}
.dashboard{
  display:none;text-align:center;padding:120px 20px;
}
.dashboard.active{display:block;}
.dashboard h2{color:#b365ff;margin-bottom:10px;}
.section{
  background:rgba(255,255,255,0.05);padding:20px;margin:20px auto;
  max-width:700px;border-radius:10px;text-align:left;
}
.tournament-list li{
  margin:8px 0;background:rgba(255,255,255,0.05);
  padding:10px;border-radius:8px;list-style:none;
}
footer{text-align:center;padding:20px;color:#aaa;}
#about,#contact{display:none;padding:120px 20px;max-width:700px;margin:auto;}
#about.active,#contact.active{display:block;}
.link-list a{
  display:block;margin:6px 0;color:#b365ff;text-decoration:none;
}
.link-list a:hover{text-decoration:underline;}
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
  <p>Official Tournament & Gaming Hub</p>
  <button id="openLogin">Enter Tournament</button>
</section>

<div class="modal" id="authModal">
  <div class="form-box" id="loginForm">
    <h2>Enter Tournament Passcode</h2>
    <input type="text" id="passcode" placeholder="Enter Passcode" />
    <button id="loginBtn">Submit</button>
    <div class="switch" id="buyPass">Buy Passcode 🔑</div>

    <div class="whatsapp-links" id="socialLinks">
      <a href="https://wa.me/923348666640" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp">
      </a>
      <a href="https://www.instagram.com/arham_arain333?igsh=NGhobDk1c29rd3oy&utm_source=qr" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png" alt="Instagram">
      </a>
    </div>
  </div>
</div>

<section class="dashboard" id="dashboard">
  <h2>Welcome, Warrior 👑</h2>
  <p>Entry Date: 24 Oct – 30 Oct</p>
  <div class="section">
    <h3>🏆 Tournament Details</h3>
    <ul class="tournament-list">
      <li><strong>International Tournament:</strong> 4 Nov – 7 Nov</li>
      <li>Entry Fee: 200 PKR</li>
      <li>Prize Pool: 5K + International Entry</li>
    </ul>
  </div>
  <button id="logoutBtn" style="margin-top:20px;">Logout</button>
</section>

<section id="about">
  <h2>About</h2>
  <p><strong>YourGoatViper</strong> — PUBG Creator, Pro TDM Player, Streamer & Editor.  
     Join the action-packed tournaments and experience the best of mobile esports.</p>
</section>

<section id="contact">
  <h2>Contact</h2>
  <div class="link-list">
    <a href="https://www.instagram.com/arham_arain333?igsh=NGhobDk1c29rd3oy&utm_source=qr" target="_blank">Instagram</a>
    <a href="https://wa.me/923348666640" target="_blank">WhatsApp</a>
  </div>
</section>

<footer>© 2025 YourGoatViper | All Rights Reserved</footer>

<script>
const modal=document.getElementById('authModal');
const openLogin=document.getElementById('openLogin');
const navLogin=document.getElementById('nav-login');
const loginBtn=document.getElementById('loginBtn');
const dashboard=document.getElementById('dashboard');
const home=document.getElementById('home');
const buyPass=document.getElementById('buyPass');
const socialLinks=document.getElementById('socialLinks');
const navHome=document.getElementById('nav-home');
const navAbout=document.getElementById('nav-about');
const navContact=document.getElementById('nav-contact');
const about=document.getElementById('about');
const contact=document.getElementById('contact');

const validPasscodes=[
  "YourGoatViper-Tournament-2n7RHJL3X0mHrbpF",
  "YourGoatViper-Tour-pass-2n7RHJL3X0mHrbpF"
];

openLogin.onclick=()=>modal.classList.add('active');
navLogin.onclick=()=>modal.classList.add('active');
window.onclick=e=>{if(e.target===modal)modal.classList.remove('active');}

buyPass.onclick=()=>{
  socialLinks.style.display = socialLinks.style.display === "block" ? "none" : "block";
};

loginBtn.onclick=()=>{
  const pass=document.getElementById('passcode').value.trim();
  if(validPasscodes.includes(pass)){
    modal.classList.remove('active');
    home.style.display="none";
    dashboard.classList.add('active');
  } else alert("Invalid Passcode! ❌");
};

document.getElementById('logoutBtn').onclick=()=>{
  dashboard.classList.remove('active');
  home.style.display="flex";
};

navHome.onclick=()=>{
  home.style.display="flex";
  about.classList.remove('active');
  contact.classList.remove('active');
  dashboard.classList.remove('active');
};
navAbout.onclick=()=>{
  about.classList.add('active');
  contact.classList.remove('active');
  home.style.display="none";
  dashboard.classList.remove('active');
};
navContact.onclick=()=>{
  contact.classList.add('active');
  about.classList.remove('active');
  home.style.display="none";
  dashboard.classList.remove('active');
};
</script>
</body>
</html>
