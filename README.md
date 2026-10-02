<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sami & Nehir Rüya | Bizim Hikayemiz</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { 
            background: linear-gradient(135deg, #0f0505, #1f0a0a, #0b0202); 
            color: #f1f1f1; display: flex; justify-content: center; align-items: center; 
            min-height: 100vh; overflow-x: hidden; 
        }
        
        /* Şifre Ekranı */
        #lock-screen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(10, 3, 3, 0.96); display: flex; flex-direction: column;
            justify-content: center; align-items: center; z-index: 1000;
            transition: opacity 0.8s ease;
        }
        .lock-box {
            background: #180808; padding: 40px 30px; border-radius: 24px;
            box-shadow: 0 20px 40px rgba(229, 9, 20, 0.3); text-align: center; width: 90%; max-width: 380px;
            border: 1px solid #5a1515;
            animation: pulseGlow 3s ease-in-out infinite;
        }
        @keyframes pulseGlow {
            0%, 100% { box-shadow: 0 20px 40px rgba(229, 9, 20, 0.3); }
            50% { box-shadow: 0 20px 50px rgba(229, 9, 20, 0.6); }
        }
        .lock-box h2 { margin-bottom: 10px; color: #fff; font-size: 26px; }
        .lock-box p { color: #ccaaaa; font-size: 14px; margin-bottom: 25px; }
        .lock-box input {
            width: 100%; padding: 15px; margin-bottom: 20px; border-radius: 12px;
            border: 1px solid #7a2222; background: #240c0c; color: #fff; font-size: 20px; text-align: center;
            letter-spacing: 5px; outline: none;
        }
        .lock-box input:focus { border-color: #ff4d4d; }
        .lock-box button {
            width: 100%; padding: 15px; border: none; border-radius: 12px;
            background: linear-gradient(45deg, #e50914, #ff3366); color: white; font-size: 16px; cursor: pointer; font-weight: bold;
            transition: transform 0.2s, box-shadow 0.2s;
            box-shadow: 0 5px 20px rgba(229, 9, 20, 0.4);
        }
        .lock-box button:hover { transform: scale(1.02); }
        #error-msg { color: #ff6b6b; margin-top: 15px; font-size: 14px; display: none; font-weight: 500; }

        /* Ana Site İçeriği */
        #main-content {
            display: none; width: 100%; max-width: 750px; padding: 30px;
            text-align: center; animation: fadeIn 1.5s ease forwards;
        }
        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(20px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        .heart-icon { font-size: 40px; color: #e50914; margin-bottom: 10px; animation: heartbeat 1.5s infinite; }
        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.15); }
        }

        h1 { font-size: 36px; margin-bottom: 5px; color: #fff; letter-spacing: 2px; }
        .sub-title { color: #ff6b6b; font-size: 18px; margin-bottom: 35px; font-weight: 600; letter-spacing: 1px; }
        
        .photo-grid {
            display: flex; flex-direction: column; gap: 30px; align-items: center; margin-bottom: 35px;
        }
        .photo-card {
            background: #180808; padding: 12px; border-radius: 20px;
            box-shadow: 0 15px 35px rgba(229, 9, 20, 0.25); border: 1px solid #5a1515;
            max-width: 420px; width: 100%; transition: transform 0.4s ease;
        }
        .photo-card:hover { transform: translateY(-8px); }
        .photo-card img {
            width: 100%; height: auto; border-radius: 14px; display: block; object-fit: cover;
        }
        .note {
            font-size: 18px; color: #ddd; line-height: 1.8; background: linear-gradient(145deg, #180808, #240c0c);
            padding: 35px; border-radius: 20px; border-left: 6px solid #e50914;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5); border-top: 1px solid #4a1515;
        }
    </style>
</head>
<body>

    <!-- ŞİFRE EKRANI -->
    <div id="lock-screen">
        <div class="lock-box">
            <div style="font-size: 30px; margin-bottom: 10px;">🌹</div>
            <h2>Sami & Nehir Rüya</h2>
            <p>Kalbe giden şifreyi gir:</p>
            <input type="password" id="password-input" placeholder="••••" maxlength="4">
            <button onclick="checkPassword()">Kilidi Aç</button>
            <div id="error-msg">Şifre yanlış sevgilim, tekrar dene! ❤</div>
        </div>
    </div>

    <!-- ANA SİTE -->
    <div id="main-content">
        <div class="heart-icon">❤</div>
        <h1>Sami & Nehir Rüya</h1>
        <div class="sub-title">✨ Sonsuza Kadar Birlikte ✨</div>
        
        <div class="photo-grid">
            <div class="photo-card">
                <img src="https://images.weserv.nl/?url=raw.githubusercontent.com/kamacisami163-cloud/bizim-hikayemiz/main/2344.jpg" alt="Sami ve Nehir Rüya"> 
            </div>
            <div class="photo-card">
                <img src="https://images.weserv.nl/?url=raw.githubusercontent.com/kamacisami163-cloud/bizim-hikayemiz/main/2012.jpg" alt="Sami ve Nehir Rüya">
            </div>
        </div>

        <div class="note">
            "Gözlerinin baktığı her yer huzur, adının geçtiği her an ömrümün en güzel hikayesi. İyi ki varsın Nehir Rüya..."
        </div>
    </div>

    <script>
        const DOGRU_SIFRE = "1518"; 

        function checkPassword() {
            const girilenSifre = document.getElementById("password-input").value;
            const lockScreen = document.getElementById("lock-screen");
            const mainContent = document.getElementById("main-content");
            const errorMsg = document.getElementById("error-msg");

            if (girilenSifre === DOGRU_SIFRE) {
                lockScreen.style.opacity = '0';
                setTimeout(() => {
                    lockScreen.style.display = 'none';
                    mainContent.style.display = 'block';
                }, 600);
            } else {
                errorMsg.style.display = 'block';
                document.getElementById("password-input").value = "";
            }
        }
        
        document.getElementById("password-input").addEventListener("keypress", function(event) {
            if (event.key === "Enter") {
                checkPassword();
            }
        });
    </script>
</body>
</html>
