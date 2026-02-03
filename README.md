<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Princess</title>
    <style>
        /* --- PURPLE THEME STYLING --- */
        body { 
            margin: 0; 
            overflow: hidden; 
            font-family: 'Palatino', 'Georgia', serif; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            height: 100vh; 
            background: linear-gradient(135deg, #f3e5f5 0%, #e1bee7 100%); 
        }
        .card { 
            text-align: center; 
            background: white; 
            padding: 2.5rem; 
            border-radius: 30px; 
            box-shadow: 0 15px 35px rgba(106, 27, 154, 0.2); 
            z-index: 5; 
            max-width: 420px;
            border: 2px solid #9c27b0;
        }
        /* Heart Animation */
        .art { 
            width: 120px; 
            height: auto; 
            fill: #7b1fa2;
            animation: pulse 1.5s infinite;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        h1 { color: #4a148c; font-size: 1.8rem; margin-bottom: 20px; }
        .buttons { 
            margin-top: 30px; 
            display: flex; 
            justify-content: center; 
            gap: 20px;
            height: 50px; 
        }
        button { 
            padding: 12px 30px; 
            font-size: 1.1rem; 
            border: none; 
            border-radius: 50px; 
            cursor: pointer; 
            font-weight: bold;
            transition: all 0.3s ease;
        }
        #yesBtn { 
            background-color: #9c27b0; 
            color: white; 
            box-shadow: 0 4px 15px rgba(156, 39, 176, 0.4);
        }
        #yesBtn:hover { background-color: #7b1fa2; transform: translateY(-2px); }
        #noBtn { 
            background-color: #e0e0e0; 
            color: #757575; 
            position: absolute; 
        }
        .hint { color: #9c27b0; font-style: italic; margin-top: 20px; font-size: 0.9rem; opacity: 0.8; }
        .result { display: none; }
        .result h2 { color: #4a148c; font-size: 2.5rem; margin-bottom: 10px; }
        .result p { color: #7b1fa2; font-size: 1.3rem; font-style: italic; }
        #confettiCanvas { position: fixed; top: 0; left: 0; pointer-events: none; z-index: 10; }
    </style>
</head>
<body>
    <canvas id="confettiCanvas"></canvas>
    <main class="card">
        <section id="questionZone">
            <svg class="art" viewBox="0 0 200 200">
                <path d="M100 183.1l-14.5-13.2C33.9 122.1 0 91.5 0 54.9 0 24.1 24.1 0 54.9 0c17.4 0 34.1 8.1 45.1 20.9C111 8.1 127.7 0 145.1 0 175.9 0 200 24.1 200 54.9c0 36.6-33.9 67.2-85.5 115.1L100 183.1z"/>
            </svg>
            <h1>Onyinyechi, will you be my valentine?</h1>
            <div class="buttons">
                <button id="yesBtn">Yes</button>
                <button id="noBtn">No</button>
            </div>
            <div class="hint" id="hint">“No” is not an option for a princess 💜</div>
        </section>
        <section class="result" id="result">
            <h2>YAY! 🎉</h2>
            <p>I love you my princess</p>
        </section>
    </main>
    <script>
        const yesBtn = document.getElementById("yesBtn");
        const noBtn = document.getElementById("noBtn");
        const questionZone = document.getElementById("questionZone");
        const result = document.getElementById("result");
        const hint = document.getElementById("hint");
        // "No" button runs away
        noBtn.addEventListener("mouseover", () => {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.position = "fixed";
            noBtn.style.left = x + "px";
            noBtn.style.top = y + "px";
        });
        // "Yes" button action
        yesBtn.addEventListener("click", () => {
            questionZone.style.display = "none";
            hint.style.display = "none";
            result.style.display = "block";
            // Confetti call would go here
        });
    </script>
</body>
</html>
