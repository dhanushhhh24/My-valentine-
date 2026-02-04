# My-valentine-
"A special surprise for the most amazing girl in the world. ❤️"
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Favorite Person ❤️</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            font-family: 'Brush Script MT', cursive, sans-serif;
            background: linear-gradient(135deg, #ffdde1, #ee9ca7);
            overflow: hidden;
            text-align: center;
            transition: background 1s ease;
        }

        #container {
            z-index: 10;
            padding: 20px;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 20px;
            backdrop-filter: blur(5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        h1 {
            color: #d32f2f;
            font-size: 3.5rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
            margin-bottom: 30px;
        }

        .buttons {
            position: relative;
            height: 100px;
            width: 300px;
            margin: 0 auto;
        }

        button {
            padding: 15px 35px;
            font-size: 1.5rem;
            cursor: pointer;
            border: none;
            border-radius: 50px;
            transition: all 0.3s ease;
            font-family: 'Arial', sans-serif;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        #yesBtn {
            background-color: #ff4d6d;
            color: white;
        }

        #yesBtn:hover {
            transform: scale(1.1);
            background-color: #ff758f;
        }

        #noBtn {
            background-color: #ffffff;
            color: #ff4d6d;
            position: absolute;
        }

        /* Floating Hearts Background */
        .heart {
            position: absolute;
            color: #ff85a1;
            font-size: 20px;
            animation: float 5s linear infinite;
            opacity: 0;
            z-index: 1;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        .success-bg {
            background: linear-gradient(135deg, #fb6f92, #ffb3c1) !important;
        }
    </style>
</head>
<body id="body">

    <div id="container">
        <h1 id="question">Will you be my Valentine? ❤️</h1>
        <div class="buttons">
            <button id="yesBtn" onclick="celebrate()">Yes</button>
            <button id="noBtn">No</button>
        </div>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const body = document.getElementById('body');
        const container = document.getElementById('container');

        // Logic for the elusive "No" button
        noBtn.addEventListener('mouseover', () => {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        });

        // Create floating hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = Math.random() > 0.5 ? '❤️' : '🌹';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
            document.body.appendChild(heart);
            
            setTimeout(() => { heart.remove(); }, 5000);
        }

        setInterval(createHeart, 300);

        // Success State
        function celebrate() {
            body.classList.add('success-bg');
            container.innerHTML = `
                <h1 style="font-size: 4rem;">Yay! 🥰</h1>
                <h2 style="color: white; font-size: 2.5rem;">Can't wait to get married to you!</h2>
                <div style="font-size: 5rem;">🌹❤️🌹❤️🌹</div>
            `;
            
            // Intensify the flowers and hearts
            setInterval(createHeart, 100);
        }
    </script>
</body>
</html>
