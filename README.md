<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Baby Raïssa ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fredoka+One&family=Gaegu:wght@400;700&display=swap');

        body {
            background-color: #fff2e6;
            background-image: radial-gradient(#ffb3c1 0.5px, transparent 0.5px);
            background-size: 20px 20px;
            font-family: 'Fredoka One', cursive;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            overflow-x: hidden;
            color: #ff4d8d;
        }

        .container { text-align: center; max-width: 600px; padding: 20px; }

        h1 { font-size: clamp(2rem, 8vw, 3.5rem); text-shadow: 2px 2px #fff; margin-bottom: 10px; }
        p { font-size: 1.1rem; margin-bottom: 30px; }

        /* Buttons */
        .btn-box { display: flex; gap: 20px; align-items: center; justify-content: center; min-height: 150px; }
        button {
            padding: 15px 45px;
            font-size: 1.4rem;
            border: none;
            border-radius: 100px;
            cursor: pointer;
            font-family: 'Fredoka One', cursive;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        #noBtn { background-color: #f1f1f1; color: #888; }
        #yesBtn { background-color: #ff4d8d; color: white; position: relative; }

        /* Post-Yes Section */
        #success { display: none; flex-direction: column; align-items: center; animation: fadeIn 0.8s ease; }
        
        .envelope-container {
            background: rgba(255, 255, 255, 0.5);
            padding: 40px;
            border-radius: 20px;
            margin: 20px 0;
        }

        .envelope {
            width: 120px;
            height: 80px;
            background-color: #ffb3c1;
            position: relative;
            cursor: pointer;
            border-radius: 0 0 5px 5px;
            margin: 0 auto 20px;
        }
        .envelope::after {
            content: "";
            position: absolute;
            top: 0; left: 0;
            border-left: 60px solid transparent;
            border-right: 60px solid transparent;
            border-top: 50px solid #ff4d8d;
        }

        .letter-box {
            display: none;
            background: white;
            padding: 35px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(255, 77, 141, 0.15);
            font-family: 'Gaegu', cursive;
            font-size: 1.4rem;
            color: #444;
            line-height: 1.5;
            text-align: left;
            border: 2px dashed #ffb3c1;
            animation: slideUp 0.6s ease;
        }

        #guilt-msg { height: 30px; font-size: 1rem; font-style: italic; margin-bottom: 10px; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes slideUp { from { transform: translateY(30px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
    </style>
</head>
<body>

    <div id="content" class="container">
        <h1>Will You Be My Valentine? 💕</h1>
        <p>Hey baby! I have something important to ask you...</p>
        
        <div id="guilt-msg"></div>

        <div class="btn-box">
            <button id="noBtn">No 🥺</button>
            <button id="yesBtn">YES! 💖</button>
        </div>
    </div>

    <div id="success" class="container">
        <h1>Yaaay! You said YES! 🥳</h1>
        <p>Because you're so sweet, I've prepared something! ✨</p>
        
        <div class="envelope-container">
            <div class="envelope" id="envelope"></div>
            <p style="font-size: 0.9rem;">📍 Click the envelope to read your letter</p>
            
            <div class="letter-box" id="letter">
                <strong>My Love Raïssa,</strong><br><br>
                I wanna tell you how much I really appreciate and admire the way you carry yourself, the warmth you bring in my life without even trying and mostly the way your smile stays with me longer than it should.<br><br>
                Baby you brought something in my life that I didn’t know I was missing. Be my valentine for now and forever, I love you ❤️<br><br>
                <strong>Forever yours, Charlie</strong>
            </div>
        </div>
    </div>

    <script>
        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');
        const guiltMsg = document.getElementById('guilt-msg');
        const content = document.getElementById('content');
        const success = document.getElementById('success');
        const envelope = document.getElementById('envelope');
        const letter = document.getElementById('letter');

        let yesScale = 1;
        let index = 0;
        const messages = [
            "Are you sure? 😏",
            "You hate me and want me to die? 😩",
            "Say yes please? 🙂",
            "Clicked No? Wow!!!! 😩",
            "Baby pleaseee? 🤗"
        ];

        noBtn.addEventListener('click', () => {
            yesScale += 0.4;
            yesBtn.style.transform = `scale(${yesScale})`;
            if (index < messages.length) {
                guiltMsg.innerText = messages[index];
                index++;
            }
        });

        yesBtn.addEventListener('click', () => {
            content.style.display = 'none';
            success.style.display = 'flex';
        });

        envelope.addEventListener('click', () => {
            envelope.style.display = 'none';
            letter.style.display = 'block';
        });
    </script>
</body>
</html>
