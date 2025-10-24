<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>YourGoatViper — Official</title>
<style>
/* ======= RESET ======= */
*{margin:0;padding:0;box-sizing:border-box;}
body{
  font-family:"Poppins",sans-serif;
  background:url('IMG_1750.png') no-repeat center center/cover;
  color:#fff;overflow-x:hidden;
}

/* ======= OVERLAY ======= */
body::before{
  content:"";
  position:fixed;inset:0;
  background:rgba(45,0,85,0.65);
  backdrop-filter:blur(10px);
  z-index:-1;
}

/* ======= HEADER ======= */
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

/* ======= HERO ======= */
.hero{
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  height:100vh;
  text-align:center;
  padding-top:60px;
}
.hero h1{
  font-size:4rem;
  color:#b365ff;
  margin-bottom:10px;
}
.hero p{
  font-size:1.2rem;
  color:#eee;
}
.hero button{
  margin-top:20px;
  padding:10px 30px;
  border:none;
  background:linear-gradient(135deg,#b365ff,#6e00ff);
  color:#fff;
  border-radius:6px;
  font-weight:600;
  cursor:pointer;
  transition:.3s;
}
.hero button:hover{transform:scale(1.05);}

/* ======= LOGIN / SIGNUP MODAL ======= */
.modal{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,0.7);
  backdrop-filter:blur(6px);
  justify-content:center;
  align-items:center;
  z-index:100;
}
.modal.active{display:flex;}
.form-box{
  width:380px;
  background:rgba(255,255,255,0.07);
  border:1px solid rgba(255,255,255,0.2);
  border-radius:12px;
  padding:30px;
  box-shadow:0 0 30px rgba(0,0,0,0.6);
}
.form-box h2{
  color:#fff;
  text-align:center;
  margin-bottom:20px;
}
.form-box input{
  width:100%;
  padding:10px;
  margin-bottom:15px;
  border:none;
  border-radius:6px;
  background:rgba(255,255,255,0.1);
  color:#fff;
}
.form-box input::placeholder{color:#ccc;}
.form-box button{
  width:100%;
  padding:10px;
  background:linear-gradient(135deg,#b365ff,#6e00ff);
  border:none;
  border-radius:6px;
  font-weight:600;
  color:#fff;
  cursor:pointer;
}
.form-box .switch{
  text-align:center;
  margin-top:15px;
  font-size:0.9rem;
}
.form-box .switch a{color:#b365ff;text-decoration:none;}
.form-box .switch a:hover{text-decoration:underline;}

/* ======= DASHBOARD ======= */
.dashboard{
  display:none;
  text-align:center;
  padding:120px 20px;
}
.dashboard.active{display:block;}
.dashboard h2{color:#b365ff;margin-bottom:10px;}
.dashboard p{color:#eee;margin-bottom:30px;}
.section{
  background:rgba(255,255,255,0.05);
  padding:20px;
  margin:20px auto;
  max-width:700px;
  border-radius:10px;
  text-align:left;
}

/* ======= TOURNAMENT LIST ======= */
.tournament-list li{
  margin:8px 0;
  background:rgba(255,255,255,0.05);
  padding:10px;
  border-radius:8px;
  list-style:none;
}

/* ======= FOOTER ======= */
footer{
  text-align:center;
  padding:20px;
  color:#aaa;
}

/* ======= CONTACT / ABOUT SECTIONS ======= */
#contact, #about{
  display:none;
  padding:120px 20px;
  max-width:700px;
  margin:auto;
}
#contact.active, #about.active{display:block;}
.link-list a{
  display:block;
  margin:6px 0;
  color:#b365ff;
  text-decoration:none;
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
  <p>Official Website of the PUBG Creator, Editor & Tournament Organizer</p>
  <button id="openLogin">Login / Register</button>
</section>

<!-- LOGIN / REGISTER MODAL -->
<div class="modal" id="authModal">
  <div class="form-box" id="loginForm">
    <h2>Login</h2>
    <input type="email" id="loginEmail" placeholder="Email" />
    <input type="password" id="loginPassword" placeholder="Password" />
    <button id="loginBtn">Login</button>
    <div class="switch">Don't have an account? <a href="#" id="showSignup">Create one</a></div>
    <div class="switch"><a href="#" id="forgotPass">Forgot password?</a></div>
  </div>

  <div class="form-box" id="signupForm" style="display:none;">
    <h2>Create Account</h2>
    <input type="text" id="signupUsername" placeholder="Username" />
    <input type="email" id="signupEmail" placeholder="Email" />
    <input type="password" id="signupPassword" placeholder="Password" />
    <input type="date" id="signupDOB" />
    <button id="createBtn">Create Account</button>
    <div class="switch">Already have an account? <a href="#" id="showLogin">Login</a></div>
  </div>
</div>

<!-- DASHBOARD -->
<section class="dashboard" id="dashboard">
  <h2>Welcome, <span id="userName"></span> 👋</h2>
  <p>Entry Date: 24 Oct – 30 Oct</p>

  <div class="section">
    <h3>🏆 Tournament List</h3>
    <ul class="tournament-list">
      <li><strong>International Tournament:</strong> 4 Nov – 7 Nov</li>
      <li>Entry Fee: 200 PKR</li>
      <li>Prize Pool: 5K + International Entry</li>
    </ul>
  </div>

  <div class="section">
    <h3>⚙️ Settings</h3>
    <p>Change your password below:</p>
    <input type="email" id="changeEmail" placeholder="Your Email" />
    <input type="password" id="oldPassword" placeholder="Current Password" />
    <input type="password" id="newPassword" placeholder="New Password" />
    <button id="changeBtn">Change Password</button>
  </div>

  <button id="logoutBtn" style="margin-top:20px;">Logout</button>
</section>

<!-- ABOUT -->
<section id="about">
  <h2>About</h2>
  <p>Meet <strong>YourGoatViper</strong>, a force to be reckoned with in the PUBG universe!  
  As a talented content creator, professional TDM player, live streamer, and skilled editor, he brings the heat with every match and edit.  
  Join the action-packed world of <strong>YourGoatViper</strong>!</p>
</section>

<!-- CONTACT -->
<section id="contact">
  <h2>Contact</h2>
  <div class="link-list">
    <a href="https://www.instagram.com/arham_arain333" target="_blank">Instagram</a>
    <a href="https://www.tiktok.com/@yourgoatviper" target="_blank">TikTok</a>
    <a href="https://www.youtube.com/@YourGoatViper" target="_blank">YouTube</a>
    <a href="https://www.snapchat.com/add/aarain21553" target="_blank">Snapchat</a>
    <a href="https://wa.me/923348666640" target="_blank">WhatsApp</a>
    <a href="mailto:arhamarain060@gmail.com">Email: arhamarain060@gmail.com</a>
  </div>
</section>

<footer>© 2025 YourGoatViper | All Rights Reserved</footer>

<script>
/* Elements */
const modal=document.getElementById('authModal');
const openLogin=document.getElementById('openLogin');
const showSignup=document.getElementById('showSignup');
const showLogin=document.getElementById('showLogin');
const loginForm=document.getElementById('loginForm');
const signupForm=document.getElementById('signupForm');
const forgotPass=document.getElementById('forgotPass');
const dashboard=document.getElementById('dashboard');
const home=document.getElementById('home');
const about=document.getElementById('about');
const contact=document.getElementById('contact');
const navHome=document.getElementById('nav-home');
const navAbout=document.getElementById('nav-about');
const navContact=document.getElementById('nav-contact');
const navLogin=document.getElementById('nav-login');

/* Open/Close Modal */
openLogin.onclick=()=>modal.classList.add('active');
navLogin.onclick=()=>modal.classList.add('active');
window.onclick=e=>{if(e.target===modal)modal.classList.remove('active');}

/* Switch Forms */
showSignup.onclick=()=>{loginForm.style.display="none";signupForm.style.display="block";}
showLogin.onclick=()=>{signupForm.style.display="none";loginForm.style.display="block";}

/* Signup */
document.getElementById('createBtn').onclick=()=>{
  const username=document.getElementById('signupUsername').value;
  const email=document.getElementById('signupEmail').value;
  const password=document.getElementById('signupPassword').value;
  const dob=document.getElementById('signupDOB').value;
  if(!email||!password||!username||!dob)return alert("Fill all fields!");
  localStorage.setItem(email,JSON.stringify({username,password,dob}));
  alert("Account created! You can now login.");
  signupForm.style.display="none";
  loginForm.style.display="block";
};

/* Login */
document.getElementById('loginBtn').onclick=()=>{
  const email=document.getElementById('loginEmail').value;
  const password=document.getElementById('loginPassword').value;
  const user=JSON.parse(localStorage.getItem(email));
  if(user&&user.password===password){
    modal.classList.remove('active');
    home.style.display="none";
    dashboard.classList.add('active');
    document.getElementById('userName').textContent=user.username;
  } else alert("Invalid email or password!");
};

/* Logout */
document.getElementById('logoutBtn').onclick=()=>{
  dashboard.classList.remove('active');
  home.style.display="flex";
};

/* Change Password */
document.getElementById('changeBtn').onclick=()=>{
  const email=document.getElementById('changeEmail').value;
  const oldPass=document.getElementById('oldPassword').value;
  const newPass=document.getElementById('newPassword').value;
  const user=JSON.parse(localStorage.getItem(email));
  if(user&&user.password===oldPass){
    user.password=newPass;
    localStorage.setItem(email,JSON.stringify(user));
    alert("Password changed successfully!");
  } else alert("Incorrect credentials!");
};

/* Forgot Password */
forgotPass.onclick=()=>{
  alert("Forgot password? Contact me on WhatsApp: +92 334 8666640");
  window.open("https://wa.me/923348666640","_blank");
};

/* Navigation */
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
