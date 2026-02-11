<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Mum</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        :root {
            /* Resin Art Color Palette */
            --metallic-pink: linear-gradient(135deg, #ff007f, #ff85a2, #800040);
            --gold: linear-gradient(135deg, #d4af37, #fcf6ba, #aa771c);
            --metallic-green: linear-gradient(90deg, #1b4d3e, #2e8b57, #002200);
            --bg-gradient: linear-gradient(-45deg, #4b0082, #ff007f, #ffd700, #1e90ff);
        }

        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            /* Animated Colorful Background */
            background: var(--bg-gradient);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Entry Screen Overlay */
        #overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 100;
            transition: opacity 1s ease-out;
        }

        .enter-btn {
            padding: 20px 50px;
            font-size: 1.5rem;
            font-weight: bold;
            color: #fff;
            background: var(--metallic-pink);
            border: 3px solid #ffd700;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 10px 30px rgba(255, 0, 127, 0.5);
            transition: all 0.3s ease;
        }

        .enter-btn:hover {
            transform: scale(1.1) rotate(-2deg);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.7);
        }

        /* Message Styling */
        #message {
            position: absolute;
            top: 15%;
            width: 100%;
            text-align: center;
            opacity: 0;
            z-index: 10;
        }

        h1 {
            font-size: 5rem;
            margin: 0;
            background: var(--gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            filter: drop-shadow(4px 4px 5px rgba(0,0,0,0.5));
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* The Rose Construction */
        #garden {
            position: absolute;
            bottom: 0;
            width: 100%;
            height: 70vh;
            display: flex;
            justify-content: center;
            align-items: flex-end;
            pointer-events: none;
        }

        .rose {
            position: relative;
            display: none;
        }

        .stem {
            width: 12px;
            height: 0;
            background: var(--metallic-green);
            margin: 0 auto;
            border-radius: 10px;
            transition: height 2.5s ease-out;
            box-shadow: 2px 0 10px rgba(0,0,0,0.3);
        }

        .flower-head {
            width: 120px;
            height: 120px;
            position: relative;
            transform: scale(0);
            transition: transform 2s cubic-bezier(0.175, 0.885, 0.32, 1.275) 1s;
        }

        .petal {
            position: absolute;
            width: 80px;
            height: 80px;
            background: var(--gold);
            border: 3px solid #ff007f; /* Shiny Pink Outline */
            border-radius: 50% 50% 10% 50%;
            transform-origin: bottom right;
            box-shadow: inset 0 0 15px rgba(255, 0, 127, 0.3);
        }

        /* Rose Petal Rotation */
        .petal:nth-child(1) { transform: rotate(0deg); }
        .petal:nth-child(2) { transform: rotate(72deg); }
        .petal:nth-child(3) { transform: rotate(144deg); }
        .petal:nth-child(4) { transform: rotate(216deg); }
        .petal:nth-child(5) { transform: rotate(288deg); }

        /* Falling Elements */
        .falling {
            position: absolute;
            pointer-events: none;
            animation: fall 5s linear forwards;
            z-index: 5;
        }

        @keyframes fall {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(90vh) rotate(720deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <div id="overlay">
        <button class="enter-btn" onclick="startSurprise()">Click for your Birthday Gift 💖</button>
    </div>

    <div id="message">
        <h1>Happy Birthday Mum</h1>
    </div>

    <div id="garden">
        <div class="rose" id="birthdayRose">
            <div class="flower-head" id="head">
                <div class="petal"></div>
                <div class="petal"></div>
                <div class="petal"></div>
                <div class="petal"></div>
                <div class="petal"></div>
            </div>
            <div class="stem" id="stem"></div>
        </div>
    </div>

    <script>
        function startSurprise() {
            // Hide Overlay
            const overlay = document.getElementById('overlay');
            overlay.style.opacity = '0';
            setTimeout(() => overlay.style.display = 'none', 1000);

            // Colorful Confetti Explosion
            const colors = ['#ff007f', '#ffd700', '#00d2ff', '#ffffff', '#2e8b57'];
            confetti({
                particleCount: 200,
                spread: 100,
                origin: { y: 0.6 },
                colors: colors
            });

            // Rose Bloom logic
            const rose = document.getElementById('birthdayRose');
            const stem = document.getElementById('stem');
            const head = document.getElementById('head');
            const message = document.getElementById('message');

            rose.style.display = 'block';
            
            setTimeout(() => {
                stem.style.height = '350px';
                head.style.transform = 'scale(1.8) translateY(-320px)';
                message.style.opacity = '1';
                message.style.transition = 'opacity 2s ease-in';
                
                // Continuous falling effects
                setInterval(createFallingLeaf, 600);
                setInterval(createFallingPetal, 900);
            }, 100);
        }

        function createFallingLeaf() {
            const leaf = document.createElement('div');
            leaf.className = 'falling';
            leaf.style.left = (Math.random() * 100) + 'vw';
            leaf.style.top = '-5vh';
            leaf.style.width = '20px';
            leaf.style.height = '30px';
            leaf.style.background = 'linear-gradient(#2e8b57, #1b4d3e)';
            leaf.style.borderRadius = '0 80% 0 80%';
            leaf.style.boxShadow = '0 0 5px rgba(0,0,0,0.2)';
            document.body.appendChild(leaf);
            setTimeout(() => leaf.remove(), 5000);
        }

        function createFallingPetal() {
            const petal = document.createElement('div');
            petal.className = 'falling';
            petal.style.left = (Math.random() * 100) + 'vw';
            petal.style.top = '-5vh';
            const size = Math.random() * 20 + 15;
            petal.style.width = size + 'px';
            petal.style.height = size + 'px';
            petal.style.background = 'gold';
            petal.style.border = '2px solid #ff007f';
            petal.style.borderRadius = '50% 50% 0 50%';
            document.body.appendChild(petal);
            setTimeout(() => petal.remove(), 5000);
        }
    </script>
</body>
</html>
