<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>YourGoatViper — Tournament Login</title>
  <style>
    /* ---------- Global ---------- */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Poppins", sans-serif;
    }

    html, body {
      height: 100%;
      background: #000;
      color: #fff;
    }

    /* ---------- Background ---------- */
    .background {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: url("IMG_1703.jpeg") no-repeat center center/cover;
      filter: blur(8px) brightness(0.5);
      z-index: -1;
    }

    /* ---------- Container ---------- */
    .login-container {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 340px;
      padding: 40px;
      background: rgba(255, 255, 255, 0.08);
      border-radius: 16px;
      box-shadow: 0 8px 30px rgba(0, 0, 0, 0.5);
      text-align: center;
      backdrop-filter: blur(10px);
      animation: fadeIn 0.8s ease-in-out;
    }

    .login-container h1 {
      font-size: 28px;
      color: #c88cff;
      font-weight: 700;
    }

    .login-container p {
      font-size: 13px;
      color: #bbb;
      margin-top: 4px;
      margin-bottom: 20px;
    }

    input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: none;
      border-radius: 6px;
      outline: none;
      font-size: 14px;
    }

    button {
      width: 100%;
      padding: 10px;
      border: none;
      border-radius: 6px;
      font-size: 15px;
      cursor: pointer;
      background: linear-gradient(135deg, #a020f0, #6a00b9);
      color: #fff;
      font-weight: 600;
      transition: all 0.3s ease;
    }

    button:hover {
      background: linear-gradient(135deg, #7d00cc, #4b0099);
      transform: translateY(-2px);
    }

    /* ---------- Extra Options ---------- */
    .extra {
      margin-top: 20px;
    }

    #buyPassBtn {
      background: transparent;
      border: 1px solid #b77cff;
      color: #b77cff;
      padding: 8px 12px;
      border-radius: 6px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    #buyPassBtn:hover {
      background: #b77cff;
      color: #fff;
    }

    /* ---------- Contact Icons ---------- */
    #contactIcons {
      margin-top: 12px;
    }

    .icon {
      width: 38px;
      height: 38px;
      margin: 0 8px;
      cursor: pointer;
      filter: drop-shadow(0 0 6px rgba(255,255,255,0.3));
      transition: transform 0.3s ease;
    }

    .icon:hover {
      transform: scale(1.1);
    }

    .hidden {
      display: none;
    }

    /* ---------- Message ---------- */
    #message {
      margin-top: 15px;
      font-size: 14px;
      font-weight: 500;
    }

    /* ---------- Animation ---------- */
    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translate(-50%, -60%);
      }
      to {
        opacity: 1;
        transform: translate(-50%, -50%);
      }
    }

    /* ---------- Responsive ---------- */
    @media (max-width: 480px) {
      .login-container {
        width: 85%;
        padding: 30px;
      }
    }
  </style>
</head>
<body>

  <div class="background"></div>

  <div class="login-container">
    <h1>YourGoatViper</h1>
    <p>Official Tournament Login</p>

    <form id="loginForm">
      <input type="email" id="email" placeholder="Enter your email" required />
      <input type="text" id="passcode" placeholder="Enter your passcode" required />
      <button type="submit">Login</button>
    </form>

    <div class="extra">
      <button id="buyPassBtn">Buy Passcode</button>
      <div id="contactIcons" class="hidden">
        <a href="https://wa.me/923348666640" target="_blank">
          <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" class="icon" alt="WhatsApp" />
        </a>
        <a href="https://www.instagram.com/arham_arain333?igsh=NGhobDk1c29rd3oy&utm_source=qr" target="_blank">
          <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png" class="icon" alt="Instagram" />
        </a>
      </div>
    </div>

    <p id="message"></p>
  </div>

  <script>
    const form = document.getElementById("loginForm");
    const message = document.getElementById("message");
    const buyBtn = document.getElementById("buyPassBtn");
    const contactIcons = document.getElementById("contactIcons");

    // Valid passcodes
    const validPasscodes = [
      "YourGoatViper-Tournament-2n7RHJL3X0mHrbpF",
      "YourGoatViper-Tour-pass-2n7RHJL3X0mHrbpF"
    ];

    // Login check
    form.addEventListener("submit", (e) => {
      e.preventDefault();
      const passcode = document.getElementById("passcode").value.trim();

      if (validPasscodes.includes(passcode)) {
        message.style.color = "#7eff8b";
        message.textContent = "✅ Login Successful! Welcome to the YourGoatViper Tournament!";
      } else {
        message.style.color = "#ff7070";
        message.textContent = "❌ Invalid Passcode. Please buy a valid one.";
      }
    });

    // Show WhatsApp & Insta icons
    buyBtn.addEventListener("click", () => {
      contactIcons.classList.toggle("hidden");
    });
  </script>
</body>
</html>
