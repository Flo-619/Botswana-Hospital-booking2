<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <meta name="description" content="Botswana Hospital Queue Booking - Fully accessible with on-screen keyboard for blind users, offline-ready, bilingual support">
    <meta name="theme-color" content="#0a2f44">
    <title>Botswana hospital queue booking | Accessible Health Queue System</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0d9488;
            --primary-dark: #0f766e;
            --primary-glow: #5eead4;
            --bg-dark: #0a0f1f;
            --card-glass: rgba(18, 25, 45, 0.85);
            --text-light: #f1f5f9;
            --text-muted: #cbd5e1;
            --accent-gold: #fbbf24;
            --error: #ef4444;
        }

        body {
            font-family: 'Inter', 'Poppins', system-ui, -apple-system, sans-serif;
            background: radial-gradient(ellipse at 30% 40%, #0f172a, #030712);
            min-height: 100vh;
            padding: 20px 18px 48px;
            color: var(--text-light);
        }

        /* High contrast focus for accessibility */
        *:focus {
            outline: 3px solid var(--accent-gold);
            outline-offset: 3px;
        }

        .bg-orb {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 0;
        }
        .bg-orb::before {
            content: '';
            position: absolute;
            top: -20%;
            left: -10%;
            width: 70%;
            height: 70%;
            background: radial-gradient(circle, rgba(13,148,136,0.15) 0%, transparent 70%);
            animation: float1 20s infinite alternate;
        }
        @keyframes float1 { 0% { transform: translate(0,0) scale(1); } 100% { transform: translate(5%,8%) scale(1.2); } }

        .app-container {
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        /* Glass Header */
        .glass-header {
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(16px);
            border-radius: 2rem;
            padding: 1.4rem 2rem;
            margin-bottom: 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
            border: 1px solid rgba(94, 234, 212, 0.25);
        }
        .brand h1 {
            font-size: 1.7rem;
            background: linear-gradient(135deg, #fff, var(--primary-glow));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .brand p { font-size: 0.75rem; color: var(--text-muted); }
        .toolbar { display: flex; gap: 10px; flex-wrap: wrap; }
        .pill-btn {
            background: rgba(255,255,255,0.05);
            border: 1px solid rgba(94,234,212,0.3);
            padding: 8px 20px;
            border-radius: 40px;
            font-size: 0.8rem;
            font-weight: 500;
            cursor: pointer;
            color: var(--text-light);
            transition: 0.2s;
        }
        .pill-btn:hover { background: rgba(13,148,136,0.3); transform: translateY(-1px); }
        .pill-btn.active { background: var(--primary); border-color: var(--primary-glow); box-shadow: 0 0 10px var(--primary-glow); }

        /* Emergency Banner */
        .emergency-banner {
            background: rgba(239,68,68,0.12);
            backdrop-filter: blur(12px);
            border-left: 5px solid var(--error);
            border-radius: 1.5rem;
            padding: 1rem 1.5rem;
            margin-bottom: 2rem;
            display: flex;
            align-items: center;
            gap: 12px;
            font-weight: 500;
        }

        /* Grid Layout */
        .grid-3col {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
            gap: 1.8rem;
            margin-bottom: 2rem;
        }

        /* Cards */
        .neo-card {
            background: var(--card-glass);
            backdrop-filter: blur(16px);
            border-radius: 2rem;
            border: 1px solid rgba(94, 234, 212, 0.2);
            overflow: hidden;
            transition: transform 0.2s, box-shadow 0.3s;
        }
        .neo-card:hover { transform: translateY(-3px); border-color: var(--primary-glow); }
        .card-header {
            padding: 1.2rem 1.8rem;
            border-bottom: 1px solid rgba(94,234,212,0.2);
            background: rgba(0,0,0,0.2);
        }
        .card-header h2 { font-size: 1.3rem; display: flex; align-items: center; gap: 8px; color: var(--primary-glow); }
        .card-body { padding: 1.5rem; }

        .input-field { margin-bottom: 1.2rem; }
        .input-field label { display: block; font-size: 0.75rem; font-weight: 600; margin-bottom: 6px; color: var(--text-muted); letter-spacing: 0.3px; }
        .input-field input, .input-field select, .input-field textarea {
            width: 100%;
            padding: 12px 16px;
            background: rgba(0,0,0,0.6);
            border: 1px solid rgba(94,234,212,0.35);
            border-radius: 1.25rem;
            color: var(--text-light);
            font-size: 0.95rem;
            transition: 0.2s;
        }
        .input-field input:focus, .input-field select:focus, .input-field textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(13,148,136,0.2);
        }
        button {
            width: 100%;
            padding: 12px;
            border-radius: 2rem;
            font-weight: 700;
            border: none;
            cursor: pointer;
            background: linear-gradient(105deg, var(--primary-dark), var(--primary));
            color: white;
            transition: 0.2s;
        }
        button:hover { transform: scale(0.98); box-shadow: 0 0 12px var(--primary-glow); }

        /* ON-SCREEN KEYBOARD FOR BLIND USERS */
        .onscreen-keyboard {
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(12px);
            border-radius: 1.5rem;
            padding: 1rem;
            margin-top: 1rem;
            border: 1px solid var(--primary-glow);
        }
        .keyboard-row {
            display: flex;
            justify-content: center;
            gap: 6px;
            margin-bottom: 8px;
            flex-wrap: wrap;
        }
        .key-btn {
            background: #1e293b;
            border: 1px solid var(--primary-glow);
            color: white;
            width: 48px;
            height: 48px;
            border-radius: 14px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: 0.1s;
            box-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }
        .key-btn.special {
            background: #334155;
            width: auto;
            padding: 0 16px;
        }
        .key-btn.space {
            width: 220px;
        }
        .key-btn:hover, .key-btn:focus {
            background: var(--primary);
            transform: scale(1.02);
            outline: 2px solid var(--accent-gold);
        }
        .keyboard-toggle {
            background: #334155;
            margin-bottom: 12px;
            font-size: 0.85rem;
        }

        .queue-item {
            background: rgba(0,0,0,0.4);
            border-radius: 1.2rem;
            padding: 0.8rem;
            margin-bottom: 0.6rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
            border: 1px solid rgba(94,234,212,0.15);
        }
        .queue-number {
            background: var(--primary);
            width: 42px;
            height: 42px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 60px;
            font-weight: 800;
        }
        .serve-small { width: auto; background: var(--accent-gold); padding: 6px 18px; font-size: 0.7rem; color: #1e293b; }
        .feedback-toast {
            margin-top: 1rem;
            padding: 12px;
            border-radius: 1rem;
            display: none;
            background: rgba(0,0,0,0.7);
            backdrop-filter: blur(8px);
            border-left: 4px solid var(--primary);
            font-size: 0.85rem;
        }
        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0,0,0,0);
            border: 0;
        }
        .accessibility-note {
            font-size: 0.7rem;
            text-align: center;
            margin-top: 12px;
            color: var(--text-muted);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
        }
        footer { text-align: center; font-size: 0.7rem; margin-top: 2rem; color: var(--text-muted); padding: 1rem; }
        
        @media (max-width: 700px) {
            .glass-header { flex-direction: column; text-align: center; }
            .key-btn { width: 40px; height: 40px; font-size: 0.9rem; }
            .key-btn.space { width: 140px; }
            .queue-item { flex-direction: column; align-items: stretch; }
            .serve-small { width: 100%; }
        }
    </style>
</head>
<body>
<div class="bg-orb"></div>
<div class="app-container">
    <!-- Header -->
    <div class="glass-header">
        <div class="brand">
            <h1>🇧🇼 Botswana hospital queue booking</h1>
            <p id="taglineText">Accessible • On-Screen Keyboard • Offline-Ready • Bilingual</p>
        </div>
        <div class="toolbar">
            <button class="pill-btn" id="fontUp" aria-label="Increase font size">🔍 A+</button>
            <button class="pill-btn" id="fontDown" aria-label="Decrease font size">🔍 A-</button>
            <button class="pill-btn" id="contrastBtn" aria-label="Toggle high contrast">🌓 Contrast</button>
            <button class="pill-btn active" id="langEn" aria-label="Switch to English">English</button>
            <button class="pill-btn" id="langTs" aria-label="Switch to Setswana">Setswana</button>
        </div>
    </div>

    <!-- Emergency Banner -->
    <div class="emergency-banner">
        <span>🚨</span> <span id="emergencyMsg">Emergency: 997 (Ambulance) / 998 (Police) — Free from any phone</span>
    </div>

    <!-- 3 Column Grid: Booking, Symptoms, On-Screen Keyboard -->
    <div class="grid-3col">
        <!-- Booking Card -->
        <div class="neo-card">
            <div class="card-header"><h2>📋 <span id="bookingTitle">Smart Queue Registration</span></h2></div>
            <div class="card-body">
                <div class="input-field">
                    <label id="nameLabel">Full Name *</label>
                    <input type="text" id="fullName" placeholder="e.g. Amantle Raditladi" aria-label="Full name" autocomplete="off">
                </div>
                <div class="input-field">
                    <label id="omangLabel">Omang (National ID) *</label>
                    <input type="text" id="omangId" placeholder="e.g. 10123456789" aria-label="Omang ID" autocomplete="off">
                </div>
                <div class="input-field">
                    <label id="hospitalLabel">Select Hospital *</label>
                    <select id="hospitalSelect" aria-label="Select hospital">
                        <option value="">-- Choose Hospital --</option>
                        <option>Princess Marina Hospital</option>
                        <option>Nyangabgwe Referral Hospital</option>
                        <option>Molepolole DHMT</option>
                        <option>Mochudi Hospital</option>
                        <option>Ghanzi Primary Hospital</option>
                    </select>
                </div>
                <div class="input-field">
                    <label id="reasonLabel">Reason for Visit *</label>
                    <input type="text" id="visitReason" placeholder="e.g. fever, chest pain, check-up" aria-label="Reason for visit" autocomplete="off">
                </div>
                <button id="bookBtn">✨ <span id="bookText">Join Queue (Offline Safe)</span></button>
                <div id="bookingToast" class="feedback-toast"></div>
            </div>
        </div>

        <!-- Symptom Checker Card (No Voice) -->
        <div class="neo-card">
            <div class="card-header"><h2>🩺 <span id="symptomTitle">Symptom Checker & AI Referral</span></h2></div>
            <div class="card-body">
                <div class="input-field">
                    <label id="symptomsLabel">Describe your symptoms (English / Setswana)</label>
                    <textarea id="symptomInput" rows="4" placeholder="Example: severe headache, chest tightness, fever with cough...&#10;Sekao: tlhogo e botlhoko, mogote, kgwa..." aria-label="Symptoms description"></textarea>
                </div>
                <button id="getAIBtn">🧠 <span id="aiBtnText">Get AI Health Recommendation & Referral</span></button>
                <div id="aiToast" class="feedback-toast"></div>
                <div class="accessibility-note">
                    <span>💡 Tip: Use the on-screen keyboard to type</span>
                </div>
            </div>
        </div>

        <!-- ON-SCREEN KEYBOARD CARD FOR BLIND/LOW-VISION USERS -->
        <div class="neo-card">
            <div class="card-header"><h2>⌨️ <span id="keyboardTitle">Accessible On-Screen Keyboard</span></h2></div>
            <div class="card-body">
                <button id="toggleKeyboardBtn" class="keyboard-toggle">🎹 <span id="toggleKeyboardText">Show Keyboard</span></button>
                <div id="onscreenKeyboard" style="display: none;">
                    <div class="onscreen-keyboard">
                        <!-- Row 1: Numbers -->
                        <div class="keyboard-row">
                            <button class="key-btn" data-key="1" aria-label="1">1</button>
                            <button class="key-btn" data-key="2" aria-label="2">2</button>
                            <button class="key-btn" data-key="3" aria-label="3">3</button>
                            <button class="key-btn" data-key="4" aria-label="4">4</button>
                            <button class="key-btn" data-key="5" aria-label="5">5</button>
                            <button class="key-btn" data-key="6" aria-label="6">6</button>
                            <button class="key-btn" data-key="7" aria-label="7">7</button>
                            <button class="key-btn" data-key="8" aria-label="8">8</button>
                            <button class="key-btn" data-key="9" aria-label="9">9</button>
                            <button class="key-btn" data-key="0" aria-label="0">0</button>
                        </div>
                        <!-- Row 2: QWERTYUIOP -->
                        <div class="keyboard-row">
                            <button class="key-btn" data-key="q">q</button><button class="key-btn" data-key="w">w</button>
                            <button class="key-btn" data-key="e">e</button><button class="key-btn" data-key="r">r</button>
                            <button class="key-btn" data-key="t">t</button><button class="key-btn" data-key="y">y</button>
                            <button class="key-btn" data-key="u">u</button><button class="key-btn" data-key="i">i</button>
                            <button class="key-btn" data-key="o">o</button><button class="key-btn" data-key="p">p</button>
                        </div>
                        <!-- Row 3: ASDFGHJKL -->
                        <div class="keyboard-row">
                            <button class="key-btn" data-key="a">a</button><button class="key-btn" data-key="s">s</button>
                            <button class="key-btn" data-key="d">d</button><button class="key-btn" data-key="f">f</button>
                            <button class="key-btn" data-key="g">g</button><button class="key-btn" data-key="h">h</button>
                            <button class="key-btn" data-key="j">j</button><button class="key-btn" data-key="k">k</button>
                            <button class="key-btn" data-key="l">l</button>
                        </div>
                        <!-- Row 4: ZXCVBNM -->
                        <div class="keyboard-row">
                            <button class="key-btn" data-key="z">z</button><button class="key-btn" data-key="x">x</button>
                            <button class="key-btn" data-key="c">c</button><button class="key-btn" data-key="v">v</button>
                            <button class="key-btn" data-key="b">b</button><button class="key-btn" data-key="n">n</button>
                            <button class="key-btn" data-key="m">m</button>
                        </div>
                        <!-- Row 5: Special keys -->
                        <div class="keyboard-row">
                            <button class="key-btn special" data-key="space">␣ Space</button>
                            <button class="key-btn special" data-key="backspace">⌫ Backspace</button>
                            <button class="key-btn special" data-key="clear">🗑 Clear All</button>
                        </div>
                        <div class="keyboard-row">
                            <button class="key-btn special" data-key="tab">↹ Tab (Next Field)</button>
                            <button class="key-btn special" data-key="enter">⏎ Enter (New Line)</button>
                        </div>
                    </div>
                    <p style="font-size:0.65rem; text-align:center; margin-top:10px; color:var(--text-muted);">
                        🔹 Click any input field first, then use keyboard buttons 🔹
                    </p>
                </div>
                <div class="accessibility-note" style="margin-top: 12px;">
                    <span>♿ Screen reader compatible</span>
                    <span>⌨️ Large tactile buttons</span>
                    <span>📱 Works on any device</span>
                </div>
            </div>
        </div>
    </div>

    <!-- Live Queue Board -->
    <div class="neo-card">
        <div class="card-header"><h2>📊 <span id="queueBoardTitle">Active Patient Queue</span> <span id="queueCounter" style="font-size:0.7rem; background:rgba(0,0,0,0.4); padding:4px 14px; border-radius:40px; margin-left:10px;"></span></h2></div>
        <div class="card-body">
            <div id="queueListContainer" style="max-height: 360px; overflow-y: auto;">
                <div id="emptyQueueMsg" style="padding: 30px; text-align: center; color: var(--text-muted);">✨ Loading queue...</div>
            </div>
            <div id="offlineStatus" style="font-size:0.7rem; text-align:center; margin-top:14px; color: var(--text-muted);">📡 Offline-capable | Queue saved locally on your device</div>
        </div>
    </div>
    <footer>⚕️ Botswana Ministry of Health | Fully Accessible: On-Screen Keyboard + Screen Reader + High Contrast + Offline Ready</footer>
</div>

<script>
    // ======================== BILINGUAL DICTIONARY ========================
    const langRes = {
        en: {
            tagline: "Accessible • On-Screen Keyboard • Offline-Ready • Bilingual",
            emergencyMsg: "Emergency: 997 (Ambulance) / 998 (Police) — Free from any phone",
            bookingTitle: "Smart Queue Registration",
            nameLabel: "Full Name *", omangLabel: "Omang (National ID) *", hospitalLabel: "Select Hospital *", reasonLabel: "Reason for Visit *",
            bookText: "Join Queue (Offline Safe)", symptomTitle: "Symptom Checker & AI Referral",
            symptomsLabel: "Describe your symptoms (English / Setswana)", aiBtnText: "Get AI Health Recommendation & Referral",
            queueBoardTitle: "Active Patient Queue", keyboardTitle: "Accessible On-Screen Keyboard",
            toggleKeyboardText: "Show Keyboard", hideKeyboardText: "Hide Keyboard",
            emptyQueue: "✨ No active queue — Book your spot above ✨",
            bookSuccess: (n,p,h) => `✅ ${n}, you are #${p} at ${h}. Queue saved offline.`,
            serveConfirm: "✅ Patient marked as served. Queue updated.",
            fillFields: "Please fill all booking fields (Name, Omang, Hospital, Reason).",
            omangInvalid: "Omang must be 5-20 letters/numbers only.",
            symptomEmpty: "Please describe your symptoms to receive AI recommendation.",
            aiChest: "⚠️ CRITICAL REFERRAL: Possible heart attack. Call 997 immediately. Emergency cardiac workup needed.",
            aiBreathing: "🚨 REFERRAL: Respiratory distress. Priority admission. Oxygen therapy required.",
            aiStroke: "⚠️ STROKE ALERT: Call 997. Golden hour. Immediate CT angiography.",
            aiHeadache: "🏥 REFERRAL: Severe headache with vision changes. BP monitoring + neuro exam. Visit ER.",
            aiFeverRash: "🩺 REFERRAL: Fever with rash — possible meningitis/measles. Isolation. Urgent clinic.",
            aiBlood: "🔴 REFERRAL: Blood in stool. Urgent colonoscopy. Hospital admission.",
            aiGeneral: "📋 GENERAL ADVICE: Rest, hydrate, monitor for 24h. If worsening, visit primary clinic."
        },
        ts: {
            tagline: "Phihlelelo • Khiboto ya skirini • E bereka ntle le inthanete • Dipuo tse pedi",
            emergencyMsg: "Tshoganetso: 997 (Ambulense) / 998 (Mapodise) — Mahala",
            bookingTitle: "Kwala Nako ya Sepatela",
            nameLabel: "Leina le le tletseng *", omangLabel: "Omang (ID) *", hospitalLabel: "Tlhopa Sepatela *", reasonLabel: "Lebaka la go etela *",
            bookText: "Tsena mo Meleng (Offline)", symptomTitle: "Tlhathollo ya Matshwao le Kaelo ya AI",
            symptomsLabel: "Tlhalosa matshwao a gago (Setswana / English)", aiBtnText: "Bona Keletso le Kaelo ya AI",
            queueBoardTitle: "Ba Emeletseng mo Meleng", keyboardTitle: "Khiboto ya Skirini e Bonolo",
            toggleKeyboardText: "Bontsha Khiboto", hideKeyboardText: "Tlhama Khiboto",
            emptyQueue: "✨ Ga go na ba e emetseng — Kwala nako kwa godimo ✨",
            bookSuccess: (n,p,h) => `✅ ${n}, o mo maemong a #${p} kwa ${h}. E bolokilwe offline.`,
            serveConfirm: "✅ Mokudi o alafiwa. Mela e tlhophafaditswe.",
            fillFields: "Tsweetswee tlatsa makgetlo otlhe (Leina, Omang, Sepatela, Lebaka).",
            omangInvalid: "Omang e tshwanetse go nna ditlhaka/dinomoro tse 5-20.",
            symptomEmpty: "Tsweetswee tlhalosa matshwao gore AI e go fe kaelo.",
            aiChest: "⚠️ KAELO E MASISI: Bothata jwa pelo. Itsanapelela 997. Tlhatlhobo ya pelo ka bonako.",
            aiBreathing: "🚨 KAELO: Bothata jwa phefumololo. Kena sepatela. Okesejene e a tlhokega.",
            aiStroke: "⚠️ TLHAKGOLO: Itsanapelela 997. Tlhathollo ya CT ka bonako.",
            aiHeadache: "🏥 KAELO: Tlhogo e botlhoko le pono. Etela emergensi. Tlhatlhobo ya kgatelelo.",
            aiFeverRash: "🩺 KAELO: Mogote le lepodile — Ikaroganye, etela kliniki ka bonako.",
            aiBlood: "🔴 KAELO: Madi mantle. Ya kwa sepateleng. Tlhatlhobo ya colonoscopy.",
            aiGeneral: "📋 KELELO: Ikhutse, nwa metsi. Fa go oketsega, etela kliniki."
        }
    };

    let currentLang = "en";
    let queueDB = [];
    let activeInputElement = null;

    // UI Language Update
    function updateUI() {
        const t = langRes[currentLang];
        document.getElementById("taglineText").innerText = t.tagline;
        document.getElementById("emergencyMsg").innerText = t.emergencyMsg;
        document.getElementById("bookingTitle").innerText = t.bookingTitle;
        document.getElementById("nameLabel").innerText = t.nameLabel;
        document.getElementById("omangLabel").innerText = t.omangLabel;
        document.getElementById("hospitalLabel").innerText = t.hospitalLabel;
        document.getElementById("reasonLabel").innerText = t.reasonLabel;
        document.getElementById("bookText").innerText = t.bookText;
        document.getElementById("symptomTitle").innerText = t.symptomTitle;
        document.getElementById("symptomsLabel").innerText = t.symptomsLabel;
        document.getElementById("aiBtnText").innerText = t.aiBtnText;
        document.getElementById("queueBoardTitle").innerText = t.queueBoardTitle;
        document.getElementById("keyboardTitle").innerText = t.keyboardTitle;
        let toggleSpan = document.getElementById("toggleKeyboardText");
        if(toggleSpan && document.getElementById("onscreenKeyboard")) {
            toggleSpan.innerText = document.getElementById("onscreenKeyboard").style.display === "none" ? t.toggleKeyboardText : t.hideKeyboardText;
        }
        if(currentLang === "en") {
            document.getElementById("langEn").classList.add("active");
            document.getElementById("langTs").classList.remove("active");
        } else {
            document.getElementById("langTs").classList.add("active");
            document.getElementById("langEn").classList.remove("active");
        }
        renderQueue();
    }

    // Queue Management (Offline Persistence)
    function saveQueue() { localStorage.setItem("bw_accessible_queue", JSON.stringify(queueDB)); }
    function loadQueue() {
        const stored = localStorage.getItem("bw_accessible_queue");
        queueDB = (stored && stored !== "[]") ? JSON.parse(stored) : [];
        renderQueue();
    }
    function renderQueue() {
        const container = document.getElementById("queueListContainer");
        const counterSpan = document.getElementById("queueCounter");
        const t = langRes[currentLang];
        if(!queueDB.length) {
            container.innerHTML = `<div style="padding:30px;text-align:center;color:var(--text-muted);">${t.emptyQueue}</div>`;
            if(counterSpan) counterSpan.innerText = "";
            return;
        }
        let html = "";
        queueDB.forEach((item, idx) => {
            html += `<div class="queue-item">
                        <div style="display:flex; align-items:center; gap:12px; flex-wrap:wrap;">
                            <span class="queue-number">${idx+1}</span>
                            <div><strong>${escapeHtml(item.name)}</strong><br><span style="font-size:0.7rem;">🏥 ${escapeHtml(item.hospital)} — ${escapeHtml(item.reason)}</span></div>
                            <button class="serve-small" onclick="servePatient('${item.id}')">✅ ${currentLang === "en" ? "Serve Patient" : "Alafa Mokudi"}</button>
                        </div>
                    </div>`;
        });
        container.innerHTML = html;
        if(counterSpan) counterSpan.innerText = `${queueDB.length} ${currentLang === "en" ? "waiting" : "ba emetse"}`;
    }
    function escapeHtml(str) { if(!str) return ''; return str.replace(/[&<>]/g, m => ({'&':'&amp;','<':'&lt;','>':'&gt;'})[m]); }
    window.servePatient = function(id) {
        queueDB = queueDB.filter(p => p.id !== id);
        saveQueue();
        renderQueue();
        showToast("bookingToast", langRes[currentLang].serveConfirm, "#0d9488");
    };
    function showToast(elId, msg, colorHint) {
        const el = document.getElementById(elId);
        if(el) { el.innerText = msg; el.style.display = "block"; el.style.borderLeftColor = colorHint; setTimeout(() => el.style.display = "none", 4500); }
    }

    // Book Queue Button
    document.getElementById("bookBtn").addEventListener("click", () => {
        const name = document.getElementById("fullName").value.trim();
        const omang = document.getElementById("omangId").value.trim();
        const hospital = document.getElementById("hospitalSelect").value;
        const reason = document.getElementById("visitReason").value.trim();
        const t = langRes[currentLang];
        if(!name || !omang || !hospital || !reason) { alert(t.fillFields); return; }
        if(omang.length < 5 || !/^[A-Za-z0-9]+$/.test(omang)) { alert(t.omangInvalid); return; }
        const newPatient = { id: Date.now()+"-"+Math.random(), name, omang, hospital, reason, ts: Date.now() };
        queueDB.push(newPatient);
        saveQueue();
        renderQueue();
        showToast("bookingToast", t.bookSuccess(name, queueDB.length, hospital), "#14b8a6");
        document.getElementById("fullName").value = "";
        document.getElementById("omangId").value = "";
        document.getElementById("visitReason").value = "";
        document.getElementById("hospitalSelect").value = "";
    });

    // ================ AI SYMPTOM DIAGNOSIS & REFERRAL ================
    function getAIDiagnosis(symptomText, lang) {
        const txt = symptomText.toLowerCase();
        const t = langRes[lang];
        if(txt.includes("chest pain") || txt.includes("botlhoko mo sefubeng") || (txt.includes("chest") && txt.includes("tight"))) return t.aiChest;
        if(txt.includes("difficulty breathing") || txt.includes("shortness") || txt.includes("go hema ka thata")) return t.aiBreathing;
        if(txt.includes("stroke") || (txt.includes("face") && txt.includes("drooping")) || txt.includes("arm weakness")) return t.aiStroke;
        if((txt.includes("severe headache") || txt.includes("tlhogo e botlhoko")) && (txt.includes("vision") || txt.includes("vomiting"))) return t.aiHeadache;
        if(txt.includes("fever") && txt.includes("rash") || (txt.includes("mogote") && txt.includes("lepodile"))) return t.aiFeverRash;
        if(txt.includes("blood in stool") || txt.includes("madi mantle")) return t.aiBlood;
        return t.aiGeneral;
    }

    document.getElementById("getAIBtn").addEventListener("click", () => {
        const symptoms = document.getElementById("symptomInput").value.trim();
        const t = langRes[currentLang];
        if(!symptoms) { alert(t.symptomEmpty); return; }
        const advice = getAIDiagnosis(symptoms, currentLang);
        const aiDiv = document.getElementById("aiToast");
        aiDiv.innerHTML = `<strong>🧠 ${currentLang === "en" ? "AI HEALTH RECOMMENDATION" : "KELELO YA BOITEKANELO"}</strong><br><br>${advice}`;
        aiDiv.style.display = "block";
        aiDiv.style.borderLeftColor = "#f59e0b";
        setTimeout(() => { if(aiDiv.style.display === "block") aiDiv.style.display = "none"; }, 8000);
    });

    // ================ ON-SCREEN KEYBOARD FOR BLIND USERS ================
    const keyboardDiv = document.getElementById("onscreenKeyboard");
    const toggleBtn = document.getElementById("toggleKeyboardBtn");
    const toggleTextSpan = document.getElementById("toggleKeyboardText");
    const inputFields = ['fullName', 'omangId', 'visitReason', 'symptomInput'];
    
    // Track which input is focused
    inputFields.forEach(id => {
        const el = document.getElementById(id);
        if(el) {
            el.addEventListener("focus", () => { activeInputElement = el; });
            el.addEventListener("click", () => { activeInputElement = el; });
        }
    });
    
    toggleBtn.addEventListener("click", () => {
        const t = langRes[currentLang];
        if(keyboardDiv.style.display === "none") {
            keyboardDiv.style.display = "block";
            toggleTextSpan.innerText = t.hideKeyboardText;
        } else {
            keyboardDiv.style.display = "none";
            toggleTextSpan.innerText = t.toggleKeyboardText;
        }
    });

    // Handle keyboard button clicks
    document.querySelectorAll(".key-btn").forEach(btn => {
        btn.addEventListener("click", (e) => {
            e.preventDefault();
            const key = btn.getAttribute("data-key");
            if(!activeInputElement) {
                // Default to fullName if no field focused
                activeInputElement = document.getElementById("fullName");
                if(activeInputElement) activeInputElement.focus();
                else return;
            }
            if(key === "backspace") {
                let val = activeInputElement.value;
                activeInputElement.value = val.slice(0, -1);
            } else if(key === "space") {
                activeInputElement.value += " ";
            } else if(key === "clear") {
                activeInputElement.value = "";
            } else if(key === "tab") {
                const allInputs = ['fullName', 'omangId', 'visitReason', 'symptomInput'];
                let currentIdx = allInputs.findIndex(id => document.getElementById(id) === activeInputElement);
                let nextIdx = (currentIdx + 1) % allInputs.length;
                activeInputElement = document.getElementById(allInputs[nextIdx]);
                if(activeInputElement) activeInputElement.focus();
            } else if(key === "enter") {
                if(activeInputElement.tagName === "TEXTAREA") activeInputElement.value += "\n";
            } else {
                activeInputElement.value += key;
            }
            activeInputElement.dispatchEvent(new Event('input', { bubbles: true }));
        });
    });

    // Accessibility: Font Size Controls
    let currentFontSize = 100;
    document.getElementById("fontUp").onclick = () => { if(currentFontSize < 150) { currentFontSize += 10; document.body.style.fontSize = currentFontSize + "%"; } };
    document.getElementById("fontDown").onclick = () => { if(currentFontSize > 70) { currentFontSize -= 10; document.body.style.fontSize = currentFontSize + "%"; } };
    
    // High Contrast Mode
    let highContrastActive = false;
    document.getElementById("contrastBtn").onclick = () => {
        if(!highContrastActive) {
            document.body.style.background = "#000000";
            document.body.style.color = "#ffffe0";
            highContrastActive = true;
        } else {
            document.body.style.background = "";
            document.body.style.color = "";
            highContrastActive = false;
        }
    };
    
    // Language Switchers
    document.getElementById("langEn").onclick = () => { currentLang = "en"; updateUI(); };
    document.getElementById("langTs").onclick = () => { currentLang = "ts"; updateUI(); };
    
    // Initialize
    loadQueue();
    updateUI();
</script>
</body>
</html>
