<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Bengaluru - Citizen Engagement</title>
    <link rel="stylesheet" href="styles.css">
    <script src="https://accounts.google.com/gsi/client" async defer></script>
    <script src="script.js" defer></script>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background: url('98faeef3-0aed-4a28-a1e3-03a29a226f55.jpeg') no-repeat center center/cover;
            color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }
        
        .login-box {
            width: 400px;
            padding: 40px;
            background: rgba(255, 255, 255, 0);
            border-radius: 12px;
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.3);
            text-align: center;
            position: relative;
            backdrop-filter: blur(10px);
        }
        
        .login-box h2 {
            margin-bottom: 20px;
            color: #0073e6;
            font-size: 24px;
        }

        .login-box input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 16px;
        }

        .login-box button {
            background: linear-gradient(135deg, #6a11cb, #2575fc);
            color: white;
            padding: 14px 22px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.3s;
            font-size: 18px;
            width: 100%;
            margin-top: 10px;
        }

        .login-box button:hover {
            background: linear-gradient(135deg, #5a0ecc, #1a73e8);
        }

        .logo {
            width: 120px;
            margin-bottom: 20px;
            display: block;
            margin-left: auto;
            margin-right: auto;
            opacity: 0;
            animation: fadeIn 2s ease-in forwards;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .toggle-link {
            margin-top: 15px;
            font-size: 14px;
        }

        .toggle-link a {
            color: #0073e6;
            text-decoration: none;
            font-weight: bold;
            cursor: pointer;
        }

        .toggle-link a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="login-box" id="auth-container">
        <img src="cdb0bd1a-85c8-4842-b292-d4bf0b1c0f3f.jpeg" alt="Smart Bengaluru Logo" class="logo">
        <h2 id="auth-title">Login</h2>
        <div id="login-form">
            <input type="text" placeholder="Username" required>
            <input type="password" placeholder="Password" required>
            <button>Login</button>
            <div id="g_id_onload" data-client_id="YOUR_GOOGLE_CLIENT_ID" data-callback="handleCredentialResponse"></div>
            <div class="g_id_signin" data-type="standard"></div>
            <div class="toggle-link">
                Don't have an account? <a onclick="toggleAuthForm()">Sign Up</a>
            </div>
        </div>
        <div id="signup-form" style="display: none;">
            <input type="text" placeholder="Full Name" required>
            <input type="email" placeholder="Email" required>
            <input type="password" placeholder="Password" required>
            <button>Sign Up</button>
            <div class="toggle-link">
                Already have an account? <a onclick="toggleAuthForm()">Login</a>
            </div>
        </div>
    </div>

    <script>
        function handleCredentialResponse(response) {
            alert("Google Sign-In Successful! Token: " + response.credential);
        }

        function toggleAuthForm() {
            let loginForm = document.getElementById("login-form");
            let signupForm = document.getElementById("signup-form");
            let authTitle = document.getElementById("auth-title");
            
            if (loginForm.style.display === "none") {
                loginForm.style.display = "block";
                signupForm.style.display = "none";
                authTitle.innerText = "Login";
            } else {
                loginForm.style.display = "none";
                signupForm.style.display = "block";
                authTitle.innerText = "Sign Up";
            }
        }
    </script>
</body>
</html>
