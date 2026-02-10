 details
Logo for Gemini Apps
Gemini Apps
Prompted Yes
Details
event
Today at 1:26 AM
apps
Gemini Apps
chat
Getting this live on a real link is the ultimate flex. Since you're ready, let’s get this hosted so you can text it to Baby Raïssa!

We’ll use GitHub Pages because it’s free, it stays up forever, and it looks professional.

Step 1: Create your "Storage Box" (Repository)
Go to GitHub.com and sign up or log in.
On the left side of your dashboard, click the green "New" button (or the + icon in the top right and select "New repository").
Repository name: Type valentine (or anything you like).
Make sure it is set to Public.
Check the box that says "Add a README file".
Scroll down and click "Create repository".
Step 2: Create the Website File
Now that you’re inside your new repository, click the "Add file" button and choose "Create new file".
Name your file: You must name it index.html (this tells the internet "This is the home page").
Edit new file: Copy the code I gave you in the previous message and paste it into the big text box.
Scroll down to the bottom and click the green "Commit changes..." button, then click "Commit changes" again in the pop-up.
Step 3: Turn on the Link
In that same repository, click on the "Settings" tab (top menu bar with the ⚙️ icon).
On the left-hand sidebar, click "Pages".
Under the "Build and deployment" section, look at "Branch".
Click the dropdown that says "None", select "main", and then click "Save".
Step 4: Your Live Link! 🚀
Wait about 60 seconds for GitHub to build the site.

Your link will be:
https://[YourGitHubUsername].github.io/valentine/

Pro-Tip: If you want to make the link even "cuter," you can use a site like Bitly or TinyURL to turn that long link into something like bit.ly/ForBabyRaissa.

Would you like me to double-check the link for you once you've set it up, or should we add some "falling heart" animations to the code to make it look even more like the TikTok?

I've updated the code to match the specific layout from your image: the messages appear in a list on the left, the buttons are that perfect "pill" shape, and the font is big, bold, and pink.

The "Baby Raïssa" Valentine Code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Baby Raïssa ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap');

        body {
            background-color: #fff2e6; /* Pale cream/pink background */
            background-image: radial-gradient(#ffb3c1 0.5px, transparent 0.5px);
            background-size: 20px 20px; /* Subtle heart/dot aesthetic */
            font-family: 'Fredoka One', cursive;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }

        .container {
            text-align: center;
            max-width: 600px;
            position: relative;
        }

        h1 {
            color: #ff4d8d;
            font-size: 4rem;
            margin-bottom: 30px;
            line-height: 1.2;
            text-shadow: 2px 2px #fff;
        }

        .main-ui {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
        }

        /* Left side messages */
        #message-list {
            text-align: left;
            color: #d63384;
            font-size: 1.2rem;
            min-width: 200px;
        }

        .guilt-text {
            margin: 5px 0;
            animation: fadeIn 0.5s ease;
        }

        /* Button Styling */
        .btn-box {
            display: flex;
            gap: 20px;
            align-items: center;
        }

        button {
            padding: 20px 50px;
            font-size: 1.5rem;
            border: none;
            border-radius: 100px; /* Pill shape */
            cursor: pointer;
            font-family: 'Fredoka One', cursive;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 8px 15px rgba(255, 77, 141, 0.2);
        }

        #noBtn { background-color: #ff85a2; color: white; }
        #yesBtn { background-color: #ff4d8d; color: white; }

        #yesBtn:hover { transform: scale(1.1); background-color: #ff1f6d; }

        /* Success Screen */
        #success {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: #fff2e6;
            z-index: 100;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        .final-text {
            color: #ff4d8d;
            font-size: 3.5rem;
            padding: 40px;
        }

        @keyframes fadeIn { from { opacity: 0; transform: translateX(-10px); } to { opacity: 1; transform: translateX(0); } }
    </style>
</head>
<body>

    <div id="content" class="container">
        <h1>Baby Raïssa <br> will you be my Valentine?</h1>
        
        <div class="main-ui">
            <div id="message-list">
                </div>

            <div class="btn-box">
                <button id="noBtn">NO</button>
                <button id="yesBtn">YES</button>
            </div>
        </div>
    </div>

    <div id="success">
        <h1 class="final-text">thank you for being my valentine, i love u so much ❤️</h1>
        <div style="font-size: 5rem;">✨🥰🌸</div>
    </div>

    <script>
        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');
        const messageList = document.getElementById('message-list');
        const content = document.getElementById('content');
        const success = document.getElementById('success');

        let yesScale = 1;
        let messageIndex = 0;

        const guiltMessages = [
            "are you sure?😏",
            "you hate me and want me to die?😩",
            "Say yes please?🙂",
            "Clicked No? Wow!!!! 😩",
            "baby pleaseee? 🤗"
        ];

        noBtn.addEventListener('click', () => {
            // 1. Grow the YES button
            yesScale += 0.4;
            yesBtn.style.transform = `scale(${yesScale})`;
            
            // 2. Add message to the list on the left
            if (messageIndex < guiltMessages.length) {
                const newMsg = document.createElement('p');
                newMsg.className = 'guilt-text';
                newMsg.innerText = guiltMessages[messageIndex];
                messageList.appendChild(newMsg);
                messageIndex++;
            }
            
            // 3. Make the "NO" button slightly harder to click (optional shift)
            noBtn.style.transform = `scale(${1 - (messageIndex * 0.05)})`;
        });

        yesBtn.addEventListener('click', () => {
            content.style.display = 'none';
            success.style.display = 'flex';
        });
    </script>
</body>
</html>
