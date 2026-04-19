# tbday
wishing birthday 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Bhonduuu!</title>
    <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Quicksand:wght@400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --pink: #ffafcc;
            --dark-pink: #ff8fab;
            --cream: #fff5f5;
            --panda-black: #333;
        }

        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            font-family: 'Quicksand', sans-serif;
            background-color: var(--cream);
            overflow: hidden;
        }

        /* Animations */
        @keyframes float {
            0% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
            100% { transform: translateY(0px) rotate(0deg); }
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }

        @keyframes heartBeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        .page {
            display: none;
            height: 100vh;
            width: 100%;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: absolute;
            top: 0;
            left: 0;
            animation: fadeIn 0.8s ease-out;
        }

        .active { display: flex; }

        h1 {
            font-family: 'Pacifico', cursive;
            color: var(--dark-pink);
            margin-bottom: 20px;
            padding: 0 20px;
        }

        img {
            max-width: 300px;
            border-radius: 20px;
            border: 8px solid white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            margin-bottom: 20px;
            animation: float 4s ease-in-out infinite;
        }

        /* Password Input Style */
        .pass-container {
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        input {
            padding: 10px;
            border: 2px solid var(--pink);
            border-radius: 8px;
            outline: none;
            font-size: 16px;
        }

        button {
            padding: 10px 25px;
            background-color: var(--dark-pink);
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            margin-top: 10px;
            transition: 0.3s;
        }

        button:hover { background-color: #fb6f92; transform: scale(1.05); }

        /* Floating decorations */
        .decor {
            position: fixed;
            pointer-events: none;
            z-index: -1;
            font-size: 24px;
        }

        /* Page 3: Gift Box */
        .gift-box {
            width: 150px;
            height: 150px;
            background: var(--dark-pink);
            position: relative;
            cursor: pointer;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 50px;
            transition: 0.5s;
        }

        .gift-box::before {
            content: '';
            position: absolute;
            width: 20px;
            height: 100%;
            background: rgba(255,255,255,0.3);
        }

        .gift-box.open {
            transform: scale(0);
            opacity: 0;
        }

        #surprise-photo {
            display: none;
            width: 280px;
        }

        /* Page 5: Letter */
        .letter {
            background: white;
            padding: 30px;
            width: 80%;
            max-width: 500px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            line-height: 1.6;
            text-align: left;
            border-left: 5px solid var(--dark-pink);
        }

        .hindi-text {
            font-size: 1.2rem;
            color: #444;
            padding: 20px;
            line-height: 1.8;
        }

        .collage {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            max-width: 90%;
        }
    </style>
</head>
<body>

    <!-- Background Animations -->
    <div id="decorations"></div>

    <!-- Page 1: Login -->
    <section id="page1" class="page active">
        <h1>THIS IS FOR YOU MY BHONDUU....</h1>
        <img src="photo1.jpg" alt="Your Photo">
        <div class="pass-container">
            <input type="password" id="password" placeholder="Enter password...">
            <br>
            <button onclick="checkPassword()">Unlock ❤️</button>
        </div>
    </section>

    <!-- Page 2: Collage -->
    <section id="page2" class="page">
        <h1>happy biirthday pyaaari bhonduu</h1>
        <img src="collage.jpg" style="max-width: 80%;" alt="Our Collage">
        <button onclick="nextPage(3)">Next Page 🐾</button>
    </section>

    <!-- Page 3: Gift Box -->
    <section id="page3" class="page">
        <h1 id="gift-msg">click to open</h1>
        <div class="gift-box" id="gift" onclick="openGift()">🎁</div>
        <div id="surprise-area" style="display:none; flex-direction:column; align-items:center;">
            <img src="photo3.jpg" id="surprise-photo" alt="Cute Photo">
            <h2 style="color: var(--dark-pink);">cutest thing in the whole world</h2>
            <button onclick="nextPage(4)">Go to Next Page</button>
        </div>
    </section>

    <!-- Page 4: Hindi Message -->
    <section id="page4" class="page">
        <img src="photo4.jpg" alt="Beautiful You">
        <p class="hindi-text">
            आपका व्यक्तित्व उस अलौकिक आभा के समान है, जो बिना किसी श्रृंगार के भी मन को मुग्ध कर लेती है। आपकी सादगी ही आपका वास्तविक सौंदर्य है।
        </p>
        <button onclick="nextPage(5)">Read my letter 💌</button>
    </section>

    <!-- Page 5: Letter -->
    <section id="page5" class="page">
        <div class="letter">
            <p><strong>Happy Birthday pyaari Bhonduuuu! 🎂❤️</strong></p>
            <p>Tumhe pata hai na ki tum mere liye kitni special ho? Tum thodi si buddhu ho thodi si ziddi bhi 😝😝 lekin jaisi bhi ho... Bestest ever ho.</p>
            <p>I promise ki main hamesha tumahre saath khada raunga tumhari saari baate sunne ke liye aur tumhe har mushkil mein sambhalne ke liye Tayyar hu. Tum hamesha aise hi hasti rehna kyunki tumhari smile dekh kar mera din ban jata hai.</p>
            <p>Stay the same,<br>My favorite Bhonduuuu! ✨🥹🎈</p>
        </div>
        <button onclick="restart()">Back to Start 🐼</button>
    </section>

    <script>
        // Password Logic
        function checkPassword() {
            const pass = document.getElementById('password').value;
            if(pass.toLowerCase() === "panda") {
                nextPage(2);
            } else {
                alert("Wrong password, my Bhonduu! Hint: 🐼");
            }
        }

        // Navigation Logic
        function nextPage(pageNum) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('page' + pageNum).classList.add('active');
        }

        function restart() {
            nextPage(1);
            document.getElementById('password').value = "";
        }

        // Gift Box Logic
        function openGift() {
            document.getElementById('gift').classList.add('open');
            document.getElementById('gift-msg').style.display = 'none';
            setTimeout(() => {
                document.getElementById('gift').style.display = 'none';
                document.getElementById('surprise-area').style.display = 'flex';
                document.getElementById('surprise-photo').style.display = 'block';
            }, 500);
        }

        // Create Floating Pandas and Hearts
        function createDecor() {
            const symbols = ['🐼', '❤️', '🎈', '🌸', '✨'];
            const container = document.getElementById('decorations');
            
            for (let i = 0; i < 20; i++) {
                const span = document.createElement('span');
                span.className = 'decor';
                span.innerHTML = symbols[Math.floor(Math.random() * symbols.length)];
                span.style.left = Math.random() * 100 + 'vw';
                span.style.top = Math.random() * 100 + 'vh';
                span.style.opacity = Math.random();
                span.style.animation = `float ${3 + Math.random() * 5}s infinite ease-in-out`;
                container.appendChild(span);
            }
        }

        createDecor();
    </script>
</body>
</html>
