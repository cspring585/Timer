<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bee and Flower Timer</title>
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif; 
            background-color: #fdfcf0;
            color: #333;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }

        h1 { 
            font-size: 2.5rem; 
            color: #5d4037; 
            margin-bottom: 40px;
        }

        .timer-container {
            position: relative;
            width: 320px;
            height: 320px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .bee-path {
            position: absolute;
            width: 100%;
            height: 100%;
            border: 6px dotted #ffd54f;
            border-radius: 50%;
        }

        /* The Flower at the finish line */
        .flower {
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 3.5rem;
            z-index: 5;
        }

        #bee {
            position: absolute;
            font-size: 3.5rem;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            transform-origin: 160px 160px; 
            left: 0;
            top: 0;
            transition: transform 1s linear;
            z-index: 20;
        }

        .timer-display {
            font-size: 5rem;
            font-weight: 900;
            color: #5d4037;
            z-index: 10;
            font-variant-numeric: tabular-nums;
        }

        .happy-wiggle {
            animation: wiggle 0.2s ease-in-out infinite;
        }

        @keyframes wiggle {
            0% { transform: rotate(var(--final-angle)) translate(0, 0); }
            25% { transform: rotate(var(--final-angle)) translate(4px, 4px); }
            75% { transform: rotate(var(--final-angle)) translate(-4px, -4px); }
            100% { transform: rotate(var(--final-angle)) translate(0, 0); }
        }

        .controls, .custom-input, .action-btns {
            margin-top: 25px;
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            justify-content: center;
        }

        button {
            padding: 14px 24px;
            font-size: 1.2rem;
            cursor: pointer;
            border: none;
            border-radius: 15px;
            background: #ffecb3;
            color: #5d4037;
            font-weight: bold;
            box-shadow: 0 4px 0 #ffe082;
        }

        button:hover { background: #fff8e1; }
        button:active { transform: translateY(2px); box-shadow: 0 2px 0 #ffe082; }

        input {
            padding: 12px;
            font-size: 1.2rem;
            border-radius: 12px;
            border: 2px solid #ffd54f;
            width: 80px;
            text-align: center;
        }

        .stop-btn { background: #eeeeee; box-shadow: 0 4px 0 #bdbdbd; }
    </style>
</head>
<body>

    <h1>Bee Busy!</h1>

    <div class="timer-container">
        <div class="bee-path"></div>
        <div class="flower">🌸</div>
        <div id="bee">🐝</div>
        <div id="display" class="timer-display">00:00</div>
    </div>

    <div class="controls">
        <button onclick="setTime(1)">1 Min</button>
        <button onclick="setTime(5)">5 Min</button>
        <button onclick="setTime(10)">10 Min</button>
        <button onclick="setTime(15)">15 Min</button>
    </div>

    <div class="custom-input">
        <input type="number" id="customMin" placeholder="0">
        <button onclick="setCustomTime()">Set Custom</button>
    </div>

    <div class="action-btns">
        <button class="stop-btn" onclick="resetTimer()">Reset</button>
    </div>

    <script>
        let countdown;
        let timeLeft;
        let totalTimeSet;
        const display = document.getElementById('display');
        const bee = document.getElementById('bee');

        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

        function playEndSound() {
            const duration = 2.0; 
            const startTime = audioCtx.currentTime;

            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            const lfo = audioCtx.createOscillator();
            const lfoGain = audioCtx.createGain();
            
            osc.type = 'sawtooth';
            osc.frequency.setValueAtTime(85, startTime); 
            osc.frequency.exponentialRampToValueAtTime(65, startTime + duration);

            lfo.frequency.setValueAtTime(12, startTime); 
            lfoGain.gain.setValueAtTime(0.06, startTime); 
            
            lfo.connect(lfoGain);
            lfoGain.connect(gain.gain); 

            gain.gain.setValueAtTime(0.2, startTime);
            gain.gain.linearRampToValueAtTime(0, startTime + duration);

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            osc.start();
            lfo.start();
            osc.stop(startTime + duration);
            lfo.stop(startTime + duration);
        }

        function updateDisplay(seconds) {
            const mins = Math.floor(seconds / 60);
            const secs = seconds % 60;
            display.textContent = `${mins.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
            
            if (totalTimeSet > 0) {
                const angle = ((totalTimeSet - seconds) / totalTimeSet) * 360;
                bee.style.transform = `rotate(${angle}deg)`;
                bee.style.setProperty('--final-angle', `${angle}deg`);
            }
        }

        function setTime(mins) {
            resetTimer();
            totalTimeSet = mins * 60;
            timeLeft = totalTimeSet;
            updateDisplay(timeLeft);
            startTimer();
        }

        function setCustomTime() {
            const val = document.getElementById('customMin').value;
            if (val > 0) setTime(val);
        }

        function startTimer() {
            clearInterval(countdown);
            countdown = setInterval(() => {
                timeLeft--;
                updateDisplay(timeLeft);
                if (timeLeft <= 0) {
                    clearInterval(countdown);
                    timerFinished();
                }
            }, 1000);
        }

        function timerFinished() {
            bee.classList.add('happy-wiggle');
            display.textContent = "Bzzz!";
            playEndSound();
        }

        function resetTimer() {
            clearInterval(countdown);
            bee.classList.remove('happy-wiggle');
            bee.style.transform = `rotate(0deg)`;
            updateDisplay(0);
        }
    </script>
</body>
</html>
