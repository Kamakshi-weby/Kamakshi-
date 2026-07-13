
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE BLACKWOOD PARADOX</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Creepster&family=Special+Elite&display=swap');

        :root {
            --bg-color: #050805;
            --corpse-pale: #cbd5e1;
            --blood-crimson: #880808;
            --moss-green: #1e3f20;
            --neon-glow: #39ff14;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--corpse-pale);
            font-family: 'Special Elite', monospace;
            overflow-x: hidden;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Nightmare Forest Vignette Overlay */
        .vignette {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: radial-gradient(circle, transparent 30%, rgba(0,0,0,0.95) 90%);
            pointer-events: none;
            z-index: 10;
        }

        /* Scanline effect for old-school creepy UI */
        .scanlines {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
            background-size: 100% 4px, 6px 100%;
            pointer-events: none;
            z-index: 11;
        }

        .game-container {
            width: 90%;
            max-width: 800px;
            height: 85vh;
            background: rgba(10, 15, 10, 0.85);
            border: 2px solid var(--blood-crimson);
            box-shadow: 0 0 30px rgba(136, 8, 8, 0.4);
            padding: 30px;
            overflow-y: auto;
            position: relative;
            z-index: 5;
        }

        /* Custom Scrollbar */
        .game-container::-webkit-scrollbar {
            width: 8px;
        }
        .game-container::-webkit-scrollbar-track {
            background: #000;
        }
        .game-container::-webkit-scrollbar-thumb {
            background: var(--blood-crimson);
        }

        .screen {
            display: none;
            animation: fadeIn 1.5s ease-in-out forwards;
        }

        .screen.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1 {
            font-family: 'Creepster', cursive;
            font-size: 3.5rem;
            color: var(--blood-crimson);
            text-align: center;
            letter-spacing: 3px;
            margin-bottom: 20px;
            text-shadow: 0 0 10px rgba(136, 8, 8, 0.8);
        }

        h2 {
            color: #d1c7a7;
            margin-bottom: 15px;
            border-bottom: 1px dashed var(--blood-crimson);
            padding-bottom: 5px;
        }

        p {
            line-height: 1.6;
            margin-bottom: 15px;
            font-size: 1.05rem;
        }

        /* Creepy Visual ASCII Art / Graphic frame placeholders */
        .scary-pic {
            width: 100%;
            height: 250px;
            background: #111;
            border: 1px solid #333;
            margin: 20px 0;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            font-family: monospace;
            color: rgba(136, 8, 8, 0.7);
            white-space: pre;
            font-size: 8px;
            overflow: hidden;
            box-shadow: inset 0 0 50px #000;
        }

        .btn {
            background: transparent;
            color: var(--corpse-pale);
            border: 1px solid var(--blood-crimson);
            padding: 12px 24px;
            font-family: 'Special Elite', monospace;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            display: block;
            margin: 20px auto;
            text-transform: uppercase;
            box-shadow: 0 0 5px rgba(136, 8, 8, 0.2);
        }

        .btn:hover {
            background: var(--blood-crimson);
            color: #fff;
            box-shadow: 0 0 15px var(--blood-crimson);
            text-shadow: 0 0 5px #000;
        }

        input[type="text"] {
            background: #000;
            border: 1px solid var(--moss-green);
            color: var(--neon-glow);
            padding: 10px;
            width: 100%;
            font-family: 'Special Elite', monospace;
            font-size: 1.2rem;
            text-align: center;
            margin-top: 15px;
        }

        input[type="text"]:focus {
            outline: none;
            border-color: var(--blood-crimson);
            box-shadow: 0 0 10px rgba(136, 8, 8, 0.5);
        }

        /* Clue Box Mechanics */
        .clue-box {
            background: rgba(0, 0, 0, 0.6);
            border-left: 4px solid var(--neon-glow);
            padding: 15px;
            margin: 15px 0;
            display: none;
        }

        .clue-box.visible {
            display: block;
            animation: glitchEffect 0.5s ease;
        }

        @keyframes glitchEffect {
            0% { transform: skewX(-5deg); opacity: 0.5; }
            50% { transform: skewX(5deg); opacity: 0.8; }
            100% { transform: skewX(0deg); opacity: 1; }
        }

        /* Puzzle inputs */
        .puzzle-input-group {
            margin: 15px 0;
            padding: 10px;
            border: 1px solid #222;
            background: rgba(5,5,5,0.5);
        }

        /* Final suspects selection styles */
        .suspect-option {
            background: #141a14;
            border: 1px solid var(--moss-green);
            padding: 15px;
            margin: 10px 0;
            cursor: pointer;
            transition: 0.2s;
        }

        .suspect-option:hover {
            border-color: var(--blood-crimson);
            background: #1a1010;
        }

        .suspect-option.selected {
            border-color: var(--neon-glow);
            background: #0d250f;
        }

        .error-msg {
            color: var(--blood-crimson);
            font-size: 0.9rem;
            text-align: center;
            margin-top: 5px;
            display: none;
        }
    </style>
</head>
<body>

    <div class="vignette"></div>
    <div class="scanlines"></div>

    <div class="game-container">
        
        <!-- SCREEN 1: START & AUDIO TRIGGER -->
        <div id="screen-start" class="screen active">
            <h1>BLACKWOOD FOG</h1>
            <div class="scary-pic">
     /\/\/\_    /\_/\/\/\    _/\/\/\/\     _/\/\/\_
    /      \  /         \  /          \   /       \
   /  /\/\  \/   /\_/\   \/   /\/\/\   \ /  /\/\   \
  /  /    \     /     \      /      \      /    \   \
 /  /      \___/       \____/        \____/      \   \
||          ||          ||            ||          ||  ||
||   ,,     ||   ,,     ||    ,,      ||   ,,     ||  ||
| \  ||  /| | \  ||  /| | \   ||   /| | \  ||  /| | / |
    [ NIGHTMARE FOREST REALM - CASE FILE #0666 ]
            </div>
            <p><strong>WARNING:</strong> This investigation contains highly unsettling atmosphere. Enter at your own peril. Turn your sound up to experience the background frequency of the woods.</p>
            <button class="btn" onclick="initGame()">Initialize Investigation</button>
        </div>

        <!-- SCREEN 2: THE INTRODUCTION & NAME INPUT -->
        <div id="screen-intro" class="screen">
            <h2>The Briefing</h2>
            <p>It is 3:14 AM. The rain striking the canopy of Blackwood Forest sounds like gravel thrown against a coffin. You were summoned here by an anonymous telegraph, but upon arrival, you find nothing but an abandoned cabin covered in twisting roots and a terrifying sequence of blood-stained notes.</p>
            <p>You pull out your badge. You are the Lead Occult Detective on this grid.</p>
            
            <div style="margin: 30px 0;">
                <label for="player-name">IDENTIFY YOURSELF, DETECTIVE:</label>
                <input type="text" id="player-name" placeholder="Enter Surname..." autocomplete="off">
                <span id="name-error" class="error-msg">You must provide a name to proceed.</span>
            </div>
            <button class="btn" onclick="saveName()">Commit Name & Open Log</button>
        </div>

        <!-- SCREEN 3: MULTI-STEP INVESTIGATION (CLUES & HARD PUZZLES) -->
        <div id="screen-investigation" class="screen">
            <h2>Case File Log: Detective <span class="detective-name-placeholder" style="color: var(--neon-glow);"></span></h2>
            <p>You step deeper into the fog. The floorboards of the cabin groan. Below your boots, the evidence reveals itself piece by piece. Work meticulously; one false deduction will trap you in this nightmare permanently.</p>

            <!-- CLUE 1 -->
            <div id="clue-1" class="clue-box visible">
                <h3>Clue #1: The Blood-Stained Diary</h3>
                <p>A diary entry from <em>Dr. Alistair Finch</em>, the missing occult researcher. It reads: <em>"The entity doesn't take your life; it swaps the vessel. I am no longer looking at my reflection. I am looking at my killer looking out."</em></p>
                <p><strong>The Cipher Lock:</strong> Dr. Finch left a safety passcode to decode his notes. The hint says: <em>"Count the letters of the forest's primary sin, multiplied by the hour of the dead."</em> (Sin = MURDER, Hour = 3AM).</p>
                <div class="puzzle-input-group">
                    <label>Enter Digital Code:</label>
                    <input type="text" id="puzzle-1" placeholder="Type answer...">
                    <span id="p1-error" class="error-msg">The lock clicks shut tighter. Incorrect.</span>
                </div>
                <button class="btn" onclick="checkPuzzle1()">Crack Cipher</button>
            </div>

            <!-- CLUE 2 -->
            <div id="clue-2" class="clue-box">
                <h3>Clue #2: The Audio Recorder</h3>
                <p>You find an old tape player spinning spinning backwards. You flip the switch. You hear Dr. Finch's manic voice: <em>"The one who died first wasn't the one buried in the dirt. Look at the dental records! The skeleton under the floorboards has a gold crown on the lower left molar. But I remember... I had that crown put in last year. Wait, then whose body is beneath me?!"</em></p>
                <button class="btn" onclick="revealClue(3)">Analyze Next Clue</button>
            </div>

            <!-- CLUE 3 -->
            <div id="clue-3" class="clue-box">
                <h3>Clue #3: The Ritual Altar</h3>
                <p>In the center of the room is a rough stone altar. Three names are carved into it, but one has been violently gouged out with a knife. The surviving names are: <strong>Alistair Finch</strong> and <strong>The Stranger</strong>.</p>
                <p>Beside it lies a riddle: <em>"I have no flesh, no bounds, no bone, yet I mimic your voice when you are alone. I am born when you speak, but die when you flee. What am I?"</em></p>
                <div class="puzzle-input-group">
                    <label>Solve the Altar's Curse (One Word):</label>
                    <input type="text" id="puzzle-3" placeholder="Type answer...">
                    <span id="p3-error" class="error-msg">A cold breeze chills your neck. Wrong.</span>
                </div>
                <button class="btn" onclick="checkPuzzle3()">Speak Word</button>
            </div>

            <!-- CLUE 4 -->
            <div id="clue-4" class="clue-box">
                <h3>Clue #4: The Torn Telegram</h3>
                <p>You piece together a scrap of paper found inside a lantern. It's a telegram sent *to* you, Detective <span class="detective-name-placeholder"></span>, dated *three days ago*. But you only received the call today.</p>
                <p>It reads: <em>"DON'T GO. THE APPOINTMENT WAS A TRAP. DETECTIVE <span class="detective-name-placeholder"></span> WAS REPORTED MISSING IN BLACKWOOD FOREST ONE WEEK AGO. IF YOU ARE READING THIS, YOU ARE ALREADY WITHIN THE ECHO."</em></p>
                <button class="btn" onclick="revealClue(5)">Process the Reality</button>
            </div>

            <!-- CLUE 5 -->
            <div id="clue-5" class="clue-box">
                <h3>Clue #5: The Mirror Room</h3>
                <p>You stumble into the back room. A massive, soot-stained mirror stands before you. You wipe away the ash. Your reflection isn't moving at pace with your hands. Instead, your reflection is standing perfectly still, holding an occult dagger, smiling maniacally back at you.</p>
                <p>Pinned to the mirror frame is the original missing person file. It lists the physical details of the victim: height, eye color, and clothes. They perfectly match everything you are wearing right now.</p>
                <button class="btn" onclick="goToAccusation()">Proceed to Final Deduction</button>
            </div>
        </div>

        <!-- SCREEN 4: THE TWIST DEDUCTION (WHO IS THE REAL VICTIM?) -->
        <div id="screen-deduction" class="screen">
            <h2>The Absolute Paradox</h2>
            <p>The clues lock together into a terrifying paradigm. This isn't a fresh crime scene. The forest is an loops-based trap. You look down at your hands; they are pale and slightly translucent. It's time to close the case file. </p>
            <p><strong>Detective <span class="detective-name-placeholder"></span>, look closely at the facts. Who is the REAL victim of this murder mystery?</strong></p>
            
            <div id="suspect-1" class="suspect-option" onclick="selectSuspect(1)">
                <strong>A) Dr. Alistair Finch</strong><br>
                <small>He was researching the entity and left the journals behind. Clearly, he was consumed by his own experiments.</small>
            </div>
            <div id="suspect-2" class="suspect-option" onclick="selectSuspect(2)">
                <strong>B) The Shape-shifting Stranger</strong><br>
                <small>The entity hidden in the woods that attempts to mimic humans but failed and got trapped here.</small>
            </div>
            <div id="suspect-3" class="suspect-option" onclick="selectSuspect(3)">
                <strong>C) You (Detective <span class="detective-name-placeholder"></span>)</strong><br>
                <small>You never actually accepted a live case. You died a week ago in these woods, and your ghost is endlessly repeating the investigation.</small>
            </div>

            <span id="deduction-error" class="error-msg">Select your target to seal the narrative.</span>
            <button class="btn" onclick="submitDeduction()">File Final Report</button>
        </div>

        <!-- SCREEN 5: THE RESOLUTION / OUTCOME -->
        <div id="screen-resolution" class="screen">
            <h1 id="ending-title">CASE CLOSURE</h1>
            <p id="ending-text"></p>
            <button class="btn" onclick="location.reload()">Re-Enter The Woods</button>
        </div>

    </div>

    <script>
        let audioCtx;
        let ambientDrone;
        let chosenSuspect = null;
        let playerName = "Unknown";

        // FUNCTION TO GENERATE PURE, CREEPY SYNTHESIZED SOUND VIA WEB AUDIO API
        // This skips the need to rely on external MP3 files that fail to load locally.
        function startSpookyAudio() {
            try {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                
                // Create a low unsettling master drone
                let oscillator1 = audioCtx.createOscillator();
                let oscillator2 = audioCtx.createOscillator();
                let biquadFilter = audioCtx.createBiquadFilter();
                let gainNode = audioCtx.createGain();

                oscillator1.type = 'sawtooth';
                oscillator1.frequency.setValueAtTime(55, audioCtx.currentTime); // Low A note
                
                oscillator2.type = 'sine';
                oscillator2.frequency.setValueAtTime(55.8, audioCtx.currentTime); // Detuned intentionally to create eerie friction beats

                biquadFilter.type = 'lowpass';
                biquadFilter.frequency.setValueAtTime(150, audioCtx.currentTime); // Muffled heavy sound

                gainNode.gain.setValueAtTime(0.15, audioCtx.currentTime); // Keep it ambient

                // Connect nodes
                oscillator1.connect(biquadFilter);
                oscillator2.connect(biquadFilter);
                biquadFilter.connect(gainNode);
                gainNode.connect(audioCtx.destination);

                oscillator1.start();
                oscillator2.start();

                // Periodic eerie sound spikes (mimicking distant wind or screams)
                setInterval(() => {
                    if(audioCtx.state === 'running') {
                        let spookOsc = audioCtx.createOscillator();
                        let spookGain = audioCtx.createGain();
                        
                        spookOsc.type = 'triangle';
                        spookOsc.frequency.setValueAtTime(120 + Math.random() * 80, audioCtx.currentTime);
                        spookOsc.frequency.exponentialRampToValueAtTime(300 + Math.random() * 200, audioCtx.currentTime + 3);
                        
                        spookGain.gain.setValueAtTime(0.0, audioCtx.currentTime);
                        spookGain.gain.linearRampToValueAtTime(0.03, audioCtx.currentTime + 1.5);
                        spookGain.gain.linearRampToValueAtTime(0.0, audioCtx.currentTime + 3);
                        
                        spookOsc.connect(spookGain);
                        spookGain.connect(audioCtx.destination);
                        spookOsc.start();
                        spookOsc.stop(audioCtx.currentTime + 3.1);
                    }
                }, 5000);

            } catch(e) {
                console.log("Audio framework context error: " + e);
            }
        }

        function switchScreen(currentId, nextId) {
            document.getElementById(currentId).classList.remove('active');
            document.getElementById(nextId).classList.add('active');
        }

        function initGame() {
            startSpookyAudio();
            switchScreen('screen-start', 'screen-intro');
        }

        function saveName() {
            const nameInput = document.getElementById('player-name').value.trim();
            if(!nameInput) {
                document.getElementById('name-error').style.display = 'block';
                return;
            }
            playerName = nameInput;
            
            // Populate all name placeholders
            const placeholders = document.querySelectorAll('.detective-name-placeholder');
            placeholders.forEach(el => el.textContent = playerName);

            switchScreen('screen-intro', 'screen-investigation');
        }

        // PUZZLE 1 CHECK: MURDER (6 letters) * 3AM = 18
        function checkPuzzle1() {
            const ans = document.getElementById('puzzle-1').value.trim();
            if(ans === "18") {
                document.getElementById('p1-error').style.display = 'none';
                revealClue(2);
            } else {
                document.getElementById('p1-error').style.display = 'block';
                playJumpscareClick();
            }
        }

        // PUZZLE 3 CHECK: An Echo
        function checkPuzzle3() {
            const ans = document.getElementById('puzzle-3').value.toLowerCase().trim();
            if(ans.includes("echo")) {
                document.getElementById('p3-error').style.display = 'none';
                revealClue(4);
            } else {
                document.getElementById('p3-error').style.display = 'block';
                playJumpscareClick();
            }
        }

        function revealClue(num) {
            document.getElementById(`clue-${num}`).classList.add('visible');
            // Scroll down automatically to reveal the element smoothly
            document.getElementById(`clue-${num}`).scrollIntoView({ behavior: 'smooth' });
        }

        function goToAccusation() {
            switchScreen('screen-investigation', 'screen-deduction');
        }

        function selectSuspect(num) {
            chosenSuspect = num;
            // Clear prior selection treatments
            for(let i=1; i<=3; i++) {
                document.getElementById(`suspect-${i}`).classList.remove('selected');
            }
            document.getElementById(`suspect-${num}`).classList.add('selected');
        }

        function submitDeduction() {
            if(!chosenSuspect) {
                document.getElementById('deduction-error').style.display = 'block';
                return;
            }
            
            let title = "";
            let text = "";

            if(chosenSuspect === 3) {
                title = "PARADOX SOLVED: SELF-REALIZATION";
                text = `Correct, Detective ${playerName}. The realization hits you like physical weight. The skeleton beneath the floor boards wearing your exact ring, the telegram, the delayed timelines... you didn't step into a case file. You step inside your own tomb. You died in Blackwood Forest exactly seven days ago. Your desperate psyche generated this simulation to comprehend its murder. As the case logs snap shut, the cabin mirrors shatter, and you finally rest in peace.`;
            } else {
                title = "TRAPPED IN THE ECHO";
                text = `Incorrect, Detective ${playerName}. You point your finger at someone else, trying to blame external factors. Suddenly, your reflection inside the mirror reaches through the glass pane, wrapping cold dead fingers around your throat. As you lose consciousness, you look beneath the couch to see your own dead eyes staring back. You failed to parse the reality, and your spirit is reset to 3:14 AM to live through this nightmare forest again...`;
            }

            document.getElementById('ending-title').textContent = title;
            document.getElementById('ending-text').textContent = text;
            switchScreen('screen-deduction', 'screen-resolution');
        }

        // Little auditory spike if they get answers wrong
        function playJumpscareClick() {
            if(!audioCtx) return;
            let osc = audioCtx.createOscillator();
            let gain = audioCtx.createGain();
            osc.type = 'sawtooth';
            osc.frequency.setValueAtTime(130, audioCtx.currentTime);
            osc.frequency.linearRampToValueAtTime(30, audioCtx.currentTime + 0.4);
            gain.gain.setValueAtTime(0.3, audioCtx.currentTime);
            gain.gain.linearRampToValueAtTime(0.01, audioCtx.currentTime + 0.4);
            osc.connect(gain);
            gain.connect(audioCtx.destination);
            osc.start();
            osc.stop(audioCtx.currentTime + 0.45);
        }
    </script>
</body>
</html>
