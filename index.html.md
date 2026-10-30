# index.html  
  
<!DOCTYPE html>  
<html lang="ar" dir="rtl">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>**عيد** **ميلاد** **سعيد** **يا** **أخويا** OMAR 🎉</title>  
    <style>  
        * {  
            box-sizing: border-box;  
            margin: 0;  
            padding: 0;  
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;  
        }  
  
        body {  
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);  
            color: #fff;  
            min-height: 100vh;  
            display: flex;  
            flex-direction: column;  
            align-items: center;  
            justify-content: center;  
            overflow-x: hidden;  
            padding: 20px;  
            text-align: center;  
        }  
  
        .container {  
            max-width: 600px;  
            width: 100%;  
            background: rgba(255, 255, 255, 0.05);  
            backdrop-filter: blur(12px);  
            border: 1px solid rgba(255, 255, 255, 0.1);  
            border-radius: 20px;  
            padding: 30px;  
            box-shadow: 0 15px 35px rgba(0,0,0,0.5);  
            position: relative;  
            z-index: 10;  
        }  
  
        h1 {  
            font-size: 2.2rem;  
            color: #ffd700;  
            margin-bottom: 20px;  
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);  
        }  
  
        .message-box {  
            background: rgba(0, 0, 0, 0.3);  
            border-radius: 15px;  
            padding: 20px;  
            margin: 20px 0;  
            border-right: 5px solid #ff416c;  
        }  
  
        .message-box p {  
            font-size: 1.4rem;  
            line-height: 1.8;  
            color: #fff;  
            font-weight: bold;  
        }  
  
        .from-text {  
            color: #ff416c;  
            font-size: 1.5rem;  
            margin-top: 10px;  
            display: block;  
        }  
  
        .music-section {  
            margin-top: 25px;  
            background: rgba(255, 255, 255, 0.08);  
            padding: 15px;  
            border-radius: 12px;  
        }  
  
        .music-section h3 {  
            font-size: 1.1rem;  
            margin-bottom: 10px;  
            color: #00f2fe;  
        }  
  
        select, input[type="file"] {  
            width: 100%;  
            padding: 10px;  
            border-radius: 8px;  
            border: none;  
            background: #fff;  
            color: #333;  
            font-size: 1rem;  
            margin-bottom: 10px;  
            cursor: pointer;  
        }  
  
        audio {  
            width: 100%;  
            margin-top: 10px;  
        }  
  
        .fireworks-canvas {  
            position: fixed;  
            top: 0;  
            left: 0;  
            width: 100%;  
            height: 100%;  
            pointer-events: none;  
            z-index: 1;  
        }  
    </style>  
</head>  
<body>  
  
    <canvas class="fireworks-canvas" id="fireworks"></canvas>  
  
    <div class="container">  
        <h1>🎉 **عيد** **ميلاد** **سعيد** 🎉</h1>  
          
        <div class="message-box">  
            <p>Kol Sana Went A5oya w Sa7by w 7abiby H.B.D OMAR ♥️😍</p>  
            <span class="from-text">From HAMADA 👑</span>  
        </div>  
  
        <div class="music-section">  
            <h3>🎵 **اختر** **أو** **ارفع** **أغنية** **الاحتفال**:</h3>  
            <select id="presetMusic" onchange="changePresetMusic()">  
                <option value="">-- **اختر** **نغمة** **جاهزة** --</option>  
                <option value="https://www.bensound.com/bensound-music/bensound-ukulele.mp3">**أغنية** **مبهجة** (Happy Ukulele)</option>  
                <option value="https://www.bensound.com/bensound-music/bensound-creativeminds.mp3">**أغنية** **هادئة** (Creative Minds)</option>  
            </select>  
              
            <label style="font-size: 0.9rem; display: block; margin: 5px 0; color: #ddd;">**أو** **ارفع** **أغنية** **من** **جهازك** (MP3, WAV, M4A):</label>  
            <input type="file" id="customAudioFile" accept="audio/*" onchange="loadCustomMusic(event)">  
  
            <audio id="audioPlayer" controls autoplay loop>  
                <source src="https://www.bensound.com/bensound-music/bensound-ukulele.mp3" type="audio/mpeg">  
                **متصفحك** **لا** **يدعم** **مشغل** **الصوت**.  
            </audio>  
        </div>  
    </div>  
  
    <script>  
        // **تشغيل** **الموسيقى** **المرفوعة** **من** **الجهاز** **بجميع** **الصيغ**  
        function loadCustomMusic(event) {  
            const file = event.target.files[0];  
            if (file) {  
                const audioPlayer = document.getElementById('audioPlayer');  
                const fileURL = URL.createObjectURL(file);  
                audioPlayer.src = fileURL;  
                audioPlayer.play().catch(e => console.log("**التشغيل** **التلقائي** **يتطلب** **تفاعل** **المستخدم**"));  
            }  
        }  
  
        function changePresetMusic() {  
            const select = document.getElementById('presetMusic');  
            const audioPlayer = document.getElementById('audioPlayer');  
            if (select.value) {  
                audioPlayer.src = select.value;  
                audioPlayer.play().catch(e => console.log("**التشغيل** **التلقائي** **يتطلب** **تفاعل** **المستخدم**"));  
            }  
        }  
  
        // **تأثير** **الألعاب** **النارية** **البسيط**  
        const canvas = document.getElementById('fireworks');  
        const ctx = canvas.getContext('2d');  
        function resizeCanvas() {  
            canvas.width = window.innerWidth;  
            canvas.height = window.innerHeight;  
        }  
        window.addEventListener('resize', resizeCanvas);  
        resizeCanvas();  
  
        const particles = [];  
        function createFirework() {  
            const x = Math.random() * canvas.width;  
            const y = Math.random() * (canvas.height / 2);  
            const color = `hsl(${Math.random() * 360}, 100%, 50%)`;  
            for (let i = 0; i < 30; i++) {  
                particles.type = 'firework';  
                particles.push({  
                    x: x,  
                    y: y,  
                    angle: Math.random() * Math.PI * 2,  
                    speed: Math.random() * 4 + 1,  
                    radius: 3,  
                    color: color,  
                    alpha: 1,  
                    decay: Math.random() * 0.02 + 0.01  
                });  
            }  
        }  
  
        function animate() {  
            ctx.fillStyle = 'rgba(15, 12, 41, 0.2)';  
            ctx.fillRect(0, 0, canvas.width, canvas.height);  
  
            particles.forEach((p, index) => {  
                p.x += Math.cos(p.angle) * p.speed;  
                p.y += Math.sin(p.angle) * p.speed;  
                p.alpha -= p.decay;  
  
                if (p.alpha <= 0) {  
                    particles.splice(index, 1);  
                } else {  
                    ctx.save();  
                    ctx.globalAlpha = p.alpha;  
                    ctx.beginPath();  
                    ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);  
                    ctx.fillStyle = p.color;  
                    ctx.fill();  
                    ctx.restore();  
                }  
            });  
  
            requestAnimationFrame(animate);  
        }  
  
        setInterval(createFirework, 800);  
        animate();  
    </script>  
</body>  
</html>  
