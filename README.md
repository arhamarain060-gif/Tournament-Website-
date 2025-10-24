<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YourGoatViper — Official</title>
<style>
/* Reset & Base */
* { margin: 0; padding: 0; box-sizing: border-box; }
body {
  font-family: "Poppins", sans-serif;
  background: url('IMG_1703.jpeg') no-repeat center center/cover;
  color: #fff;
  overflow-x: hidden;
  animation: fadeIn 1s ease-in;
}
@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
body::before {
  content: "";
  position: fixed; inset: 0;
  background: rgba(0,0,0,0.7);
  backdrop-filter: blur(8px);
  z-index: -1;
}
body::after {
  content: "";
  position: fixed; inset: 0;
  background: radial-gradient(circle, rgba(179,101,255,0.1) 1px, transparent 1px);
  background-size: 20px 20px;
  animation: float 10s infinite linear;
  z-index: -2;
}
@keyframes float { 0% { transform: translateY(0); } 100% { transform: translateY(-20px); } }

/* Header */
header {
  width: 100%;
  padding: 20px 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(0,0,0,0.4);
  position: fixed;
  top: 0; left: 0; z-index: 10;
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255,255,255,0.1);
  animation: slideDown 0.5s ease-out;
}
@keyframes slideDown { from { transform: translateY(-100%); } to { transform: translateY(0); } }
.logo { font-size: 1.7rem; font-weight: 700; color: #b365ff; text-shadow: 0 0 10px #b365ff; }
nav a {
  margin: 0 15px;
  text-decoration: none;
  color: #fff;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
}
nav a:hover { color: #b365ff; transform: scale(1.05); }
nav a::after {
  content: "";
  position: absolute; bottom: -5px; left: 0; width: 0; height: 2px;
  background: #b365ff; transition: width 0.3s;
}
nav a:hover::after { width: 100%; }

/* Hero */
.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  text-align: center;
  padding: 120px 20px 20px;
  background: rgba(255,255,255,0.05);
  border-radius: 15px;
  margin: 20px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.5);
  animation: bounceIn 1s ease-out;
}
@keyframes bounceIn { 0% { transform: scale(0.8); opacity: 0; } 100% { transform: scale(1); opacity: 1; } }
.hero h1 { font-size: 4rem; color: #b365ff; margin-bottom: 10px; text-shadow: 0 0 20px #b365ff; }
.hero p { font-size: 1.3rem; color: #ddd; max-width: 600px; line-height: 1.6; }
.hero .about-text {
  margin-top: 20px;
  font-size: 1.1rem;
  color: #ccc;
  max-width: 700px;
  line-height: 1.5;
  animation: fadeInUp 1s ease-out 0.5s both;
}
@keyframes fadeInUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
.hero button {
  margin-top: 25px;
  padding: 12px 35px;
  border: none;
  background: linear-gradient(135deg, #b365ff, #6e00ff);
  color: #fff;
  border-radius: 25px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 5px 15px rgba(179,101,255,0.3);
}
.hero button:hover { transform: scale(1.05); box-shadow: 0 10px 25px rgba(179,101,255,0.5); }

/* Modal */
.modal {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.75);
  backdrop-filter: blur(6px);
  justify-content: center;
  align-items: center;
  z-index: 100;
  animation: zoomIn 0.3s ease-out;
}
@keyframes zoomIn { from { transform: scale(0.9); opacity: 0; } to { transform: scale(1); opacity: 1; } }
.modal.active { display: flex; }
.form-box {
  width: 400px;
  background: rgba(255,255,255,0.1);
  border: 1px solid rgba(255,255,255,0.2);
  border-radius: 15px;
  padding: 30px;
  box-shadow: 0 15px 35px rgba(0,0,0,0.6);
  backdrop-filter: blur(10px);
  animation: slideUp 0.4s ease-out;
}
@keyframes slideUp { from { transform: translateY(50px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
.form-box h2 { color: #fff; text-align: center; margin-bottom: 20px; font-size: 1.8rem; }
.form-box input {
  width: 100%;
  padding: 12px;
  margin-bottom: 15px;
  border: none;
  border-radius: 8px;
  background: rgba(255,255,255,0.1);
  color: #fff;
  font-size: 1rem;
  transition: all 0.3s;
}
.form-box input:focus { outline: none; background: rgba(255,255,255,0.2); box-shadow: 0 0 10px #b365ff; }
.form-box button {
  width: 100%;
  padding: 12px;
  background: linear-gradient(135deg, #b365ff, #6e00ff);
  border: none;
  border-radius: 8px;
  font-weight: 600;
  color: #fff;
  cursor: pointer;
  transition: all 0.3s;
  box-shadow: 0 5px 15px rgba(179,101,255,0.3);
}
.form-box button:hover { transform: translateY(-2px); box-shadow: 0 10px 25px rgba(179,101,255,0.5); }
.form-box .switch { text-align: center; margin-top: 15px; font-size: 0.9rem; }
.form-box .switch a { color: #b365ff; text-decoration: none; transition: color 0.3s; }
.form-box .switch a:hover { color: #fff; }

/* Dashboard */
.dashboard {
  display: none;
  text-align: center;
  padding: 120px 20px;
  animation: fadeIn 0.5s ease-in;
}
.dashboard.active { display: block; }
.dashboard h2 { color: #b365ff; margin-bottom: 10px; text-shadow: 0 0 10px #b365ff; }
.dashboard p { color: #eee; margin-bottom: 30px; }
.section {
  background: rgba(255,255,255,0.05);
  padding: 25px;
  margin: 20px auto;
  max-width: 750px;
  border-radius: 15px;
  text-align: left;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
  animation: fadeInUp 0.6s ease-out;
}
.tournament-dates h3 { color: #b365ff; margin-bottom: 15px; font-size: 1.5rem; }
.tournament-dates ul { list-style: none; padding: 0; }
.tournament-dates li {
  margin: 10px 0;
  background: rgba(255,255,255,0.05);
  padding: 12px;
  border-radius: 8px;
  border-left: 4px solid #b365ff;
  transition: transform 0.3s;
}
.tournament-dates li:hover { transform: translateX(5px); }

/* Sections */
#contact, #about {
  display: none;
  padding: 120px 20px;
  max-width: 750px;
  margin: auto;
  background: rgba(255,255,255,0.05);
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
  animation: fadeIn 0.5s ease-in;
}
#contact.active, #about.active { display: block; }
.link-list a {
  display: block;
  margin: 8px 0;
  color: #b365ff;
  text-decoration: none;
  padding: 8px;
  border-radius: 5px;
  transition: all 0.3s;
}
.link-list a:hover { background: rgba(179,101,255,0.1); transform: scale(1.02); }

/* Footer */
footer { text-align: center; padding: 20px; color: #aaa; background: rgba(0,0,0,0.2); }

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
  <p>Official Website of the PUBG Creator & Tournament Organizer</p>
  <div class="about-text">
    Meet <strong>YourGoatViper</strong>, a force to be reckoned with in the PUBG universe!  
    As a talented content creator, professional TDM player, live streamer, and skilled editor,  
    YourGoatViper brings the heat with every match and edit.  
    Join the action-packed world of <strong>YourGoatViper</strong>!
  </div>
  <button id="openLogin">Login / Register</button>
</section>

<!-- Modal -->
<div class="modal" id="authModal">
  <div class="form-box" id="signupForm">
    <h2>Create Account</h2>
    <input type="text" id="username" placeholder="Username">
    <input type="email" id="email" placeholder="Email">
    <input type="text" id="passcode" placeholder="Enter Passcode">
    <button id="createAccount">Create Account</button>
    <div class="switch">
      Already have an account? <a href="#" id="alreadyAccount">Login</a>
    </div>
  </div>

  <div class="form-box" id="loginForm" style="display:none;">
    <h2>Login</h2>
    <input type="email" id="loginEmail" placeholder="Email">
    <input type="text" id="loginPasscode" placeholder="Enter Passcode">
    <button id="loginBtn">Login</button>
    <div class="switch">
      <a href="#" id="backSignup">Create New Account</a>
    </div>
  </div>
</div>

<section class="dashboard" id="dashboard">
  <h2>Welcome, <span id="userName"></span> 👋</h2>
  <p>Entry Date: 24 Oct – 30 Oct</p>
  <div class="section tournament-dates">
    <h3>🏆 Tournament Dates</h3>
    <ul>
      <li><strong>International Tournament:</strong> 4 Nov – 7 Nov</li>
      <li>Entry Fee: 200 PKR</li>
      <li>Prize Pool: 5K + International Entry</li>
    </ul>
  </div>
  <button id="logoutBtn" style="margin-top:20px; padding:10px 20px; border-radius:8px;">Logout</button>
</section>

<section id="about">
  <h2>About</h2>
  <p>Meet <strong>YourGoatViper</strong>, a force to be reckoned with in the PUBG universe!  
  As a talented content creator, professional TDM player, live streamer, and skilled editor,  
  YourGoatViper brings the heat with every match and edit.  
  Join the action-packed world of <strong>YourGoatViper</strong>!</p>
</section>

<section id="contact">
  <h2>Contact</h2>
  <div class="link-list">
    <a href="https://www.instagram.com/arham_arain333" target="_blank">Instagram</a>
    <a href="https://www.tiktok.com/@yourgoatviper" target="_blank">TikTok</a>
    <a href="https://www.youtube.com/@YourGoatViper" target="_blank">YouTube</a>
    <a href="https://www.snapchat.com/add/aarain21553" target="_blank">Snapchat</a>
    <a href="https://wa.me/923348666640" target="_blank">WhatsApp</a>
    <a href="mailto:arhamarain060@gmail.com">Email</a>
  </div>
</section>

<footer>© 2025 YourGoatViper | All Rights Reserved</footer>

<script>
// Click sound
const clickSound = new Audio("https://www.soundjay.com/button/sounds/button-16.mp3");

// 32 passcodes
const validPasscodes = [
  "YourGoatViper-TourneyPro-4j8KLm9Np2","YourGoatViper-GamingFrenzy-7h3GHj5Kl8",
  "YourGoatViper-ChampMode-9p4MNl2kJh6","YourGoatViper-VictoryLap-1q2wS3eD4r",
  "YourGoatViper-EliteWarrior-5t6Yh8Ij3k","YourGoatViper-TournamentTamer-9n8Bh4Lm2p",
  "YourGoatViper-GamerGirl-2c4V6b8Nl1k","YourGoatViper-SniperKing-7g6Jh3Kl4m",
  "YourGoatViper-PlayoffPro-9m8Nl4Kp2j","YourGoatViper-GamingMaster-4h6Gf2sD3p",
  "YourGoatViper-NoobSlayer-1a2b3c4d5","YourGoatViper-TourneyTitan-6p9Lk4Jh3g",
  "YourGoatViper-FPSFanatic-8m5Nl2pKj","YourGoatViper-GamingGuru-3q2w1e4r",
  "YourGoatViper-ChampionshipChaser-9h8j7k6p","YourGoatViper-BattleHardened-2t4g6y8h",
  "YourGoatViper-GamerGod-5m3j9p2k","YourGoatViper-TourneyTactician-1p8L4k2j3",
  "YourGoatViper-SniperSavant-7g4h2j9p","YourGoatViper-EliteSquad-3m5n8b2v",
  "YourGoatViper-GamingGenius-9p6l4j3h","YourGoatViper-TourneyTitan-2c8B4n6m",
  "YourGoatViper-FPSFan-5t7y6h3","YourGoatViper-GamingGrind-9m2p4l8k",
  "YourGoatViper-NoMercy-1q2w3e4r","YourGoatViper-TourneyTerror-6h8j3k2",
  "YourGoatViper-GamingGamer-4g5j9p2m","YourGoatViper-EliteElite-8n9m4l3k",
  "YourGoatViper-SniperSniper-2p4l6j8h","YourGoatViper-GamingGaming-5g7h9j2k",
  "YourGoatViper-Tournament-2n7RHJL3X0mHrbpF","YourGoatViper-UltimateWarrior-3k8Lm2Hj9Q"
];

// Elements
const openLogin = document.getElementById("openLogin");
const authModal = document.getElementById("authModal");
const signupForm = document.getElementById("signupForm");
const loginForm = document.getElementById("loginForm");
const alreadyAccount = document.getElementById("alreadyAccount");
const backSignup = document.getElementById("backSignup");
const createAccountBtn = document.getElementById("createAccount");
const loginBtn = document.getElementById("loginBtn");
const dashboard = document.getElementById("dashboard");
const userNameEl = document.getElementById("userName");
const logoutBtn = document.getElementById("logoutBtn");

// Navigation
const navHome = document.getElementById("nav-home");
const navAbout = document.getElementById("nav-about");
const navContact = document.getElementById("nav-contact");
const navLogin = document.getElementById("nav-login");
const homeSection = document.getElementById("home");
const aboutSection = document.getElementById("about");
const contactSection = document.getElementById("contact");

// Open modal
openLogin.addEventListener("click", ()=>{clickSound.play(); authModal.classList.add("active");});
alreadyAccount.addEventListener("click", ()=>{clickSound.play(); signupForm.style.display="none"; loginForm.style.display="block";});
backSignup.addEventListener("click", ()=>{clickSound.play(); loginForm.style.display="none"; signupForm.style.display="block";});

// Helper
function saveUser(username,email,passcode){localStorage.setItem("user", JSON.stringify({username,email,passcode}));}
function getUser(){return JSON.parse(localStorage.getItem("user"));}

// Create account
createAccountBtn.addEventListener("click", ()=>{
    clickSound.play();
    const username=document.getElementById("username").value;
    const email=document.getElementById("email").value;
    const passcode=document.getElementById("passcode").value;
    if(username && email && validPasscodes.includes(passcode)){
        saveUser(username,email,passcode);
        alert("Account created successfully!");
        authModal.classList.remove("active");
        showDashboard(username);
    }else alert("Invalid passcode or empty fields!");
});

// Login
loginBtn.addEventListener("click", ()=>{
    clickSound.play();
    const email=document.getElementById("loginEmail").value;
    const passcode=document.getElementById("loginPasscode").value;
    const user=getUser();
    if(user && user.email===email && user.passcode===passcode){
        authModal.classList.remove("active");
        showDashboard(user.username);
    }else alert("Invalid credentials!");
});

// Show dashboard
function showDashboard(username){
    dashboard.classList.add("active");
    userNameEl.textContent=username;
    homeSection.style.display="none";
    aboutSection.style.display="none";
    contactSection.style.display="none";
}

// Logout
logoutBtn.addEventListener("click", ()=>{
    clickSound.play();
    dashboard.classList.remove("active");
    homeSection.style.display="block";
});

// Navigation
navHome.addEventListener("click", ()=>{clickSound.play(); homeSection.style.display="block"; aboutSection.style.display="none"; contactSection.style.display="none"; dashboard.classList.remove("active");});
navAbout.addEventListener("click", ()=>{clickSound.play(); homeSection.style.display="none"; aboutSection.style.display="block"; contactSection.style.display="none"; dashboard.classList.remove("active");});
navContact.addEventListener("click", ()=>{clickSound.play(); homeSection.style.display="none"; aboutSection.style.display="none"; contactSection.style.display="block"; dashboard.classList.remove("active");});
navLogin.addEventListener("click", ()=>{clickSound.play(); authModal.classList.add("active");});

</script>

</body>
</html>
