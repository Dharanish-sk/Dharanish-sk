<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dharanish SK — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #fdf6ed;
    --warm-white: #fffbf5;
    --ink: #1a1208;
    --text: #2d2416;
    --muted: #8b7355;

    --coral:   #f4694b;
    --amber:   #f0a500;
    --sage:    #5a9e7c;
    --sky:     #4a90d9;
    --violet:  #7c5cbf;
    --rose:    #e8547a;
    --teal:    #2ab3a3;
    --peach:   #f7c59f;
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--cream);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* Organic blobs background */
  .bg-canvas {
    position: fixed;
    inset: 0;
    z-index: 0;
    overflow: hidden;
    pointer-events: none;
  }

  .blob {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.18;
    animation: drift 12s ease-in-out infinite;
  }

  .blob-1 { width: 500px; height: 500px; background: var(--coral); top: -150px; left: -100px; animation-delay: 0s; }
  .blob-2 { width: 400px; height: 400px; background: var(--amber); top: 200px; right: -100px; animation-delay: -4s; }
  .blob-3 { width: 350px; height: 350px; background: var(--sage); bottom: 100px; left: 30%; animation-delay: -8s; }
  .blob-4 { width: 300px; height: 300px; background: var(--violet); bottom: -80px; right: 20%; animation-delay: -2s; }

  @keyframes drift {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33%       { transform: translate(30px, -20px) scale(1.05); }
    66%       { transform: translate(-20px, 30px) scale(0.95); }
  }

  /* ── LAYOUT ── */
  .page {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 56px 28px 80px;
  }

  /* ── HEADER ── */
  .hero {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 36px;
    align-items: center;
    margin-bottom: 56px;
    animation: slideUp 0.8s ease both;
  }

  @media (max-width: 580px) {
    .hero { grid-template-columns: 1fr; text-align: center; }
    .hero-links { justify-content: center !important; }
  }

  @keyframes slideUp {
    from { opacity: 0; transform: translateY(32px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .avatar-wrap {
    position: relative;
    width: 130px;
    height: 130px;
    flex-shrink: 0;
  }

  .avatar-bg {
    position: absolute;
    inset: -6px;
    border-radius: 50%;
    background: conic-gradient(var(--coral), var(--amber), var(--sage), var(--sky), var(--violet), var(--rose), var(--coral));
    animation: spin 6s linear infinite;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  .avatar-face {
    position: relative;
    z-index: 1;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--cream);
    border: 4px solid var(--cream);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Playfair Display', serif;
    font-size: 52px;
    font-weight: 900;
    background: linear-gradient(135deg, #fff8f0, #fdecd8);
    color: var(--coral);
    overflow: hidden;
  }

  .hero-text h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(36px, 6vw, 60px);
    font-weight: 900;
    line-height: 1.05;
    color: var(--ink);
    margin-bottom: 10px;
  }

  .hero-text h1 em {
    font-style: normal;
    background: linear-gradient(135deg, var(--coral), var(--amber));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .hero-sub {
    font-size: 15px;
    color: var(--muted);
    font-weight: 400;
    letter-spacing: 0.03em;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
    flex-wrap: wrap;
  }

  .status-dot {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(90,158,124,0.12);
    border: 1px solid rgba(90,158,124,0.3);
    border-radius: 100px;
    padding: 4px 12px;
    font-size: 12px;
    color: var(--sage);
    font-weight: 500;
  }

  .status-dot::before {
    content: '';
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--sage);
    box-shadow: 0 0 6px var(--sage);
    animation: pulse-dot 2s ease-in-out infinite;
  }

  @keyframes pulse-dot {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0.3; }
  }

  .hero-links {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .pill-btn {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 9px 20px;
    border-radius: 100px;
    font-size: 13px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.22s ease;
    border: 2px solid transparent;
    cursor: pointer;
    font-family: 'DM Sans', sans-serif;
  }

  .pill-coral  { background: var(--coral); color: #fff; }
  .pill-coral:hover  { transform: translateY(-3px); box-shadow: 0 10px 28px rgba(244,105,75,0.4); }
  .pill-sky    { background: transparent; color: var(--sky); border-color: var(--sky); }
  .pill-sky:hover    { background: var(--sky); color: #fff; transform: translateY(-3px); box-shadow: 0 10px 28px rgba(74,144,217,0.35); }
  .pill-violet { background: transparent; color: var(--violet); border-color: var(--violet); }
  .pill-violet:hover { background: var(--violet); color: #fff; transform: translateY(-3px); box-shadow: 0 10px 28px rgba(124,92,191,0.35); }

  /* ── SECTION HEADERS ── */
  .sec-head {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 24px;
  }

  .sec-icon {
    width: 40px; height: 40px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
  }

  .sec-title {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--ink);
  }

  .sec-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, currentColor, transparent);
    opacity: 0.15;
  }

  /* ── CARDS ── */
  .card {
    background: #fffdf9;
    border-radius: 20px;
    padding: 28px;
    box-shadow: 0 2px 16px rgba(26,18,8,0.06);
    border: 1.5px solid rgba(26,18,8,0.07);
    transition: transform 0.25s, box-shadow 0.25s;
  }

  .card:hover {
    transform: translateY(-5px);
    box-shadow: 0 12px 36px rgba(26,18,8,0.1);
  }

  /* ── ABOUT SECTION ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    margin-bottom: 48px;
    animation: slideUp 0.8s 0.15s ease both;
  }

  @media (max-width: 520px) { .about-grid { grid-template-columns: 1fr; } }

  .about-card {
    border-radius: 18px;
    padding: 22px 24px;
    box-shadow: 0 2px 16px rgba(0,0,0,0.05);
    position: relative;
    overflow: hidden;
    transition: transform 0.25s, box-shadow 0.25s;
  }

  .about-card:hover { transform: translateY(-4px); box-shadow: 0 10px 28px rgba(0,0,0,0.1); }

  .about-card .a-icon { font-size: 26px; margin-bottom: 10px; }
  .about-card .a-label { font-size: 11px; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; opacity: 0.55; margin-bottom: 4px; font-family: 'DM Mono', monospace; }
  .about-card .a-val   { font-size: 15px; font-weight: 600; color: var(--ink); }

  .ac-coral  { background: linear-gradient(135deg, #fff1ee, #ffe4dd); border: 1.5px solid rgba(244,105,75,0.18); }
  .ac-amber  { background: linear-gradient(135deg, #fffaee, #ffefc8); border: 1.5px solid rgba(240,165,0,0.2); }
  .ac-sage   { background: linear-gradient(135deg, #eef7f2, #d5eee3); border: 1.5px solid rgba(90,158,124,0.2); }
  .ac-sky    { background: linear-gradient(135deg, #edf4fc, #d2e7f8); border: 1.5px solid rgba(74,144,217,0.2); }

  /* ── SKILLS ── */
  .skills-section { margin-bottom: 48px; animation: slideUp 0.8s 0.25s ease both; }

  .skill-group { margin-bottom: 22px; }
  .skill-group-label {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--muted);
    font-family: 'DM Mono', monospace;
    margin-bottom: 12px;
  }

  .skill-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .skill-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 16px;
    border-radius: 100px;
    font-size: 13px;
    font-weight: 500;
    transition: all 0.22s;
    cursor: default;
    box-shadow: 0 2px 8px rgba(0,0,0,0.07);
  }

  .skill-tag:hover { transform: translateY(-3px) scale(1.05); box-shadow: 0 8px 20px rgba(0,0,0,0.14); }

  /* colorful skill tags */
  .st-coral  { background: #fff1ee; color: #c03d25; border: 1.5px solid rgba(244,105,75,0.25); }
  .st-amber  { background: #fffaee; color: #8a5e00; border: 1.5px solid rgba(240,165,0,0.3); }
  .st-sage   { background: #eef7f2; color: #2d7a55; border: 1.5px solid rgba(90,158,124,0.3); }
  .st-sky    { background: #edf4fc; color: #2563a8; border: 1.5px solid rgba(74,144,217,0.3); }
  .st-violet { background: #f3f0fa; color: #5b3da6; border: 1.5px solid rgba(124,92,191,0.3); }
  .st-rose   { background: #fdf0f4; color: #b53060; border: 1.5px solid rgba(232,84,122,0.3); }
  .st-teal   { background: #eaf7f6; color: #1a7a72; border: 1.5px solid rgba(42,179,163,0.3); }

  /* ── CURRENTLY ── */
  .currently-section { margin-bottom: 48px; animation: slideUp 0.8s 0.35s ease both; }

  .currently-list { list-style: none; display: flex; flex-direction: column; gap: 0; }

  .cl-item {
    display: flex;
    align-items: flex-start;
    gap: 18px;
    padding: 18px 0;
    border-bottom: 1px dashed rgba(139,115,85,0.2);
    transition: background 0.2s;
  }

  .cl-item:last-child { border-bottom: none; }
  .cl-item:hover { padding-left: 6px; }

  .cl-dot {
    width: 36px; height: 36px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 17px;
    flex-shrink: 0;
    margin-top: 1px;
  }

  .cl-text { font-size: 15px; color: var(--text); line-height: 1.6; padding-top: 6px; }
  .cl-text strong { color: var(--ink); }

  /* ── STATS ── */
  .stats-section { margin-bottom: 48px; animation: slideUp 0.8s 0.4s ease both; }

  .stats-imgs { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  @media (max-width: 560px) { .stats-imgs { grid-template-columns: 1fr; } }

  .stats-imgs img, .streak-img {
    width: 100%;
    border-radius: 16px;
    border: 1.5px solid rgba(26,18,8,0.07);
    transition: transform 0.25s, box-shadow 0.25s;
    box-shadow: 0 2px 16px rgba(26,18,8,0.06);
  }

  .stats-imgs img:hover, .streak-img:hover {
    transform: translateY(-4px);
    box-shadow: 0 12px 30px rgba(26,18,8,0.12);
  }

  .streak-wrap { margin-top: 14px; }
  .streak-img { display: block; }

  /* ── CONNECT ── */
  .connect-section { animation: slideUp 0.8s 0.5s ease both; }

  .connect-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 14px;
  }

  .connect-card {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 20px 22px;
    border-radius: 18px;
    text-decoration: none;
    color: var(--text);
    box-shadow: 0 2px 12px rgba(0,0,0,0.05);
    border: 1.5px solid rgba(26,18,8,0.07);
    background: #fffdf9;
    transition: all 0.25s;
  }

  .connect-card:hover { transform: translateY(-4px); }

  .cc-icon {
    width: 46px; height: 46px;
    border-radius: 13px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    flex-shrink: 0;
  }

  .cc-info .cc-label { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: 0.1em; font-family: 'DM Mono', monospace; margin-bottom: 3px; }
  .cc-info .cc-val   { font-size: 13px; font-weight: 600; color: var(--ink); word-break: break-all; }

  /* ── FOOTER ── */
  .footer {
    margin-top: 64px;
    text-align: center;
    font-size: 13px;
    color: var(--muted);
    font-family: 'DM Mono', monospace;
    letter-spacing: 0.05em;
  }

  .footer .rainbow-text {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    font-weight: 700;
    background: linear-gradient(90deg, var(--coral), var(--amber), var(--sage), var(--sky), var(--violet), var(--rose));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    display: block;
    margin-bottom: 8px;
  }

  /* ── SECTION SPACING ── */
  .section { margin-bottom: 48px; }

  /* ── TROPHIES / VIEWS ROW ── */
  .meta-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 48px;
    animation: slideUp 0.8s 0.08s ease both;
  }

  .meta-badge {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 8px 16px;
    border-radius: 100px;
    font-size: 12px;
    font-weight: 600;
    font-family: 'DM Mono', monospace;
    border: 1.5px solid;
    transition: transform 0.2s;
  }

  .meta-badge:hover { transform: scale(1.05); }
  .mb-coral  { color: var(--coral);  border-color: rgba(244,105,75,0.3);  background: rgba(244,105,75,0.08); }
  .mb-sky    { color: var(--sky);    border-color: rgba(74,144,217,0.3);  background: rgba(74,144,217,0.08); }
  .mb-sage   { color: var(--sage);   border-color: rgba(90,158,124,0.3);  background: rgba(90,158,124,0.08); }
  .mb-violet { color: var(--violet); border-color: rgba(124,92,191,0.3);  background: rgba(124,92,191,0.08); }
  .mb-amber  { color: var(--amber);  border-color: rgba(240,165,0,0.3);   background: rgba(240,165,0,0.08); }
</style>
</head>
<body>

<!-- Organic color blobs -->
<div class="bg-canvas">
  <div class="blob blob-1"></div>
  <div class="blob blob-2"></div>
  <div class="blob blob-3"></div>
  <div class="blob blob-4"></div>
</div>

<div class="page">

  <!-- ── HERO ── -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-bg"></div>
      <div class="avatar-face">D</div>
    </div>
    <div class="hero-text">
      <h1>Dharanish <em>S</em></h1>
      <div class="hero-sub">
        <span class="status-dot">Open to Opportunities</span>
        <span style="color:var(--muted);font-size:13px;">📍 Tamil Nadu, India</span>
      </div>
      <div class="hero-links">
        <a href="mailto:dharanishselvarajk@gmail.com" class="pill-btn pill-coral">✉ Email</a>
        <a href="https://www.linkedin.com/in/Dharanish-SK/" target="_blank" class="pill-btn pill-sky">💼 LinkedIn</a>
        <a href="https://github.com/dharanish-sk" target="_blank" class="pill-btn pill-violet">⚡ GitHub</a>
      </div>
    </div>
  </div>

  <!-- ── META BADGES ── -->
  <div class="meta-row">
    <span class="meta-badge mb-coral">🎓 CSE Student</span>
    <span class="meta-badge mb-sky">⚛️ Full Stack Dev</span>
    <span class="meta-badge mb-sage">🌱 Open Source</span>
    <span class="meta-badge mb-violet">🤖 AI Enthusiast</span>
    <span class="meta-badge mb-amber">🎯 Problem Solver</span>
  </div>

  <!-- ── ABOUT ── -->
  <div class="section about-grid">
    <div class="about-card ac-coral">
      <div class="a-icon">🎓</div>
      <div class="a-label">Education</div>
      <div class="a-val">Computer Science Engineering</div>
    </div>
    <div class="about-card ac-amber">
      <div class="a-icon">🌱</div>
      <div class="a-label">Currently Exploring</div>
      <div class="a-val">AI / ML + Full Stack</div>
    </div>
    <div class="about-card ac-sage">
      <div class="a-icon">💬</div>
      <div class="a-label">Ask Me About</div>
      <div class="a-val">React · Python · DSA · APIs</div>
    </div>
    <div class="about-card ac-sky">
      <div class="a-icon">⚡</div>
      <div class="a-label">Fun Fact</div>
      <div class="a-val">I debug better with lo-fi music 🎵</div>
    </div>
  </div>

  <!-- ── SKILLS ── -->
  <div class="skills-section">
    <div class="sec-head">
      <div class="sec-icon" style="background:#fff1ee;">🛠️</div>
      <div class="sec-title">Tech Stack</div>
      <div class="sec-line" style="color:var(--coral);"></div>
    </div>
    <div class="card">
      <div class="skill-group">
        <div class="skill-group-label">Frontend</div>
        <div class="skill-pills">
          <span class="skill-tag st-coral">🌐 HTML5</span>
          <span class="skill-tag st-sky">🎨 CSS3</span>
          <span class="skill-tag st-amber">⚡ JavaScript</span>
          <span class="skill-tag st-sky">🔷 TypeScript</span>
          <span class="skill-tag st-teal">⚛️ React</span>
          <span class="skill-tag st-sky">💨 Tailwind CSS</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">Backend & Database</div>
        <div class="skill-pills">
          <span class="skill-tag st-sage">🟢 Node.js</span>
          <span class="skill-tag st-sky">🐍 Python</span>
          <span class="skill-tag st-amber">☕ Java</span>
          <span class="skill-tag st-sage">🍃 MongoDB</span>
          <span class="skill-tag st-sky">🐬 MySQL</span>
        </div>
      </div>
      <div class="skill-group" style="margin-bottom:0">
        <div class="skill-group-label">Tools & Design</div>
        <div class="skill-pills">
          <span class="skill-tag st-coral">🔧 Git</span>
          <span class="skill-tag st-violet">🎯 Figma</span>
          <span class="skill-tag st-rose">📮 Postman</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ── CURRENTLY ── -->
  <div class="currently-section">
    <div class="sec-head">
      <div class="sec-icon" style="background:#eef7f2;">🚀</div>
      <div class="sec-title">Currently</div>
      <div class="sec-line" style="color:var(--sage);"></div>
    </div>
    <div class="card">
      <ul class="currently-list">
        <li class="cl-item">
          <div class="cl-dot" style="background:#fff1ee;">🔭</div>
          <div class="cl-text">Building <strong>full-stack web apps</strong> with React + Node.js</div>
        </li>
        <li class="cl-item">
          <div class="cl-dot" style="background:#eef7f2;">🌱</div>
          <div class="cl-text">Deep-diving into <strong>Machine Learning</strong> and AI development</div>
        </li>
        <li class="cl-item">
          <div class="cl-dot" style="background:#edf4fc;">👯</div>
          <div class="cl-text">Looking to collaborate on <strong>open-source projects</strong></div>
        </li>
        <li class="cl-item">
          <div class="cl-dot" style="background:#f3f0fa;">💬</div>
          <div class="cl-text">Happy to chat about <strong>Web Dev, DSA</strong>, or anything tech</div>
        </li>
        <li class="cl-item">
          <div class="cl-dot" style="background:#fdf0f4;">⚡</div>
          <div class="cl-text">Fun fact — I debug code better with <strong>lo-fi music</strong> playing 🎵</div>
        </li>
      </ul>
    </div>
  </div>

  <!-- ── GITHUB STATS ── -->
  <div class="stats-section">
    <div class="sec-head">
      <div class="sec-icon" style="background:#f3f0fa;">📊</div>
      <div class="sec-title">GitHub Analytics</div>
      <div class="sec-line" style="color:var(--violet);"></div>
    </div>
    <div class="stats-imgs">
      <img src="https://github-readme-stats.vercel.app/api?username=dharanish-sk&show_icons=true&theme=default&hide_border=true&bg_color=fffdf9&title_color=f4694b&icon_color=4a90d9&text_color=2d2416&ring_color=f4694b" alt="GitHub Stats" />
      <img src="https://github-readme-stats.vercel.app/api/top-langs?username=dharanish-sk&layout=compact&theme=default&hide_border=true&bg_color=fffdf9&title_color=f4694b&text_color=2d2416" alt="Top Languages" />
    </div>
    <div class="streak-wrap">
      <img class="streak-img" src="https://streak-stats.demolab.com?user=dharanish-sk&theme=default&hide_border=true&background=fffdf9&ring=f4694b&fire=f0a500&currStreakLabel=f4694b&sideLabels=4a90d9&dates=8b7355" alt="GitHub Streak" />
    </div>
  </div>

  <!-- ── CONNECT ── -->
  <div class="connect-section">
    <div class="sec-head">
      <div class="sec-icon" style="background:#fffaee;">🤝</div>
      <div class="sec-title">Let's Connect</div>
      <div class="sec-line" style="color:var(--amber);"></div>
    </div>
    <div class="connect-row">
      <a href="mailto:dharanishselvarajk@gmail.com" class="connect-card" style="border-color:rgba(244,105,75,0.2);">
        <div class="cc-icon" style="background:#fff1ee;">📧</div>
        <div class="cc-info">
          <div class="cc-label">Email</div>
          <div class="cc-val">dharanishselvarajk@gmail.com</div>
        </div>
      </a>
      <a href="https://www.linkedin.com/in/Dharanish-SK/" target="_blank" class="connect-card" style="border-color:rgba(74,144,217,0.2);">
        <div class="cc-icon" style="background:#edf4fc;">💼</div>
        <div class="cc-info">
          <div class="cc-label">LinkedIn</div>
          <div class="cc-val">Dharanish-SK</div>
        </div>
      </a>
      <a href="https://github.com/dharanish-sk" target="_blank" class="connect-card" style="border-color:rgba(124,92,191,0.2);">
        <div class="cc-icon" style="background:#f3f0fa;">⚡</div>
        <div class="cc-info">
          <div class="cc-label">GitHub</div>
          <div class="cc-val">dharanish-sk</div>
        </div>
      </a>
    </div>
  </div>

  <!-- ── FOOTER ── -->
  <div class="footer">
    <span class="rainbow-text">Keep shipping. Keep learning.</span>
    crafted with ❤️ by Dharanish SK &nbsp;·&nbsp; Tamil Nadu, India 🇮🇳
  </div>

</div>
</body>
</html>
