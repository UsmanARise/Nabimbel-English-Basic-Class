<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hello, Friends Nabimbel! - Learn English, Play and Have Fun!</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --blue: #A8D8EA;
    --yellow: #FFE66D;
    --orange: #FFB347;
    --mint: #B5EAD7;
    --purple: #C7CEEA;
    --pink: #FFB7B2;
    --dark: #4A4A6A;
    --white: #FFFFFF;
    --shadow: 0 6px 20px rgba(74, 74, 106, 0.12);
  }

  body {
    font-family: 'Nunito', sans-serif;
    background: linear-gradient(135deg, #FFF9E6 0%, #E8F6FF 50%, #F0E8FF 100%);
    min-height: 100vh;
    color: var(--dark);
    overflow-x: hidden;
  }

  .sunflower-bg {
    position: fixed;
    font-size: 40px;
    opacity: 0.15;
    pointer-events: none;
    z-index: 0;
    animation: sway 6s ease-in-out infinite;
  }
  @keyframes sway { 0%,100%{transform:rotate(-10deg)} 50%{transform:rotate(10deg)} }

  nav {
    background: rgba(255,255,255,0.9);
    backdrop-filter: blur(10px);
    padding: 12px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 10px;
    box-shadow: 0 2px 15px rgba(0,0,0,0.06);
    position: sticky;
    top: 0;
    z-index: 100;
  }
  .logo { display:flex; align-items:center; gap:8px; font-weight:900; font-size:1.1rem; color:var(--dark); cursor:pointer; }
  .logo span { font-size:1.6rem; }
  .nav-links { display:flex; gap:6px; flex-wrap:wrap; }
  .nav-links button {
    background:transparent; border:none; padding:8px 16px; border-radius:20px;
    font-family:'Nunito',sans-serif; font-weight:700; font-size:0.9rem; color:var(--dark);
    cursor:pointer; transition:all 0.25s;
  }
  .nav-links button:hover { background: var(--yellow); transform: translateY(-2px); }
  .nav-links button.active { background: var(--orange); color: white; }

  .page { display:none; padding:30px 20px 60px; max-width:1100px; margin:0 auto; position:relative; z-index:1; }
  .page.active { display:block; animation:fadeIn 0.4s ease; }
  @keyframes fadeIn { from{opacity:0;transform:translateY(10px)} to{opacity:1;transform:translateY(0)} }

  .hero { text-align:center; padding:40px 20px; }
  .hero h1 {
    font-size: clamp(2rem, 5vw, 3.2rem);
    font-weight: 900;
    background: linear-gradient(135deg, #FF9A56, #FFD93D, #6BCB77);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    margin-bottom: 12px;
  }
  .hero p { font-size: 1.15rem; color:#6B6B8A; margin-bottom:24px; }
  .illustration { font-size: clamp(3rem, 8vw, 5rem); margin:20px 0; letter-spacing:10px; }

  .btn-primary {
    background: linear-gradient(135deg, #FFB347, #FF9A56);
    color:white; border:none; padding:16px 40px; border-radius:30px;
    font-family:'Nunito',sans-serif; font-size:1.15rem; font-weight:800; cursor:pointer;
    box-shadow: 0 6px 20px rgba(255,154,86,0.4); transition: all 0.3s;
  }
  .btn-primary:hover { transform: translateY(-3px) scale(1.03); box-shadow: 0 10px 28px rgba(255,154,86,0.55); }
  .btn-secondary {
    background: var(--mint); color: var(--dark); border: none;
    padding: 12px 28px; border-radius: 25px;
    font-family: 'Nunito', sans-serif; font-size: 1rem; font-weight: 800;
    cursor: pointer; transition: all 0.3s;
  }
  .btn-secondary:hover { background:#9EE0C5; transform: translateY(-2px); }

  .cards-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:20px; margin-top:30px; }
  .feature-card {
    background: var(--white); border-radius: 22px; padding: 26px 20px;
    text-align: center; box-shadow: var(--shadow); transition: all 0.3s;
    cursor: pointer; border: 3px solid transparent;
  }
  .feature-card:hover { transform: translateY(-6px); border-color: var(--yellow); }
  .feature-card .icon { font-size: 2.6rem; margin-bottom: 10px; }
  .feature-card h3 { font-size: 1.1rem; font-weight: 800; margin-bottom: 6px; }
  .feature-card p { font-size: 0.85rem; color: #8A8AA5; }

  .progress-wrap { margin: 30px auto; max-width: 600px; }
  .progress-label { display:flex; justify-content:space-between; font-weight:700; font-size:0.9rem; margin-bottom:8px; }
  .progress-bar { height:18px; background:#E8E8F0; border-radius:12px; overflow:hidden; }
  .progress-fill { height:100%; width:0%; background:linear-gradient(90deg,#6BCB77,#FFD93D); border-radius:12px; transition:width 0.8s ease; }

  .section-title { font-size:1.6rem; font-weight:900; margin:30px 0 6px; display:flex; align-items:center; gap:10px; }
  .section-sub { color:#8A8AA5; margin-bottom:20px; font-size:0.95rem; }

  .learn-section { margin-bottom: 36px; }
  .materi-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(280px,1fr)); gap:16px; }
  .materi-card {
    background: var(--white); border-radius: 18px; padding: 20px;
    box-shadow: var(--shadow); border-left: 6px solid var(--blue);
    transition: all 0.3s; position: relative;
  }
  .materi-card:hover { transform: translateY(-3px); box-shadow: 0 10px 28px rgba(74,74,106,0.18); }
  .materi-card .en { font-size: 1.25rem; font-weight: 800; color: #3A3A5A; margin-bottom: 4px; }
  .materi-card .id { color: #6B6B8A; font-size: 0.95rem; margin-bottom: 10px; }
  .materi-card .contoh { font-size: 0.82rem; color: #8A8AA5; font-style: italic; background: #F8F8FC; padding: 8px 12px; border-radius: 10px; margin-top: 8px; }
  .speaker-btn {
    background: var(--yellow); border: none; width: 38px; height: 38px;
    border-radius: 50%; font-size: 1.1rem; cursor: pointer;
    transition: all 0.25s; position: absolute; top: 16px; right: 16px;
  }
  .speaker-btn:hover { transform: scale(1.15); background: var(--orange); }
  .learned-check { font-size: 0.8rem; color: #6BCB77; font-weight: 700; margin-top: 6px; display: none; }

  .info-box {
    background: linear-gradient(135deg, #FFF3CD, #FFE8A3);
    border-radius: 16px; padding: 18px 22px; margin: 20px 0;
    border-left: 6px solid var(--orange); font-size: 0.92rem; line-height: 1.6;
  }

  .practice-tabs { display:flex; gap:10px; flex-wrap:wrap; margin-bottom:24px; }
  .practice-tabs button {
    padding: 12px 22px; border: none; border-radius: 22px;
    font-family: 'Nunito', sans-serif; font-weight: 800; font-size: 0.95rem;
    cursor: pointer; background: #E8E8F0; color: var(--dark); transition: all 0.25s;
  }
  .practice-tabs button.active { background: var(--orange); color: white; box-shadow: 0 4px 14px rgba(255,154,86,0.4); }

  .activity-box { background: var(--white); border-radius: 22px; padding: 28px; box-shadow: var(--shadow); }
  .match-grid { display:grid; grid-template-columns:1fr 1fr; gap:14px; margin-top:16px; }
  .match-col h4 { font-size: 0.9rem; color: #8A8AA5; margin-bottom: 10px; text-transform: uppercase; letter-spacing: 1px; }
  .match-item {
    background: #F5F5FC; border: 2px solid transparent; border-radius: 14px;
    padding: 14px 16px; margin-bottom: 10px; cursor: pointer; font-weight: 700;
    transition: all 0.2s; font-size: 0.95rem;
  }
  .match-item:hover { background: #EDEDFA; }
  .match-item.selected { border-color: var(--orange); background: #FFF3E0; }
  .match-item.matched { background: #E0F7E8; border-color: #6BCB77; cursor: default; opacity: 0.85; }
  .match-item.wrong { animation: shake 0.4s; border-color: #FF6B6B; }
  @keyframes shake { 0%,100%{transform:translateX(0)} 25%{transform:translateX(-6px)} 75%{transform:translateX(6px)} }

  .feedback { margin-top:14px; padding:12px 18px; border-radius:14px; font-weight:700; font-size:0.92rem; display:none; }
  .feedback.show { display:block; animation:fadeIn 0.3s; }
  .feedback.correct { background:#E0F7E8; color:#2E7D4F; }
  .feedback.incorrect { background:#FFE8E8; color:#C0392B; }

  .score-display { font-size:1.1rem; font-weight:800; margin-top:14px; }
  .score-display span { color: var(--orange); font-size: 1.3rem; }

  .dialogue-scenario { display:flex; gap:10px; flex-wrap:wrap; margin-bottom:20px; }
  .dialogue-scenario button {
    padding: 10px 18px; border: none; border-radius: 20px;
    font-family: 'Nunito', sans-serif; font-weight: 700; cursor: pointer;
    background: #E8E8F0; transition: all 0.25s; font-size: 0.88rem;
  }
  .dialogue-scenario button.active { background: var(--purple); }
  .chat-area { min-height:340px; display:flex; flex-direction:column; gap:12px; padding:10px 0; }
  .chat-bubble {
    max-width:75%; padding:12px 16px; border-radius:18px; font-size:0.95rem;
    line-height:1.5; position:relative; animation:bubbleIn 0.4s ease;
    display:flex; align-items:center; gap:10px;
  }
  @keyframes bubbleIn { from{opacity:0;transform:translateY(10px) scale(0.95)} to{opacity:1;transform:translateY(0) scale(1)} }
  .chat-bubble.andi { background:#D6E8FF; align-self:flex-start; border-bottom-left-radius:4px; }
  .chat-bubble.siti { background:#FFE0EC; align-self:flex-end; border-bottom-right-radius:4px; }
  .chat-bubble .char { font-size: 1.6rem; }
  .chat-bubble .name { font-size: 0.7rem; font-weight: 800; color: #6B6B8A; display: block; margin-bottom: 2px; }
  .chat-bubble .mini-speaker {
    background: rgba(255,255,255,0.7); border: none; border-radius: 50%;
    width: 30px; height: 30px; cursor: pointer; font-size: 0.85rem;
    flex-shrink: 0; transition: transform 0.2s;
  }
  .chat-bubble .mini-speaker:hover { transform: scale(1.15); }
  .dialogue-hint {
    background: linear-gradient(135deg, #E8F6FF, #D6E8FF);
    border-radius: 14px; padding: 14px 18px; font-size: 0.88rem;
    margin: 16px 0; color: #4A4A6A;
  }

  .quiz-container { max-width: 700px; margin: 0 auto; }
  .quiz-header { display:flex; justify-content:space-between; align-items:center; margin-bottom:16px; flex-wrap:wrap; gap:10px; }
  .question-num { font-weight: 800; color: #8A8AA5; font-size: 0.9rem; }
  .quiz-progress { flex:1; min-width:150px; height:10px; background:#E8E8F0; border-radius:8px; overflow:hidden; margin:0 14px; }
  .quiz-progress-fill { height:100%; width:0%; background:linear-gradient(90deg,#6BCB77,#FFD93D); transition:width 0.5s; }
  .question-text { font-size: 1.25rem; font-weight: 800; margin: 20px 0; line-height: 1.5; }

  /* 🔉 BARU: tombol speaker di samping soal kuis */
  .question-text-wrap { display: flex; align-items: flex-start; gap: 10px; }
  .question-speaker {
    background: var(--yellow); border: none; border-radius: 50%;
    width: 40px; height: 40px; font-size: 1.1rem; cursor: pointer;
    flex-shrink: 0; transition: transform 0.2s, background 0.2s;
  }
  .question-speaker:hover { transform: scale(1.12); background: var(--orange); }

  .options { display:flex; flex-direction:column; gap:12px; margin-bottom:20px; }
  .option {
    background:#F5F5FC; border:2px solid transparent; border-radius:16px;
    padding:16px 20px; cursor:pointer; font-weight:700; font-size:1rem;
    text-align:left; font-family:'Nunito',sans-serif; transition:all 0.2s; color:var(--dark);
    display: flex; align-items: center; gap: 10px;
  }
  .option:hover:not(.disabled) { background:#EDEDFA; border-color:var(--purple); }
  .option.selected { border-color: var(--orange); background: #FFF3E0; }
  .option.correct { background: #E0F7E8; border-color: #6BCB77; }
  .option.incorrect { background: #FFE8E8; border-color: #FF6B6B; }
  .option.disabled { cursor: default; opacity: 0.85; }

  /* 🔉 BARU: mini speaker dalam opsi */
  .option-mini-speaker {
    background: rgba(255,255,255,0.8); border: none; border-radius: 50%;
    width: 32px; height: 32px; cursor: pointer; font-size: 0.85rem;
    flex-shrink: 0; transition: transform 0.2s, background 0.2s;
  }
  .option-mini-speaker:hover { transform: scale(1.15); background: var(--yellow); }

  .quiz-actions { display:flex; gap:12px; flex-wrap:wrap; }

  .quiz-result { text-align:center; padding:30px 20px; }
  .quiz-result .big-score {
    font-size: 4rem; font-weight: 900;
    background: linear-gradient(135deg, #FF9A56, #FFD93D);
    -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent;
  }
  .quiz-result .msg { font-size: 1.2rem; font-weight: 800; margin: 10px 0 6px; }
  .quiz-result .detail { color: #8A8AA5; margin-bottom: 20px; }
  .quiz-result .badge-display { font-size: 3rem; margin: 10px 0; }

  .stats-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(150px,1fr)); gap:16px; margin:24px 0; }
  .stat-card { background:var(--white); border-radius:20px; padding:22px 16px; text-align:center; box-shadow:var(--shadow); }
  .stat-card .num { font-size:2rem; font-weight:900; color:var(--orange); }
  .stat-card .lbl { font-size:0.82rem; color:#8A8AA5; font-weight:700; margin-top:4px; }

  .badge-area { display:flex; gap:16px; flex-wrap:wrap; margin:16px 0 24px; }
  .badge-item {
    display: flex; align-items: center; gap: 10px;
    background: #F5F5FC; border-radius: 16px; padding: 12px 18px;
    font-weight: 700; font-size: 0.9rem; opacity: 0.4; transition: all 0.3s;
  }
  .badge-item.earned { opacity:1; background:linear-gradient(135deg,#FFF3CD,#FFE8A3); box-shadow:0 4px 14px rgba(255,200,60,0.3); }
  .badge-item .badge-icon { font-size: 1.6rem; }

  .toast {
    position: fixed; bottom: 24px; left: 50%;
    transform: translateX(-50%) translateY(100px);
    background: linear-gradient(135deg, #6BCB77, #4CAF50);
    color: white; padding: 14px 28px; border-radius: 20px;
    font-weight: 800; box-shadow: 0 8px 24px rgba(76,175,80,0.4);
    transition: transform 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    z-index: 999; font-size: 0.95rem;
  }
  .toast.show { transform: translateX(-50%) translateY(0); }

  .confetti { position:fixed; pointer-events:none; z-index:998; font-size:1.5rem; animation:confettiFall 1.5s ease-out forwards; }
  @keyframes confettiFall { to { transform: translateY(100vh) rotate(720deg); opacity: 0; } }

  @media (max-width: 600px) {
    .match-grid { grid-template-columns: 1fr; }
    .nav-links button { padding: 6px 10px; font-size: 0.82rem; }
    .hero h1 { font-size: 1.8rem; }
  }
</style>
</head>
<body>

<div class="sunflower-bg" style="top:15%;left:3%">🌻</div>
<div class="sunflower-bg" style="top:45%;right:4%;animation-delay:1s">🌻</div>
<div class="sunflower-bg" style="bottom:10%;left:8%;animation-delay:2s">🌻</div>
<div class="sunflower-bg" style="top:75%;right:12%;animation-delay:1.5s">🌻</div>

<nav>
  <div class="logo" onclick="showPage('home')"><span>🌻</span> Hello, Friends Nabimbel!</div>
  <div class="nav-links">
    <button data-page="home" class="active" onclick="showPage('home')">Home</button>
    <button data-page="learn" onclick="showPage('learn')">Learn</button>
    <button data-page="practice" onclick="showPage('practice')">Practice</button>
    <button data-page="talk" onclick="showPage('talk')">Let's Talk</button>
    <button data-page="quiz" onclick="showPage('quiz')">Quiz</button>
    <button data-page="progress" onclick="showPage('progress')">My Progress</button>
  </div>
</nav>

<!-- HOME -->
<div class="page active" id="page-home">
  <div class="hero">
    <div class="illustration">👧🌻👦</div>
    <h1>Let's Learn Greetings!</h1>
    <p>Belajar sapaan Bahasa Inggris dengan cara yang seru dan menyenangkan.</p>
    <button class="btn-primary" onclick="showPage('learn')">🚀 Start Learning</button>
  </div>
  <div class="cards-grid">
    <div class="feature-card" onclick="showPage('learn')"><div class="icon">📚</div><h3>Learn Vocabulary</h3><p>Pelajari kosakata sapaan</p></div>
    <div class="feature-card" onclick="showPage('practice')"><div class="icon">✏️</div><h3>Practice Dialogue</h3><p>Latihan percakapan interaktif</p></div>
    <div class="feature-card" onclick="showPage('talk')"><div class="icon">🎮</div><h3>Play Games</h3><p>Simulasi percakapan seru</p></div>
    <div class="feature-card" onclick="showPage('quiz')"><div class="icon">🏆</div><h3>Take a Quiz</h3><p>Uji pemahamanmu!</p></div>
  </div>
  <div class="progress-wrap">
    <div class="progress-label"><span>Progres Belajarmu</span><span id="home-progress-text">0%</span></div>
    <div class="progress-bar"><div class="progress-fill" id="home-progress-fill"></div></div>
  </div>
</div>

<!-- LEARN -->
<div class="page" id="page-learn">
  <h2 class="section-title">📚 Learn Greetings</h2>
  <p class="section-sub">Klik tombol 🔊 untuk mendengarkan pelafalan, dan klik kartu untuk menandai sudah dipelajari.</p>
  <div class="learn-section"><h3 class="section-title" style="font-size:1.2rem">1️⃣ Basic Greetings</h3><div class="materi-grid" id="materi-basic"></div></div>
  <div class="learn-section"><h3 class="section-title" style="font-size:1.2rem">2️⃣ Asking How Someone Is</h3><div class="materi-grid" id="materi-howareyou"></div></div>
  <div class="learn-section"><h3 class="section-title" style="font-size:1.2rem">3️⃣ Introducing Yourself</h3><div class="materi-grid" id="materi-intro"></div></div>
  <div class="learn-section"><h3 class="section-title" style="font-size:1.2rem">4️⃣ Leave-taking</h3><div class="materi-grid" id="materi-leave"></div></div>
  <div class="info-box">
    💡 <strong>Good evening vs Good night:</strong><br>
    "Good evening" digunakan saat <em>bertemu</em> seseorang pada malam hari (sekitar pukul 18.00 ke atas).<br>
    "Good night" digunakan saat <em>berpisah</em> atau <em>akan tidur</em> pada malam hari — bukan untuk menyapa saat bertemu!
  </div>
  <div class="progress-wrap">
    <div class="progress-label"><span>Materi dipelajari</span><span id="learn-progress-text">0%</span></div>
    <div class="progress-bar"><div class="progress-fill" id="learn-progress-fill"></div></div>
  </div>
</div>

<!-- PRACTICE -->
<div class="page" id="page-practice">
  <h2 class="section-title">✏️ Practice</h2>
  <p class="section-sub">Ayo latihan dengan tiga aktivitas seru!</p>
  <div class="practice-tabs">
    <button class="active" onclick="showActivity('match', this)">1. Match the Words</button>
    <button onclick="showActivity('dialogue', this)">2. Complete the Dialogue</button>
    <button onclick="showActivity('choose', this)">3. Choose the Right Greeting</button>
  </div>

  <div class="activity-box" id="activity-match">
    <h3 style="margin-bottom:6px">🔗 Match the Words</h3>
    <p style="color:#8A8AA5;font-size:0.9rem;margin-bottom:10px">Cocokkan ungkapan Bahasa Inggris dengan artinya. Klik satu dari kiri, lalu satu dari kanan.</p>
    <div class="match-grid">
      <div class="match-col"><h4>English</h4><div id="match-left"></div></div>
      <div class="match-col"><h4>Bahasa Indonesia</h4><div id="match-right"></div></div>
    </div>
    <div class="feedback" id="match-feedback"></div>
    <div class="score-display">Skor: <span id="match-score">0</span> / 5</div>
    <button class="btn-secondary" style="margin-top:14px" onclick="initMatch()">🔄 Ulangi</button>
  </div>

  <div class="activity-box" id="activity-dialogue" style="display:none">
    <h3 style="margin-bottom:6px">💬 Complete the Dialogue</h3>
    <p style="color:#8A8AA5;font-size:0.9rem;margin-bottom:16px">Pilih ungkapan yang tepat untuk melengkapi dialog.</p>
    <div id="dialogue-container"></div>
    <div class="feedback" id="dialogue-feedback"></div>
    <div class="score-display">Skor: <span id="dialogue-score">0</span> / 3</div>
    <button class="btn-secondary" style="margin-top:14px" onclick="initDialogue()">🔄 Ulangi</button>
  </div>

  <div class="activity-box" id="activity-choose" style="display:none">
    <h3 style="margin-bottom:6px">🎯 Choose the Right Greeting</h3>
    <p style="color:#8A8AA5;font-size:0.9rem;margin-bottom:16px">Pilih sapaan yang tepat sesuai situasi.</p>
    <div id="choose-container"></div>
    <div class="feedback" id="choose-feedback"></div>
    <div class="score-display">Skor: <span id="choose-score">0</span> / 3</div>
    <button class="btn-secondary" style="margin-top:14px" onclick="initChoose()">🔄 Ulangi</button>
  </div>
</div>

<!-- TALK -->
<div class="page" id="page-talk">
  <h2 class="section-title">💬 Let's Talk</h2>
  <p class="section-sub">Simulasi percakapan dengan Andi & Siti. Klik 🔊 untuk mendengar, dan "Next Dialogue" untuk lanjut.</p>
  <div class="dialogue-hint">
    📖 <strong>Petunjuk:</strong> Baca dialog bersama tutor atau temanmu secara bergantian. Andi membaca bagian Andi, Siti membaca bagian Siti. Gunakan tombol 🔊 untuk mendengar pelafalan setiap kalimat.
  </div>
  <div class="dialogue-scenario" id="scenario-buttons"></div>
  <div class="activity-box">
    <div class="chat-area" id="chat-area"></div>
    <div style="display:flex;gap:12px;flex-wrap:wrap;margin-top:16px">
      <button class="btn-primary" style="padding:12px 28px;font-size:1rem" onclick="nextDialogue()">Next Dialogue ▶</button>
      <button class="btn-secondary" onclick="restartDialogue()">🔄 Mulai Ulang</button>
    </div>
  </div>
</div>

<!-- QUIZ -->
<div class="page" id="page-quiz">
  <h2 class="section-title">🏆 Quiz</h2>
  <p class="section-sub">Uji pemahamanmu tentang Greetings! Ada 10 soal pilihan ganda.</p>

  <div class="quiz-container" id="quiz-start-box">
    <div class="activity-box" style="text-align:center;padding:50px 30px">
      <div style="font-size:3rem;margin-bottom:12px">🎯</div>
      <h3 style="margin-bottom:8px">Siap untuk kuis?</h3>
      <p style="color:#8A8AA5;margin-bottom:24px">Jawab 10 soal dan dapatkan skormu!</p>
      <button class="btn-primary" onclick="startQuiz()">🚀 Mulai Kuis</button>
    </div>
  </div>

  <div class="quiz-container" id="quiz-box" style="display:none">
    <div class="quiz-header">
      <span class="question-num" id="question-num">Question 1 of 10</span>
      <div class="quiz-progress"><div class="quiz-progress-fill" id="quiz-progress-fill"></div></div>
    </div>
    <div class="activity-box">
      <!-- 🔉 BARU: wrapper dengan tombol speaker di samping soal -->
      <div class="question-text-wrap">
        <button class="question-speaker" id="question-speaker" title="Dengarkan soal">🔊</button>
        <div class="question-text" id="question-text" style="margin-top:0"></div>
      </div>
      <div class="options" id="options-box"></div>
      <div class="feedback" id="quiz-feedback"></div>
      <div class="quiz-actions" style="margin-top:16px">
        <button class="btn-primary" style="padding:12px 28px;font-size:1rem" id="check-btn" onclick="checkAnswer()">Check Answer</button>
        <button class="btn-secondary" id="next-btn" onclick="nextQuestion()" style="display:none">Next Question ▶</button>
      </div>
    </div>
  </div>

  <div class="quiz-container" id="quiz-result-box" style="display:none">
    <div class="activity-box quiz-result">
      <div class="badge-display" id="result-badge">🌟</div>
      <div class="big-score" id="result-score">0</div>
      <div class="msg" id="result-msg"></div>
      <div class="detail" id="result-detail"></div>
      <button class="btn-primary" onclick="startQuiz()">🔄 Try Again</button>
    </div>
  </div>
</div>

<!-- PROGRESS -->
<div class="page" id="page-progress">
  <h2 class="section-title">📊 My Progress</h2>
  <p class="section-sub">Lihat perkembangan belajarmu di sini!</p>
  <div class="progress-wrap" style="max-width:100%">
    <div class="progress-label"><span>Progres Keseluruhan</span><span id="progress-overall-text">0%</span></div>
    <div class="progress-bar"><div class="progress-fill" id="progress-overall-fill"></div></div>
  </div>
  <div class="stats-grid">
    <div class="stat-card"><div class="num" id="stat-materi">0%</div><div class="lbl">Materi Dipelajari</div></div>
    <div class="stat-card"><div class="num" id="stat-activities">0</div><div class="lbl">Aktivitas Selesai</div></div>
    <div class="stat-card"><div class="num" id="stat-lastscore">-</div><div class="lbl">Skor Kuis Terakhir</div></div>
    <div class="stat-card"><div class="num" id="stat-bestscore">-</div><div class="lbl">Skor Terbaik</div></div>
    <div class="stat-card"><div class="num" id="stat-stars">0</div><div class="lbl">⭐ Bintang</div></div>
  </div>
  <h3 style="margin:20px 0 10px">🏅 Badge</h3>
  <div class="badge-area" id="badge-area">
    <div class="badge-item" id="badge-beginner"><span class="badge-icon">🌱</span> Greeting Beginner</div>
    <div class="badge-item" id="badge-master"><span class="badge-icon">👑</span> Greeting Master</div>
  </div>
  <button class="btn-primary" style="margin-top:20px" onclick="showPage('learn')">📖 Lanjutkan Belajar</button>
</div>

<div class="toast" id="toast"></div>

<script>
/* ============ STATE & STORAGE ============ */
const STORAGE_KEY = 'nabimbel_progress_v1';
let state = {
  learnedCards: [],
  matchDone: false,
  dialogueDone: false,
  chooseDone: false,
  lastQuizScore: null,
  bestQuizScore: null,
  stars: 0,
  badges: []
};

function loadState() {
  try {
    const saved = localStorage.getItem(STORAGE_KEY);
    if (saved) state = Object.assign(state, JSON.parse(saved));
  } catch(e) { console.warn('Storage error', e); }
}
function saveState() {
  try { localStorage.setItem(STORAGE_KEY, JSON.stringify(state)); } catch(e) {}
  updateProgressUI();
}

/* ============ NAVIGATION ============ */
function showPage(name) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  const target = document.getElementById('page-' + name);
  if (target) target.classList.add('active');
  document.querySelectorAll('.nav-links button').forEach(b => {
    b.classList.toggle('active', b.dataset.page === name);
  });
  window.scrollTo({ top: 0, behavior: 'smooth' });
  if (name === 'progress') updateProgressUI();
  if (name === 'practice') { initMatch(); initDialogue(); initChoose(); }
  if (name === 'talk') { initTalk(); }
}

/* ============ 🔉 BARU: CHILD VOICE (SUARA ANAK) ============ */
/* Strategi:
   1) Muat semua voice (async di beberapa browser).
   2) Pilih voice prioritas yang terdengar seperti anak / pelafalan bagus.
   3) Gunakan pitch tinggi (1.5) + rate 0.85 agar terdengar seperti anak.
   4) Fallback ke voice apapun dengan lang en-*.
*/
let childVoice = null;
let voicesReady = false;

const CHILD_VOICE_PRIORITY = [
  // Prioritas tertinggi: voice yang secara eksplisit untuk anak
  /child/i, /kid/i, /junior/i,
  // Voice wanita UK/US Google — pitch tinggi + pelafalan bagus terdengar seperti anak
  /Google UK English Female/i,
  /Google US English/i,
  /Samantha/i,           // macOS voice wanita jernih
  /Microsoft Zira/i,     // Windows voice wanita
  /Microsoft Aria/i,
  /Karen/i, /Tessa/i,
  /Female/i
];

function pickBestVoice() {
  if (!('speechSynthesis' in window)) return;
  const voices = window.speechSynthesis.getVoices();
  if (!voices || !voices.length) return;

  // 1) Cari berdasarkan prioritas nama
  for (const re of CHILD_VOICE_PRIORITY) {
    const found = voices.find(v => re.test(v.name) && /^en/i.test(v.lang));
    if (found) { childVoice = found; voicesReady = true; return; }
  }
  // 2) Fallback: voice en-GB lalu en-US apa saja
  childVoice = voices.find(v => /^en-GB/i.test(v.lang))
             || voices.find(v => /^en-US/i.test(v.lang))
             || voices.find(v => /^en/i.test(v.lang))
             || voices[0];
  voicesReady = true;
}

// Voice list dimuat async — pasang listener
if ('speechSynthesis' in window) {
  pickBestVoice();
  window.speechSynthesis.onvoiceschanged = pickBestVoice;
}

/* 🔉 Fungsi speak utama — semua suara kini pakai childVoice + pitch tinggi */
function speak(text, opts = {}) {
  if (!text) return;
  if (!('speechSynthesis' in window)) { showToast('Browser tidak mendukung audio 😅'); return; }

  // pastikan voice sudah terpilih
  if (!voicesReady) pickBestVoice();

  window.speechSynthesis.cancel(); // hentikan ucapan sebelumnya
  const u = new SpeechSynthesisUtterance(text);
  u.lang   = (childVoice && childVoice.lang) || 'en-GB';
  u.rate   = opts.rate  ?? 0.85;   // pelan & jelas
  u.pitch  = opts.pitch ?? 1.5;    // tinggi → mirip anak
  u.volume = opts.volume ?? 1;
  if (childVoice) u.voice = childVoice;
  window.speechSynthesis.speak(u);
}

/* Helper: mainkan suara setelah delay kecil (untuk feedback) */
function speakLater(text, delay = 250, opts = {}) {
  setTimeout(() => speak(text, opts), delay);
}

/* ============ TOAST & CONFETTI ============ */
let toastTimer;
function showToast(msg) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => t.classList.remove('show'), 2600);
}
function confetti() {
  const emojis = ['🌻','⭐','🎉','✨','🌟','💛'];
  for (let i = 0; i < 14; i++) {
    const el = document.createElement('div');
    el.className = 'confetti';
    el.textContent = emojis[Math.floor(Math.random()*emojis.length)];
    el.style.left = Math.random()*100 + 'vw';
    el.style.top = '-40px';
    el.style.animationDelay = Math.random()*0.4 + 's';
    document.body.appendChild(el);
    setTimeout(() => el.remove(), 2000);
  }
}

/* ============ LEARN ============ */
const materiData = {
  basic: [
    { id:'b1', en:'Hello!', id_:'Halo!', icon:'👋', contoh:'Hello! Nice to see you.' },
    { id:'b2', en:'Hi!', id_:'Hai!', icon:'😊', contoh:'Hi! I am Andi.' },
    { id:'b3', en:'Good morning!', id_:'Selamat pagi!', icon:'🌅', contoh:'Good morning, Mom!' },
    { id:'b4', en:'Good afternoon!', id_:'Selamat siang/sore!', icon:'☀️', contoh:'Good afternoon, Sir!' },
    { id:'b5', en:'Good evening!', id_:'Selamat malam (saat bertemu)!', icon:'🌆', contoh:'Good evening, everyone!' }
  ],
  howareyou: [
    { id:'h1', en:'How are you?', id_:'Apa kabar?', icon:'🤔', contoh:'Hi Siti, how are you?' },
    { id:'h2', en:"I'm fine, thank you.", id_:'Saya baik, terima kasih.', icon:'😊', contoh:"I'm fine, thank you, and you?" },
    { id:'h3', en:"I'm great!", id_:'Saya sangat baik!', icon:'🤩', contoh:"I'm great! Today is my birthday." },
    { id:'h4', en:"I'm okay.", id_:'Saya baik-baik saja.', icon:'🙂', contoh:"I'm okay, thanks." },
    { id:'h5', en:'How about you?', id_:'Bagaimana denganmu?', icon:'👉', contoh:"I'm fine. How about you?" }
  ],
  intro: [
    { id:'i1', en:'What is your name?', id_:'Siapa namamu?', icon:'❓', contoh:'Hi! What is your name?' },
    { id:'i2', en:'My name is ...', id_:'Nama saya ...', icon:'📛', contoh:'My name is Andi.' },
    { id:'i3', en:'Nice to meet you.', id_:'Senang bertemu denganmu.', icon:'🤝', contoh:'Nice to meet you, Siti.' },
    { id:'i4', en:'Nice to meet you too.', id_:'Senang bertemu denganmu juga.', icon:'😄', contoh:'Nice to meet you too, Andi.' }
  ],
  leave: [
    { id:'l1', en:'Goodbye!', id_:'Selamat tinggal!', icon:'👋', contoh:'Goodbye, Mrs. Rina!' },
    { id:'l2', en:'Bye!', id_:'Dadah!', icon:'✌️', contoh:'Bye, Andi! See you.' },
    { id:'l3', en:'See you!', id_:'Sampai jumpa!', icon:'🫡', contoh:'See you, Siti!' },
    { id:'l4', en:'See you tomorrow!', id_:'Sampai jumpa besok!', icon:'📅', contoh:'See you tomorrow at school!' }
  ]
};

function renderLearnCards() {
  Object.keys(materiData).forEach(section => {
    const container = document.getElementById('materi-' + section);
    container.innerHTML = '';
    materiData[section].forEach(item => {
      const learned = state.learnedCards.includes(item.id);
      const card = document.createElement('div');
      card.className = 'materi-card';
      card.style.cursor = 'pointer';
      card.innerHTML = `
        <button class="speaker-btn" title="Dengarkan">🔊</button>
        <div style="font-size:1.8rem;margin-bottom:6px">${item.icon}</div>
        <div class="en">${item.en}</div>
        <div class="id">${item.id_}</div>
        <div class="contoh">"${item.contoh}"</div>
        ${learned ? '<div class="learned-check" style="display:block">✅ Sudah dipelajari</div>' : ''}
      `;
      // 🔉 klik speaker: ucapkan English + arti Indonesia (dua kalimat)
      card.querySelector('.speaker-btn').addEventListener('click', (e) => {
        e.stopPropagation();
        speak(item.en, { pitch: 1.5, rate: 0.85 });
      });
      card.addEventListener('click', () => {
        // 🔉 ucapkan otomatis saat kartu diklik
        speak(item.en, { pitch: 1.5, rate: 0.85 });
        if (!state.learnedCards.includes(item.id)) {
          state.learnedCards.push(item.id);
          saveState();
          renderLearnCards();
          checkBeginnerBadge();
          showToast('Great job! Materi ditandai dipelajari ✅');
        }
      });
      container.appendChild(card);
    });
  });
  updateProgressUI();
}

function checkBeginnerBadge() {
  const totalCards = Object.values(materiData).flat().length;
  if (state.learnedCards.length >= totalCards && !state.badges.includes('beginner')) {
    state.badges.push('beginner');
    saveState();
    confetti();
    showToast('🏅 Badge "Greeting Beginner" diperoleh!');
    // 🔉 suara anak ucapan selamat (Inggris)
    speak('Congratulations! You are a Greeting Beginner!', { pitch: 1.5, rate: 0.85 });
  }
}

/* ============ PROGRESS UI ============ */
function updateProgressUI() {
  const totalCards = Object.values(materiData).flat().length;
  const learnedPct = Math.round((state.learnedCards.length / totalCards) * 100);
  const activitiesDone = (state.matchDone?1:0) + (state.dialogueDone?1:0) + (state.chooseDone?1:0);
  const quizPart = state.bestQuizScore !== null ? 1 : 0;
  const totalActivities = 4;
  const overallPct = Math.round(((activitiesDone + quizPart) / totalActivities) * 100);

  const homeFill = document.getElementById('home-progress-fill');
  const homeText = document.getElementById('home-progress-text');
  if (homeFill) { homeFill.style.width = overallPct + '%'; homeText.textContent = overallPct + '%'; }

  const learnFill = document.getElementById('learn-progress-fill');
  const learnText = document.getElementById('learn-progress-text');
  if (learnFill) { learnFill.style.width = learnedPct + '%'; learnText.textContent = learnedPct + '%'; }

  const pf = document.getElementById('progress-overall-fill');
  const pt = document.getElementById('progress-overall-text');
  if (pf) { pf.style.width = overallPct + '%'; pt.textContent = overallPct + '%'; }
  const sm = document.getElementById('stat-materi'); if (sm) sm.textContent = learnedPct + '%';
  const sa = document.getElementById('stat-activities'); if (sa) sa.textContent = activitiesDone + ' / 3';
  const sl = document.getElementById('stat-lastscore'); if (sl) sl.textContent = state.lastQuizScore !== null ? state.lastQuizScore : '-';
  const sb = document.getElementById('stat-bestscore'); if (sb) sb.textContent = state.bestQuizScore !== null ? state.bestQuizScore : '-';
  const ss = document.getElementById('stat-stars'); if (ss) ss.textContent = state.stars;

  const bB = document.getElementById('badge-beginner');
  const bM = document.getElementById('badge-master');
  if (bB) bB.classList.toggle('earned', state.badges.includes('beginner'));
  if (bM) bM.classList.toggle('earned', state.badges.includes('master'));
}

/* ============ PRACTICE: MATCH ============ */
const matchPairs = [
  { en:'Hello!', id:'Halo!' },
  { en:'Good morning!', id:'Selamat pagi!' },
  { en:'How are you?', id:'Apa kabar?' },
  { en:'Nice to meet you.', id:'Senang bertemu denganmu.' },
  { en:'Goodbye!', id:'Selamat tinggal!' }
];

let matchSelectedLeft = null;
let matchMatched = 0;
let matchScore = 0;

function shuffle(a) { const b=[...a]; for(let i=b.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[b[i],b[j]]=[b[j],b[i]];} return b; }

function initMatch() {
  matchSelectedLeft = null;
  matchMatched = 0;
  matchScore = 0;
  document.getElementById('match-score').textContent = '0';
  document.getElementById('match-feedback').className = 'feedback';
  const left = document.getElementById('match-left');
  const right = document.getElementById('match-right');
  left.innerHTML = ''; right.innerHTML = '';

  shuffle(matchPairs).forEach(p => {
    const el = document.createElement('div');
    el.className = 'match-item';
    el.textContent = p.en;
    el.dataset.key = p.en;
    el.dataset.side = 'left';
    el.addEventListener('click', () => handleMatchClick(el));
    left.appendChild(el);
  });

  shuffle(matchPairs).forEach(p => {
    const el = document.createElement('div');
    el.className = 'match-item';
    el.textContent = p.id;
    el.dataset.key = p.en;
    el.dataset.side = 'right';
    el.addEventListener('click', () => handleMatchClick(el));
    right.appendChild(el);
  });
}

function handleMatchClick(el) {
  if (el.classList.contains('matched')) return;
  const feedback = document.getElementById('match-feedback');

  if (el.dataset.side === 'left') {
    document.querySelectorAll('#match-left .match-item').forEach(x => x.classList.remove('selected'));
    el.classList.add('selected');
    matchSelectedLeft = el;
    // 🔉 BARU: ucapkan English saat item kiri dipilih
    speak(el.dataset.key, { pitch: 1.5, rate: 0.85 });
    return;
  }

  if (!matchSelectedLeft) {
    feedback.className = 'feedback show incorrect';
    feedback.textContent = 'Pilih dulu ungkapan Bahasa Inggris di sebelah kiri ya! 😊';
    return;
  }

  // 🔉 BARU: saat klik kanan, ucapkan English dari pasangan kiri (jika cocok) / English dari kanan (jika salah)
  if (matchSelectedLeft.dataset.key === el.dataset.key) {
    matchSelectedLeft.classList.remove('selected');
    matchSelectedLeft.classList.add('matched');
    el.classList.add('matched');
    matchMatched++;
    matchScore += 20;
    document.getElementById('match-score').textContent = matchScore;
    feedback.className = 'feedback show correct';
    feedback.textContent = 'Great job! Cocok! ✅';
    // ucapkan English yang cocok (dengan suara anak)
    speak(el.dataset.key, { pitch: 1.5, rate: 0.85 });
    matchSelectedLeft = null;
    if (matchMatched === matchPairs.length) {
      feedback.textContent = 'Excellent! Semua pasangan cocok! 🎉';
      confetti();
      speakLater('Excellent! Well done!', 900);
      if (!state.matchDone) {
        state.matchDone = true;
        state.stars += 1;
        saveState();
        showToast('⭐ Bintang +1! Aktivitas selesai.');
      }
      checkBeginnerBadge();
    }
  } else {
    el.classList.add('wrong');
    setTimeout(() => el.classList.remove('wrong'), 500);
    feedback.className = 'feedback show incorrect';
    feedback.textContent = 'Keep trying! Belum cocok, coba lagi 💪';
    // ucapkan English dari kiri (supaya anak dengar lagi) + "Try again" lembut
    speak(matchSelectedLeft.dataset.key, { pitch: 1.5, rate: 0.85 });
    matchSelectedLeft.classList.remove('selected');
    matchSelectedLeft = null;
  }
}

/* ============ PRACTICE: DIALOGUE ============ */
const dialogueQuestions = [
  { lines:['A: Good morning!','B: ___!'], options:['Good morning','Goodbye','Good night'], answer:'Good morning',
    explain:'Karena A menyapa "Good morning", jawaban yang tepat juga "Good morning".' },
  { lines:['A: How are you?','B: ___'], options:["I'm fine, thank you.",'My name is Andi.','See you tomorrow!'], answer:"I'm fine, thank you.",
    explain:'"How are you?" menanyakan kabar, jadi jawabannya "I\'m fine, thank you."' },
  { lines:['A: Nice to meet you.','B: ___'], options:['Nice to meet you too.','Goodbye!','Good afternoon!'], answer:'Nice to meet you too.',
    explain:'Balasan "Nice to meet you" adalah "Nice to meet you too."' }
];

let dialogueIdx = 0;
let dialogueScore = 0;
let dialogueAnswered = false;

function initDialogue() {
  dialogueIdx = 0;
  dialogueScore = 0;
  document.getElementById('dialogue-score').textContent = '0';
  document.getElementById('dialogue-feedback').className = 'feedback';
  renderDialogueQuestion();
}

function renderDialogueQuestion() {
  const container = document.getElementById('dialogue-container');
  const feedback = document.getElementById('dialogue-feedback');
  feedback.className = 'feedback';
  dialogueAnswered = false;

  if (dialogueIdx >= dialogueQuestions.length) {
    container.innerHTML = '<div style="text-align:center;padding:30px"><div style="font-size:3rem">🎉</div><h3>Excellent! Semua dialog selesai!</h3></div>';
    if (!state.dialogueDone) {
      state.dialogueDone = true;
      state.stars += 1;
      saveState();
      confetti();
      speakLater('Excellent! Well done!', 400);
      showToast('⭐ Bintang +1! Aktivitas selesai.');
      checkBeginnerBadge();
    }
    return;
  }

  const q = dialogueQuestions[dialogueIdx];
  // 🔉 BARU: tambahkan tombol 🔊 untuk mendengar baris dialog (English saja)
  container.innerHTML = `
    <div style="background:#F5F5FC;border-radius:16px;padding:20px;margin-bottom:16px;font-size:1.05rem;font-weight:700;line-height:1.8;position:relative">
      <button class="speaker-btn" id="dlg-speaker" title="Dengarkan dialog" style="position:static;margin-bottom:8px">🔊</button>
      ${q.lines.map(l => `<div>${l.replace('___','<span style="color:#FF9A56">___</span>')}</div>`).join('')}
    </div>
    <div class="options" id="dialogue-options"></div>
  `;
  // 🔉 BARU: klik speaker dialog → ucapkan baris A + B (tanpa blank) English
  document.getElementById('dlg-speaker').addEventListener('click', () => {
    const spoken = q.lines.map(l => l.replace(/^[AB]:\s*/, '').replace('___', '')).join(' ');
    speak(spoken, { pitch: 1.5, rate: 0.85 });
  });

  const optsBox = document.getElementById('dialogue-options');
  q.options.forEach(opt => {
    const btn = document.createElement('button');
    btn.className = 'option';
    btn.innerHTML = `<span style="flex:1;text-align:left">${opt}</span>`;
    // 🔉 BARU: klik opsi → ucapkan English-nya
    btn.addEventListener('click', () => answerDialogue(btn, opt));
    optsBox.appendChild(btn);
  });
}

function answerDialogue(btn, opt) {
  if (dialogueAnswered) return;
  dialogueAnswered = true;
  const q = dialogueQuestions[dialogueIdx];
  const feedback = document.getElementById('dialogue-feedback');
  const allOpts = document.querySelectorAll('#dialogue-options .option');
  allOpts.forEach(o => o.classList.add('disabled'));

  // 🔉 BARU: ucapkan opsi yang dipilih user (English) — suara anak
  speak(opt, { pitch: 1.5, rate: 0.85 });

  if (opt === q.answer) {
    btn.classList.add('correct');
    dialogueScore += 1;
    document.getElementById('dialogue-score').textContent = dialogueScore;
    feedback.className = 'feedback show correct';
    feedback.textContent = '✅ Great job! ' + q.explain;
  } else {
    btn.classList.add('incorrect');
    allOpts.forEach(o => { if (o.textContent === q.answer) o.classList.add('correct'); });
    feedback.className = 'feedback show incorrect';
    feedback.textContent = '💡 ' + q.explain;
    // 🔉 ulangi jawaban yang benar dengan suara anak setelah 1 detik
    speakLater(q.answer, 1000, { pitch: 1.5, rate: 0.85 });
  }

  setTimeout(() => { dialogueIdx++; renderDialogueQuestion(); }, 2000);
}

/* ============ PRACTICE: CHOOSE ============ */
const chooseScenarios = [
  { icon:'🏫', situation:'Kamu bertemu gurumu di sekolah pukul 07.00 pagi.', question:'What should you say?',
    options:['Good morning!','Good night!','Goodbye!'], answer:'Good morning!' },
  { icon:'🌙', situation:'Kamu bertemu temanmu di taman pukul 19.30 malam.', question:'What should you say?',
    options:['Good night!','Good evening!','Good afternoon!'], answer:'Good evening!' },
  { icon:'👋', situation:'Kamu pulang sekolah dan berpamitan dengan gurumu.', question:'What should you say?',
    options:['Good morning!','Hello!','Goodbye!'], answer:'Goodbye!' }
];

let chooseIdx = 0;
let chooseScore = 0;
let chooseAnswered = false;

function initChoose() {
  chooseIdx = 0;
  chooseScore = 0;
  document.getElementById('choose-score').textContent = '0';
  document.getElementById('choose-feedback').className = 'feedback';
  renderChooseQuestion();
}

function renderChooseQuestion() {
  const container = document.getElementById('choose-container');
  const feedback = document.getElementById('choose-feedback');
  feedback.className = 'feedback';
  chooseAnswered = false;

  if (chooseIdx >= chooseScenarios.length) {
    container.innerHTML = '<div style="text-align:center;padding:30px"><div style="font-size:3rem">🏆</div><h3>Excellent! Semua situasi dijawab!</h3></div>';
    if (!state.chooseDone) {
      state.chooseDone = true;
      state.stars += 1;
      saveState();
      confetti();
      speakLater('Excellent! Well done!', 400);
      showToast('⭐ Bintang +1! Aktivitas selesai.');
      checkBeginnerBadge();
    }
    return;
  }

  const s = chooseScenarios[chooseIdx];
  container.innerHTML = `
    <div style="background:linear-gradient(135deg,#E8F6FF,#D6E8FF);border-radius:16px;padding:24px;text-align:center;margin-bottom:16px">
      <div style="font-size:3rem">${s.icon}</div>
      <p style="font-size:1.05rem;font-weight:700;margin-top:8px">${s.situation}</p>
      <p style="color:#6B6B8A;font-weight:800;margin-top:10px">${s.question}</p>
    </div>
    <div class="options" id="choose-options"></div>
  `;
  const optsBox = document.getElementById('choose-options');
  s.options.forEach(opt => {
    const btn = document.createElement('button');
    btn.className = 'option';
    btn.innerHTML = `<span style="flex:1;text-align:left">${opt}</span>`;
    // 🔉 klik → ucapkan English
    btn.addEventListener('click', () => answerChoose(btn, opt));
    optsBox.appendChild(btn);
  });
}

function answerChoose(btn, opt) {
  if (chooseAnswered) return;
  chooseAnswered = true;
  const s = chooseScenarios[chooseIdx];
  const feedback = document.getElementById('choose-feedback');
  const allOpts = document.querySelectorAll('#choose-options .option');
  allOpts.forEach(o => o.classList.add('disabled'));

  // 🔉 BARU: ucapkan opsi yang dipilih user (English)
  speak(opt, { pitch: 1.5, rate: 0.85 });

  if (opt === s.answer) {
    btn.classList.add('correct');
    chooseScore += 1;
    document.getElementById('choose-score').textContent = chooseScore;
    feedback.className = 'feedback show correct';
    feedback.textContent = '✅ Excellent! Jawabanmu tepat.';
  } else {
    btn.classList.add('incorrect');
    allOpts.forEach(o => { if (o.textContent === s.answer) o.classList.add('correct'); });
    feedback.className = 'feedback show incorrect';
    feedback.textContent = '💡 Jawaban yang tepat: ' + s.answer;
    speakLater(s.answer, 1000, { pitch: 1.5, rate: 0.85 });
  }

  setTimeout(() => { chooseIdx++; renderChooseQuestion(); }, 2000);
}

function showActivity(name, btn) {
  document.querySelectorAll('.practice-tabs button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  document.getElementById('activity-match').style.display = name === 'match' ? 'block' : 'none';
  document.getElementById('activity-dialogue').style.display = name === 'dialogue' ? 'block' : 'none';
  document.getElementById('activity-choose').style.display = name === 'choose' ? 'block' : 'none';
  if (name === 'match') initMatch();
  if (name === 'dialogue') initDialogue();
  if (name === 'choose') initChoose();
}

/* ============ LET'S TALK ============ */
const talkScenarios = [
  { title:'Bertemu Teman', dialogues:[
    { char:'Andi', text:'Hello! Good morning!', icon:'👦' },
    { char:'Siti', text:'Good morning! How are you?', icon:'👧' },
    { char:'Andi', text:"I'm fine, thank you. How about you?", icon:'👦' },
    { char:'Siti', text:"I'm great! Nice to meet you.", icon:'👧' },
    { char:'Andi', text:'Nice to meet you too!', icon:'👦' }
  ]},
  { title:'Menyapa Guru', dialogues:[
    { char:'Andi', text:'Good morning, Mrs. Rina!', icon:'👦' },
    { char:'Mrs. Rina', text:'Good morning, Andi! How are you today?', icon:'👩‍🏫' },
    { char:'Andi', text:"I'm fine, thank you. And you?", icon:'👦' },
    { char:'Mrs. Rina', text:"I'm great, thank you!", icon:'👩‍🏫' },
    { char:'Andi', text:'Goodbye, Mrs. Rina! See you tomorrow!', icon:'👦' }
  ]},
  { title:'Memperkenalkan Diri', dialogues:[
    { char:'Andi', text:'Hi! What is your name?', icon:'👦' },
    { char:'Siti', text:'Hello! My name is Siti.', icon:'👧' },
    { char:'Andi', text:'Nice to meet you, Siti. I am Andi.', icon:'👦' },
    { char:'Siti', text:'Nice to meet you too, Andi!', icon:'👧' },
    { char:'Andi', text:'See you later, Siti!', icon:'👦' }
  ]}
];

let talkScenarioIdx = 0;
let talkLineIdx = 0;

function initTalk() {
  talkScenarioIdx = 0;
  talkLineIdx = 0;
  const btns = document.getElementById('scenario-buttons');
  btns.innerHTML = '';
  talkScenarios.forEach((s, i) => {
    const b = document.createElement('button');
    b.textContent = (i+1) + '. ' + s.title;
    b.className = i === 0 ? 'active' : '';
    b.addEventListener('click', () => {
      document.querySelectorAll('#scenario-buttons button').forEach(x => x.classList.remove('active'));
      b.classList.add('active');
      talkScenarioIdx = i;
      talkLineIdx = 0;
      renderChat();
    });
    btns.appendChild(b);
  });
  renderChat();
}

function renderChat() {
  const area = document.getElementById('chat-area');
  area.innerHTML = '';
  const scen = talkScenarios[talkScenarioIdx];
  const showLines = scen.dialogues.slice(0, talkLineIdx + 1);
  showLines.forEach(d => {
    const bubble = document.createElement('div');
    bubble.className = 'chat-bubble ' + (d.char === 'Siti' ? 'siti' : 'andi');
    bubble.innerHTML = `
      <span class="char">${d.icon}</span>
      <div>
        <span class="name">${d.char}</span>
        ${d.text}
      </div>
      <button class="mini-speaker" title="Dengarkan">🔊</button>
    `;
    bubble.querySelector('.mini-speaker').addEventListener('click', () => speak(d.text, { pitch: 1.5, rate: 0.85 }));
    area.appendChild(bubble);
  });
}

function nextDialogue() {
  const scen = talkScenarios[talkScenarioIdx];
  if (talkLineIdx < scen.dialogues.length - 1) {
    talkLineIdx++;
    renderChat();
    // 🔉 auto-play baris baru dengan suara anak
    speak(scen.dialogues[talkLineIdx].text, { pitch: 1.5, rate: 0.85 });
  } else {
    showToast('Dialog selesai! Pilih skenario lain atau mulai ulang 😊');
    speak('Great job! See you next time!', { pitch: 1.5, rate: 0.85 });
  }
}

function restartDialogue() {
  talkLineIdx = 0;
  renderChat();
}

/* ============ QUIZ ============ */
const quizBank = [
  { q:'What do you say when you meet your friend in the morning?', opts:['Good morning!','Good night!','Goodbye!','Good afternoon!'], ans:'Good morning!' },
  { q:'Apa arti dari "Hello!"?', opts:['Selamat tinggal!','Halo!','Selamat pagi!','Sampai jumpa!'], ans:'Halo!' },
  { q:'Situation: Kamu bertemu gurumu pukul 14.00 siang. What do you say?', opts:['Good morning!','Good evening!','Good afternoon!','Good night!'], ans:'Good afternoon!' },
  { q:'"How are you?" — What is the best answer?', opts:['My name is Andi.','Goodbye!',"I'm fine, thank you.",'Good morning!'], ans:"I'm fine, thank you." },
  { q:'Apa arti dari "Nice to meet you"?', opts:['Senang bertemu denganmu','Selamat pagi','Sampai jumpa besok','Apa kabar?'], ans:'Senang bertemu denganmu' },
  { q:'Which one is used when you are LEAVING someone at night?', opts:['Good evening!','Good night!','Good afternoon!','Hello!'], ans:'Good night!' },
  { q:'"See you tomorrow!" artinya...', opts:['Sampai jumpa besok!','Selamat malam!','Apa kabar?','Senang bertemu!'], ans:'Sampai jumpa besok!' },
  { q:'What is the correct response to "What is your name?"', opts:['Good morning.',"My name is Siti.",'See you later.',"I'm fine, thank you."], ans:'My name is Siti.' },
  { q:'Kamu akan tidur malam. Apa yang kamu ucapkan?', opts:['Good evening!','Good night!','Good afternoon!','Hello!'], ans:'Good night!' },
  { q:'A: "Nice to meet you." B: "..."', opts:['Nice to meet you too.','Good morning.','I am fine.','Goodbye!'], ans:'Nice to meet you too.' }
];

let quizQuestions = [];
let quizIdx = 0;
let quizCorrect = 0;
let quizSelected = null;
let quizChecked = false;

function startQuiz() {
  document.getElementById('quiz-start-box').style.display = 'none';
  document.getElementById('quiz-result-box').style.display = 'none';
  document.getElementById('quiz-box').style.display = 'block';

  quizQuestions = shuffle(quizBank).map(q => ({
    q: q.q,
    ans: q.ans,
    opts: shuffle(q.opts)
  }));
  quizIdx = 0;
  quizCorrect = 0;
  renderQuizQuestion();
}

function renderQuizQuestion() {
  quizSelected = null;
  quizChecked = false;
  const q = quizQuestions[quizIdx];
  document.getElementById('question-num').textContent = `Question ${quizIdx+1} of ${quizQuestions.length}`;
  document.getElementById('quiz-progress-fill').style.width = ((quizIdx) / quizQuestions.length * 100) + '%';
  document.getElementById('question-text').textContent = q.q;
  const fb = document.getElementById('quiz-feedback');
  fb.className = 'feedback';

  // 🔉 BARU: tombol speaker di samping soal → ucapkan pertanyaan (English)
  // Pertanyaan berbahasa Indonesia tidak diucapkan ulang, kita ucapkan versi English saja
  const speakerBtn = document.getElementById('question-speaker');
  // ganti handler lama
  speakerBtn.onclick = () => speak(q.q, { pitch: 1.5, rate: 0.85 });

  // 🔉 auto-play soal saat muncul (jika English) — beri delay kecil agar voice siap
  if (/^[\x00-\x7F]*$/.test(q.q.replace(/[—"".?]/g,''))) {
    // hanya kalau mayoritas ASCII (English)
    setTimeout(() => speak(q.q, { pitch: 1.5, rate: 0.85 }), 400);
  }

  const optsBox = document.getElementById('options-box');
  optsBox.innerHTML = '';
  q.opts.forEach((opt, i) => {
    const btn = document.createElement('button');
    btn.className = 'option';
    btn.innerHTML = `<span style="flex:1;text-align:left">${String.fromCharCode(65+i)}. ${opt}</span>`;
    btn.dataset.value = opt;
    btn.addEventListener('click', () => selectOption(btn, opt));
    optsBox.appendChild(btn);
  });

  document.getElementById('check-btn').style.display = 'inline-block';
  document.getElementById('check-btn').disabled = true;
  document.getElementById('next-btn').style.display = 'none';
}

function selectOption(btn, opt) {
  if (quizChecked) return;
  document.querySelectorAll('#options-box .option').forEach(o => o.classList.remove('selected'));
  btn.classList.add('selected');
  quizSelected = opt;
  document.getElementById('check-btn').disabled = false;
  // 🔉 BARU: ucapkan opsi yang dipilih (English)
  speak(opt, { pitch: 1.5, rate: 0.85 });
}

function checkAnswer() {
  if (!quizSelected || quizChecked) return;
  quizChecked = true;
  const q = quizQuestions[quizIdx];
  const fb = document.getElementById('quiz-feedback');
  const allOpts = document.querySelectorAll('#options-box .option');
  allOpts.forEach(o => {
    o.classList.add('disabled');
    o.classList.remove('selected');
    if (o.dataset.value === q.ans) o.classList.add('correct');
    else if (o.dataset.value === quizSelected) o.classList.add('incorrect');
  });

  if (quizSelected === q.ans) {
    quizCorrect++;
    fb.className = 'feedback show correct';
    fb.textContent = '✅ Excellent! Jawabanmu benar.';
    // 🔉 puji dalam English dengan suara anak
    speakLater('Excellent! Correct!', 500, { pitch: 1.5, rate: 0.85 });
  } else {
    fb.className = 'feedback show incorrect';
    fb.textContent = '💡 Jawaban yang benar: ' + q.ans;
    // 🔉 ucapkan jawaban benar dengan suara anak (setelah delay)
    speakLater(q.ans, 700, { pitch: 1.5, rate: 0.85 });
  }

  document.getElementById('check-btn').style.display = 'none';
  document.getElementById('next-btn').style.display = 'inline-block';
  document.getElementById('next-btn').textContent = (quizIdx === quizQuestions.length - 1) ? 'See Result 🏁' : 'Next Question ▶';
}

function nextQuestion() {
  if (quizIdx < quizQuestions.length - 1) {
    quizIdx++;
    renderQuizQuestion();
  } else {
    finishQuiz();
  }
}

function finishQuiz() {
  document.getElementById('quiz-box').style.display = 'none';
  const resultBox = document.getElementById('quiz-result-box');
  resultBox.style.display = 'block';

  const score = Math.round((quizCorrect / quizQuestions.length) * 100);
  const wrong = quizQuestions.length - quizCorrect;

  state.lastQuizScore = score;
  if (state.bestQuizScore === null || score > state.bestQuizScore) state.bestQuizScore = score;

  if (!state.quizCompletedOnce) {
    state.quizCompletedOnce = true;
    state.stars += 1;
  }
  if (score >= 80 && !state.badges.includes('master')) {
    state.badges.push('master');
    state.stars += 2;
    confetti();
    showToast('👑 Badge "Greeting Master" diperoleh!');
    speakLater('Wow! You are a Greeting Master!', 900, { pitch: 1.5, rate: 0.85 });
  }
  saveState();

  document.getElementById('result-score').textContent = score;
  document.getElementById('result-detail').textContent = `Benar: ${quizCorrect} soal · Salah: ${wrong} soal`;

  let msg = '', badge = '🌟', speechMsg = '';
  if (score === 100) { msg = 'Perfect! Kamu luar biasa! 🎉'; badge = '🏆'; confetti(); speechMsg = 'Perfect! You are amazing!'; }
  else if (score >= 80) { msg = 'Great job! Kamu hebat! 👏'; badge = '👑'; speechMsg = 'Great job! You did very well!'; }
  else if (score >= 60) { msg = 'Good effort! Terus berlatih ya! 💪'; badge = '⭐'; speechMsg = 'Good effort! Keep practicing!'; }
  else { msg = 'Keep trying! Jangan menyerah! 🌱'; badge = '🌱'; speechMsg = 'Keep trying! Do not give up!'; }

  document.getElementById('result-msg').textContent = msg;
  document.getElementById('result-badge').textContent = badge;
  // 🔉 ucapkan pesan motivasi (English) dengan suara anak
  setTimeout(() => speak(speechMsg, { pitch: 1.5, rate: 0.85 }), 600);
}

/* ============ INIT ============ */
function init() {
  loadState();
  renderLearnCards();
  updateProgressUI();
  initMatch();
  initDialogue();
  initChoose();
  initTalk();
}

document.addEventListener('DOMContentLoaded', init);
</script>
</body>
</html>
