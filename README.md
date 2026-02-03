<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KUKU, Be My Valentine? ❤️</title>

    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #ffebee;
            font-family: Arial, sans-serif;
            overflow: hidden;
            margin: 0;
            text-align: center;
        }

        h1 {
            color: #d32f2f;
            text-shadow: 2px 2px white;
            z-index: 10;
        }

        .buttons {
            position: relative;
            width: 300px;
            height: 120px;
            display: flex;
            justify-content: center;
            gap: 20px;
            z-index: 10;
        }

        button {
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            border: none;
            border-radius: 50px;
            transition: 0.2s;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        #yesBtn {
            background-color: #ff4081;
            color: white;
        }

        #noBtn {
            background-color: #9e9e9e;
            color: white;
            position: absolute;
        }

        /* Floating hearts */
        .heart {
            position: absolute;
            color: #ff80ab;
            font-size: 20px;
            user-select: none;
            pointer-events: none;
            animation: floatUp 4s linear infinite;
            opacity: 0;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(100vh) scale(0.5);
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh) scale(1.5);
                opacity: 0;
            }
        }
    </style>
</head>

<body>

    <h1>KUKU ❤️<br>Will you be my Valentine?</h1>

    <div class="buttons">
        <button id="yesBtn" onclick="sayILoveYou()">Yes 💕</button>
        <button id="noBtn" onmouseover="moveButton()">No 🙈</button>
    </div>

    <script>
        // Floating hearts generator
        function createHeart() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "❤️";
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = (Math.random() * 2 + 3) + "s";
            document.body.appendChild(heart);

            setTimeout(() => heart.remove(), 5000);
        }

        setInterval(createHeart, 300);

        function sayILoveYou() {
            alert("I Love You KUKU ❤️");

            document.body.innerHTML = `
                <div>
                    <h1 style="font-size:3rem;">Yayyy KUKU! 🥰🌹</h1>
                    <p style="font-size:1.5rem;">
                        You just made my heart so happy ❤️<br>
                        Happy Valentine’s Day!
                    </p>
                </div>
            `;

            setInterval(createHeart, 150);
        }

        function moveButton() {
            const btn = document.getElementById("noBtn");
            const x = Math.random() * (window.innerWidth - btn.offsetWidth);
            const y = Math.random() * (window.innerHeight - btn.offsetHeight);

            btn.style.left = x + "px";
            btn.style.top = y + "px";
        }
    </script>

</body>
</html>
