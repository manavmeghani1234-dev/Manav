<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Valentine's Day, My Love ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;600&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            background: linear-gradient(-45deg, #ff6b6b, #feca57, #ff9ff3, #54a0ff);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating hearts */
        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .heart {
            position: absolute;
            color: #ff69b4;
            font-size: 20px;
            animation: float 6s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        /* Main container */
        .container {
            text-align: center;
            max-width: 800px;
            padding: 20px;
            z-index: 10;
            position: relative;
        }

        .title {
            font-family: 'Dancing Script', cursive;
            font-size: clamp(3rem, 8vw, 6rem);
            color: white;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.3);
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .subtitle {
            font-size: clamp(1.2rem, 4vw, 2rem);
            color: white;
            margin-bottom: 30px;
            font-weight: 300;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        /* Photo gallery */
        .photo-gallery {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin: 40px 0;
        }

        .photo {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid rgba(255,255,255,0.8);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .photo:hover {
            transform: scale(1.1) rotate(5deg);
            border-color: #ff69b4;
            box-shadow: 0 15px 40px rgba(255,105,180,0.4);
        }

        /* Love message */
        .love-message {
            background: rgba(255,255,255,0.95);
            padding: 40px;
            border-radius: 20px;
            margin: 40px 0;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            backdrop-filter: blur(10px);
            animation: slideUp 1s ease-out;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .message-title {
            font-family: 'Dancing Script', cursive;
            font-size: 2.5rem;
            color: #e91e63;
            margin-bottom: 20px;
        }

        .message-text {
            font-size: 1.2rem;
            line-height: 1.8;
            color: #333;
            margin-bottom: 30px;
        }

        /* Buttons */
        .btn {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(45deg, #ff6b6b, #ff8e8e);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            margin: 10px;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255,107,107,0.4);
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(255,107,107,0.6);
        }

        .btn-secondary {
            background: linear-gradient(45deg, #54a0ff, #7dc8ff);
            box-shadow: 0 10px 30px rgba(84,160,255,0.4);
        }

        .btn-secondary:hover {
            box-shadow: 0 15px 40px rgba(84,160,255,0.6);
        }

        /* Countdown */
        .countdown {
            font-size: 1.5rem;
            color: white;
            margin: 20px 0;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .photo-gallery {
                flex-direction: column;
                align-items: center;
            }
            
            .photo {
                width: 100px;
                height: 100px;
            }
            
            .love-message {
                padding: 20px;
                margin: 20px 10px;
            }
        }
    </style>
</head>
<body>
    <div class="hearts" id="hearts"></div>
    
    <div class="container">
        <h1 class="title" data-name="Sarah">Happy Valentine's Day, Sarah! ❤️</h1>
        <p class="subtitle">The love of my life, my everything, my forever...</p>
        
        <div class="countdown" id="countdown">
            Our love grows stronger every day! 💕
        </div>
        
        <div class="photo-gallery">
            <!-- Replace these with your actual photos -->
            <img src="https://via.placeholder.com/120/ff69b4/ffffff?text=💕" alt="Our first date" class="photo" onclick="enlargePhoto(this)">
            <img src="https://via.placeholder.com/120/feca57/ffffff?text=💕" alt="Our vacation" class="photo" onclick="enlargePhoto(this)">
            <img src="https://via.placeholder.com/120/54a0ff/ffffff?text=💕" alt="Just us" class="photo" onclick="enlargePhoto(this)">
            <img src="https://via.placeholder.com/120/ff9ff3/ffffff?text=💕" alt="Forever" class="photo" onclick="enlargePhoto(this)">
        </div>
        
        <div class="love-message">
            <h2 class="message-title">My Dearest [Her Name],</h2>
            <p class="message-text">
                Every day with you feels like a dream. You make my heart skip a beat and fill my world with color. 
                From our first laugh together to every moment since, you've been my greatest adventure. 
                I can't wait to create a lifetime more of memories with you. 
                <br><br>
                You are my sun, my moon, and all my stars. I love you more than words can say.
            </p>
            <p style="font-size: 1.5rem; font-weight: 600; color: #e91e63;">
                Forever yours,<br>
                <span style="font-family: 'Dancing Script', cursive; font-size: 2rem;">[Your Name]</span>
            </p>
        </div>
        
        <button class="btn" onclick="playMusic()">🎵 Play Our Song</button>
        <a href="https://www.google.com/maps/search/restaurant+near+me" target="_blank" class="btn btn-secondary">Dinner Reservation →</a>
        <br><br>
        <button class="btn" onclick="showSurprise()">💝 See Your Surprise!</button>
    </div>

    <script>
        // Customize these variables
        const GIRLFRIEND_NAME = "Sarah"; // Change to her name
        const YOUR_NAME = "Your Name";   // Change to your name
        const SONG_URL = "https://www.soundjay.com/misc/sounds/bell-ringing-05.wav"; // Add your song URL
        
        // Update title with her name
        document.querySelector('[data-name]').textContent = `Happy Valentine's Day, ${GIRLFRIEND_NAME}! ❤️`;
        document.querySelector('.message-text').innerHTML = `
            Every day with you feels like a dream. You make my heart skip a beat and fill my world with color. 
            From our first laugh together to every moment since, you've been my greatest adventure. 
            I can't wait to create a lifetime more of memories with you. 
            <br><br>
            You are my sun, my moon, and all my stars. I love you more than words can say.
        `;
        document.querySelector('.message-text + p').innerHTML = `
            Forever yours,<br>
            <span style="font-family: 'Dancing Script', cursive; font-size: 2rem;">${YOUR_NAME}</span>
        `;

        // Floating hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.innerHTML = '💖';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 3 + 4) + 's';
            heart.style.fontSize = (Math.random() * 10 + 15) + 'px';
            document.getElementById('hearts').appendChild(heart);
            
            setTimeout(() => {
                heart.remove();
            }, 7000);
        }

        setInterval(createHeart, 300);

        // Photo enlargement
        function enlargePhoto(img) {
            const modal = document.createElement('div');
            modal.style.cssText = `
                position: fixed; top: 0; left: 0; width: 100%; height: 100%; 
                background: rgba(0,0,0,0.9); z-index: 1000; 
                display: flex; justify-content: center; align-items: center;
            `;
            modal.innerHTML = `
                <img src="${img.src}" style="max-width: 90%; max-height: 90%; border-radius: 10px;">
                <button onclick="this.parentElement.remove()" style="
                    position: absolute; top: 20px; right: 20px; background: #ff6b6b; 
                    color: white; border: none; padding: 10px 20px; border-radius: 25px;
                    font-size: 18px; cursor: pointer;
                ">✕</button>
            `;
            document.body.appendChild(modal);
        }

        // Music player
        let audio;
        function playMusic() {
            if (!audio) {
                audio = new Audio(SONG_URL);
                audio.loop = true;
            }
            if (audio.paused) {
                audio.play();
                this.textContent = '⏸️ Pause Music';
            } else {
                audio.pause();
                this.textContent = '🎵 Play Our Song';
            }
        }

        // Surprise modal
        function showSurprise() {
            const surprise = document.createElement('div');
            surprise.style.cssText = `
                position: fixed; top: 0; left: 0; width: 100%; height: 100%; 
                background: linear-gradient(45deg, #ff9a9e, #fecfef, #fecfef, #ff9a9e);
                background-size: 400% 400%; animation: gradientShift 3s ease infinite;
                z-index: 1000; display: flex; flex-direction: column; 
                justify-content: center; align-items: center; text-align: center; padding: 20px;
            `;
            surprise.innerHTML = `
                <h1 style="font-family: 'Dancing Script', cursive; font-size: 4rem; color: #e91e63; margin-bottom: 20px;">
                    Surprise! 💝
                </h1>
                <p style="font-size: 1.5rem; color: #333; max-width: 500px; line-height: 1.6;">
                    Check your door! I left something special there for you... 
                    Can't wait to see your beautiful smile! 😍
                </p>
                <button onclick="this.parentElement.remove(); createHeartExplosion()" 
                        style="margin-top: 30px; padding: 15px 40px; background: #e91e63; 
                               color: white; border: none; border-radius: 50px; font-size: 1.2rem;
                               cursor: pointer; box-shadow: 0 10px 30px rgba(233,30,99,0.4);">
                    Got it! ❤️
                </button>
            `;
            document.body.appendChild(surprise);
        }

        // Heart explosion
        function createHeartExplosion() {
            for (let i = 0; i < 50; i++) {
                setTimeout(createHeart, i * 50);
            }
        }

        // PWA install prompt (optional)
        let deferredPrompt;
        window.addEventListener('beforeinstallprompt', (e) => {
            deferredPrompt = e;
        });
    </script>
</body>
</html>
