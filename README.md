<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Mouli Ray ❤️</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        body {
            background: linear-gradient(135deg, #fff5f7 0%, #ffd1dc 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow-x: hidden;
            text-align: center;
        }

        .card {
            background: rgba(255, 255, 255, 0.9);
            padding: 30px;
            border-radius: 30px;
            box-shadow: 0 10px 30px rgba(255, 77, 109, 0.2);
            backdrop-filter: blur(10px);
            max-width: 85%;
            margin: 20px;
            border: 2px solid white;
            transition: all 0.5s ease;
        }

        #teddy-img {
            width: 180px;
            border-radius: 20px;
            margin-bottom: 10px;
            transition: 0.5s;
        }

        h1 {
            color: #ff4d6d;
            font-size: 26px;
            margin: 10px 0;
        }

        .buttons {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            min-height: 80px;
        }

        button {
            padding: 12px 28px;
            font-size: 1.1rem;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: 0.3s;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }

        #yesBtn { background: #ff4d6d; color: white; }
        #noBtn { background: white; color: #ff4d6d; border: 1px solid #ff4d6d; position: absolute; }
        
        #letterBtn {
            background: #ff758f;
            color: white;
            display: none;
            margin: 20px auto;
        }

        #letterContent {
            display: none;
            background: #fff;
            padding: 25px;
            border-radius: 15px;
            border-left: 5px solid #ff4d6d;
            text-align: left;
            line-height: 1.6;
            color: #444;
            font-style: italic;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.05);
            margin-top: 20px;
            animation: slideUp 0.8s ease;
            max-height: 40vh;
            overflow-y: auto;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
        </audio>

    <div class="card" id="mainCard">
        <div id="gameSpace">
            <img id="teddy-img" src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueXN3ZzZ4bm9oZzR4ZzR4ZzR4ZzR4ZzR4ZzR4ZzR4ZzR4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/57Y8WpY8j9D960V8vS/giphy.gif" alt="Teddy">
            <h1 id="question">Mouli Ray, will you be my Valentine? 🧸</h1>
            <div class="buttons" id="btnWrapper">
                <button id="yesBtn" onclick="celebrate()">YES! ❤️</button>
                <button id="noBtn" onmouseover="moveButton()" ontouchstart="moveButton()">No</button>
            </div>
        </div>

        <div id="letterContent">
            <h3 style="color:#ff4d6d; margin-top:0;">Dear Mouli Ray,</h3>
            <p id="letter-text">
                "Dil rasta tera dekhe, Dil rasta dhoondhe tera..." <br><br>
                I don't know if it's cringey to simp over the same person; I know no previous version of mine would find writing letters or being this romantic normal. But yup, I am. That's what you made me. <br><br>
                You know, every time you say I'm a good boyfriend, I realize it's you who changed me from the core. May all success come to you (including me 😗). <br><br>
                I would choose you again and again, at any point. No one else's opinion matters to me... I love you ❤️. <br><br>
                Happy Valentine's Day. <br>
                Yours and only yours,<br>
                <b>Deepuuuu 😗</b>
            </p>
        </div>
        
        <button id="letterBtn" onclick="showLetter()">Read My Letter ✉️</button>
    </div>

    <script>
        function moveButton() {
            const btn = document.getElementById('noBtn');
            const padding = 60;
            const x = Math.random() * (window.innerWidth - btn.clientWidth - padding);
            const y = Math.random() * (window.innerHeight - btn.clientHeight - padding);
            btn.style.left = Math.max(padding/2, x) + 'px';
            btn.style.top = Math.max(padding/2, y) + 'px';
        }

        function celebrate() {
            const music = document.getElementById('bgMusic');
            music.play().catch(e => console.log("Audio play blocked"));

            const end = Date.now() + (4 * 1000);
            (function frame() {
                confetti({ particleCount: 3, angle: 60, spread: 55, origin: { x: 0 }, colors: ['#ff4d6d', '#ff758f'] });
                confetti({ particleCount: 3, angle: 120, spread: 55, origin: { x: 1 }, colors: ['#ff4d6d', '#ff758f'] });
                if (Date.now() < end) requestAnimationFrame(frame);
            }());

            document.getElementById('question').innerText = "Yay! ❤️ Happy Valentine's Day!";
            document.getElementById('btnWrapper').style.display = 'none';
            document.getElementById('noBtn').style.display = 'none';
            document.getElementById('teddy-img').src = "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExbmZ4eHF6ZzR4ZzR4ZzR4ZzR4ZzR4ZzR4ZzR4ZzR4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/v4aDfA8QjYg7u/giphy.gif";
            document.getElementById('letterBtn').style.display = 'block';
        }

        function showLetter() {
            document.getElementById('letterBtn').style.display = 'none';
            document.getElementById('letterContent').style.display = 'block';
            document.getElementById('teddy-img').style.width = '100px';
        }
    </script>
</body>
</html>
