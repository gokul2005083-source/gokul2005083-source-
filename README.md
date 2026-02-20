<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GOKUL RAJ — Ultra Pro Resume 2030</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Exo+2:wght@300;400;600;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --green: #00ff88;
    --green2: #00cc66;
    --teal: #00e5ff;
    --gold: #ffd700;
    --dark: #020c06;
    --dark2: #041a0c;
    --dark3: #071f0f;
    --panel: rgba(0,255,136,0.04);
    --border: rgba(0,255,136,0.18);
    --text: #c8f5dc;
    --muted: #6b9e7a;
    --glow: 0 0 20px rgba(0,255,136,0.4);
    --glow2: 0 0 40px rgba(0,255,136,0.2);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--dark);
    color: var(--text);
    font-family: 'Exo 2', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom cursor */
  .cursor {
    position: fixed;
    width: 10px; height: 10px;
    background: var(--green);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%,-50%);
    box-shadow: var(--glow);
    transition: transform 0.1s;
  }
  .cursor-ring {
    position: fixed;
    width: 36px; height: 36px;
    border: 1px solid rgba(0,255,136,0.5);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9998;
    transform: translate(-50%,-50%);
    transition: all 0.15s ease;
  }

  /* Animated background */
  .bg-grid {
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,136,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,136,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    z-index: 0;
    animation: gridShift 20s linear infinite;
  }
  @keyframes gridShift {
    0% { background-position: 0 0; }
    100% { background-position: 60px 60px; }
  }

  /* DNA helix background */
  .dna-canvas {
    position: fixed;
    right: 0; top: 0;
    width: 300px; height: 100%;
    opacity: 0.12;
    z-index: 0;
  }

  /* Floating particles */
  .particle {
    position: fixed;
    width: 3px; height: 3px;
    background: var(--green);
    border-radius: 50%;
    animation: float linear infinite;
    opacity: 0.5;
    z-index: 0;
  }
  @keyframes float {
    0% { transform: translateY(100vh) translateX(0); opacity: 0; }
    10% { opacity: 0.5; }
    90% { opacity: 0.3; }
    100% { transform: translateY(-100px) translateX(var(--drift)); opacity: 0; }
  }

  /* Main layout */
  .container {
    position: relative;
    z-index: 1;
    max-width: 1200px;
    margin: 0 auto;
    padding: 40px 30px;
  }

  /* HEADER */
  .header {
    position: relative;
    padding: 60px 0 50px;
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: center;
    gap: 40px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 60px;
    opacity: 0;
    animation: fadeSlideDown 0.8s ease forwards;
  }

  .header::before {
    content: '';
    position: absolute;
    bottom: -1px; left: 0;
    width: 0%;
    height: 1px;
    background: var(--green);
    animation: lineGrow 1.2s ease forwards 0.3s;
    box-shadow: var(--glow);
  }
  @keyframes lineGrow {
    to { width: 100%; }
  }

  .header-badge {
    display: flex;
    align-items: center;
    gap: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--green);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 16px;
  }
  .badge-dot {
    width: 8px; height: 8px;
    background: var(--green);
    border-radius: 50%;
    box-shadow: var(--glow);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0%, 100% { transform: scale(1); opacity: 1; }
    50% { transform: scale(1.5); opacity: 0.5; }
  }

  .name {
    font-family: 'Orbitron', monospace;
    font-size: clamp(42px, 6vw, 80px);
    font-weight: 900;
    letter-spacing: 8px;
    line-height: 1;
    text-transform: uppercase;
    background: linear-gradient(135deg, #ffffff 0%, var(--green) 50%, var(--teal) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    filter: drop-shadow(0 0 30px rgba(0,255,136,0.4));
    animation: nameGlow 3s ease-in-out infinite alternate;
  }
  @keyframes nameGlow {
    from { filter: drop-shadow(0 0 20px rgba(0,255,136,0.3)); }
    to { filter: drop-shadow(0 0 50px rgba(0,255,136,0.7)); }
  }

  .tagline {
    font-family: 'Exo 2', sans-serif;
    font-size: 14px;
    font-weight: 400;
    letter-spacing: 5px;
    color: var(--muted);
    text-transform: uppercase;
    margin-top: 12px;
  }
  .tagline span {
    color: var(--green);
  }

  .contact-grid {
    display: flex;
    flex-direction: column;
    gap: 10px;
    text-align: right;
  }
  .contact-item {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    gap: 8px;
    transition: color 0.3s;
  }
  .contact-item:hover { color: var(--green); }
  .contact-item .icon {
    width: 20px; height: 20px;
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    font-size: 9px;
    color: var(--green);
  }

  /* Section layout */
  .main-grid {
    display: grid;
    grid-template-columns: 300px 1fr;
    gap: 50px;
  }

  /* Section titles */
  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 5px;
    text-transform: uppercase;
    color: var(--green);
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }
  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }
  .section-title .num {
    color: rgba(0,255,136,0.4);
    font-size: 9px;
  }

  /* Panel cards */
  .panel {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 24px;
    position: relative;
    clip-path: polygon(0 0, calc(100% - 16px) 0, 100% 16px, 100% 100%, 16px 100%, 0 calc(100% - 16px));
    transition: border-color 0.3s, background 0.3s;
    margin-bottom: 24px;
  }
  .panel::before {
    content: '';
    position: absolute;
    inset: 0;
    clip-path: polygon(0 0, calc(100% - 16px) 0, 100% 16px, 100% 100%, 16px 100%, 0 calc(100% - 16px));
    background: linear-gradient(135deg, rgba(0,255,136,0.06), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .panel:hover {
    border-color: rgba(0,255,136,0.4);
    box-shadow: var(--glow2), inset 0 0 30px rgba(0,255,136,0.03);
  }
  .panel:hover::before { opacity: 1; }

  .corner-dot {
    position: absolute;
    top: -1px; right: -1px;
    width: 4px; height: 4px;
    background: var(--green);
    box-shadow: var(--glow);
  }
  .corner-dot2 {
    position: absolute;
    bottom: -1px; left: -1px;
    width: 4px; height: 4px;
    background: var(--green);
    box-shadow: var(--glow);
  }

  /* Skills */
  .skill-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 12px;
    border: 1px solid rgba(0,255,136,0.2);
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text);
    letter-spacing: 1px;
    margin: 4px 3px;
    clip-path: polygon(6px 0, 100% 0, calc(100% - 6px) 100%, 0 100%);
    background: rgba(0,255,136,0.04);
    transition: all 0.3s;
    cursor: default;
  }
  .skill-tag:hover {
    background: rgba(0,255,136,0.12);
    border-color: var(--green);
    color: var(--green);
    box-shadow: var(--glow);
    transform: translateY(-2px);
  }
  .skill-tag .dot {
    width: 5px; height: 5px;
    background: var(--green);
    border-radius: 50%;
    box-shadow: var(--glow);
    flex-shrink: 0;
  }

  /* Skill category header */
  .skill-cat {
    font-family: 'Orbitron', monospace;
    font-size: 8px;
    letter-spacing: 3px;
    color: rgba(0,255,136,0.5);
    text-transform: uppercase;
    margin-top: 16px;
    margin-bottom: 8px;
  }

  /* Summary */
  .summary-text {
    font-size: 14px;
    line-height: 1.9;
    color: var(--text);
    border-left: 2px solid var(--green);
    padding-left: 20px;
    position: relative;
  }
  .summary-text::before {
    content: '"';
    font-size: 60px;
    font-family: 'Orbitron', monospace;
    color: rgba(0,255,136,0.1);
    position: absolute;
    top: -10px; left: 10px;
    line-height: 1;
  }

  /* Experience */
  .exp-item {
    position: relative;
    padding: 24px;
    background: var(--panel);
    border: 1px solid var(--border);
    margin-bottom: 20px;
    clip-path: polygon(0 0, calc(100% - 20px) 0, 100% 20px, 100% 100%, 20px 100%, 0 calc(100% - 20px));
    transition: all 0.3s;
  }
  .exp-item:hover {
    border-color: rgba(0,255,136,0.4);
    box-shadow: var(--glow2);
    transform: translateX(4px);
  }

  .exp-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 12px;
  }
  .exp-title {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 700;
    color: #fff;
    letter-spacing: 1px;
  }
  .exp-company {
    font-size: 12px;
    color: var(--green);
    margin-top: 4px;
    font-family: 'Space Mono', monospace;
  }
  .exp-date {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 2px;
    background: rgba(0,255,136,0.07);
    border: 1px solid var(--border);
    padding: 4px 10px;
    white-space: nowrap;
  }

  .exp-bullet {
    position: relative;
    font-size: 13px;
    color: var(--text);
    padding-left: 20px;
    margin-top: 8px;
    line-height: 1.7;
    opacity: 0.85;
  }
  .exp-bullet::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: var(--green);
    font-size: 10px;
    top: 2px;
  }

  /* Projects grid */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 8px;
  }

  .project-card {
    position: relative;
    padding: 20px;
    background: rgba(0,255,136,0.03);
    border: 1px solid var(--border);
    clip-path: polygon(0 0, calc(100% - 14px) 0, 100% 14px, 100% 100%, 14px 100%, 0 calc(100% - 14px));
    overflow: hidden;
    transition: all 0.3s;
    cursor: default;
  }
  .project-card::after {
    content: '';
    position: absolute;
    top: -50%; left: -50%;
    width: 200%; height: 200%;
    background: radial-gradient(circle, rgba(0,255,136,0.06) 0%, transparent 70%);
    opacity: 0;
    transition: opacity 0.4s;
  }
  .project-card:hover {
    border-color: rgba(0,255,136,0.5);
    box-shadow: var(--glow2), 0 20px 40px rgba(0,0,0,0.4);
    transform: translateY(-4px);
  }
  .project-card:hover::after { opacity: 1; }

  .project-icon {
    font-size: 24px;
    margin-bottom: 10px;
    display: block;
  }
  .project-name {
    font-family: 'Orbitron', monospace;
    font-size: 11px;
    font-weight: 700;
    color: #fff;
    letter-spacing: 1px;
    margin-bottom: 8px;
  }
  .project-desc {
    font-size: 11px;
    color: var(--muted);
    line-height: 1.6;
  }

  /* Certs */
  .cert-item {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 12px 16px;
    border: 1px solid var(--border);
    margin-bottom: 10px;
    background: rgba(0,255,136,0.03);
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }
  .cert-item::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 2px;
    background: var(--green);
    box-shadow: var(--glow);
  }
  .cert-item:hover {
    border-color: rgba(0,255,136,0.4);
    transform: translateX(4px);
    background: rgba(0,255,136,0.06);
  }
  .cert-name {
    font-family: 'Exo 2', sans-serif;
    font-size: 12px;
    font-weight: 600;
    color: var(--text);
    flex: 1;
  }
  .cert-issuer {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--green);
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  /* Stat bars */
  .stat-item {
    margin-bottom: 16px;
  }
  .stat-header {
    display: flex;
    justify-content: space-between;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    margin-bottom: 6px;
    letter-spacing: 1px;
  }
  .stat-header span:last-child { color: var(--green); }
  .stat-bar {
    height: 2px;
    background: rgba(0,255,136,0.1);
    position: relative;
    overflow: hidden;
  }
  .stat-fill {
    position: absolute;
    top: 0; left: 0;
    height: 100%;
    background: linear-gradient(90deg, var(--green), var(--teal));
    box-shadow: 0 0 8px var(--green);
    width: 0%;
    transition: width 1.5s cubic-bezier(0.4, 0, 0.2, 1);
  }

  /* Education */
  .edu-card {
    background: linear-gradient(135deg, rgba(0,255,136,0.06), rgba(0,229,255,0.03));
    border: 1px solid rgba(0,255,136,0.2);
    padding: 24px;
    position: relative;
    clip-path: polygon(0 0, calc(100% - 20px) 0, 100% 20px, 100% 100%, 0 100%);
  }
  .edu-card::after {
    content: 'B.TECH';
    position: absolute;
    right: 20px; top: 20px;
    font-family: 'Orbitron', monospace;
    font-size: 8px;
    color: rgba(0,255,136,0.2);
    letter-spacing: 4px;
    transform: rotate(-5deg);
    font-weight: 900;
  }

  /* Strengths hexagon-like */
  .strengths-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  .strength-item {
    padding: 12px;
    border: 1px solid var(--border);
    font-size: 11px;
    color: var(--text);
    display: flex;
    align-items: center;
    gap: 8px;
    transition: all 0.3s;
    background: rgba(0,255,136,0.02);
  }
  .strength-item:hover {
    border-color: rgba(0,255,136,0.4);
    background: rgba(0,255,136,0.07);
    color: #fff;
  }
  .strength-item::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--green);
    transform: rotate(45deg);
    flex-shrink: 0;
    box-shadow: var(--glow);
  }

  /* Animations */
  @keyframes fadeSlideDown {
    from { opacity: 0; transform: translateY(-30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeSlideUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }

  .sidebar { animation: fadeSlideUp 0.8s ease forwards 0.4s; opacity: 0; }
  .main-content { animation: fadeSlideUp 0.8s ease forwards 0.6s; opacity: 0; }

  /* Scan line effect */
  body::after {
    content: '';
    position: fixed;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, transparent, var(--green), transparent);
    animation: scanLine 4s linear infinite;
    z-index: 100;
    pointer-events: none;
    opacity: 0.5;
  }
  @keyframes scanLine {
    0% { top: 0; opacity: 0.5; }
    80% { opacity: 0.3; }
    100% { top: 100%; opacity: 0; }
  }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--dark); }
  ::-webkit-scrollbar-thumb { background: var(--green); border-radius: 2px; }

  /* HUD elements */
  .hud-corner {
    position: fixed;
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: rgba(0,255,136,0.3);
    letter-spacing: 2px;
    z-index: 5;
  }
  .hud-tl { top: 16px; left: 20px; }
  .hud-tr { top: 16px; right: 20px; text-align: right; }
  .hud-bl { bottom: 16px; left: 20px; }
  .hud-br { bottom: 16px; right: 20px; text-align: right; }

  .data-stream {
    font-family: 'Space Mono', monospace;
    font-size: 8px;
    color: rgba(0,255,136,0.15);
    letter-spacing: 1px;
    line-height: 1.4;
    animation: dataFlicker 3s steps(1) infinite;
  }
  @keyframes dataFlicker {
    0%, 100% { opacity: 0.15; }
    50% { opacity: 0.25; }
  }

  /* Glitch effect on name hover */
  .name:hover {
    animation: glitch 0.5s steps(2) forwards, nameGlow 3s ease-in-out infinite alternate;
  }
  @keyframes glitch {
    0% { text-shadow: 2px 0 var(--green), -2px 0 var(--teal); }
    25% { text-shadow: -4px 0 var(--teal), 4px 0 var(--green); }
    50% { text-shadow: 4px 2px var(--green), -4px -2px var(--teal); }
    75% { text-shadow: -2px 0 var(--green), 2px 0 var(--teal); }
    100% { text-shadow: none; }
  }

  /* Typing cursor */
  .typing-cursor::after {
    content: '|';
    animation: blink 1s step-end infinite;
    color: var(--green);
  }
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  /* Node network visual */
  .network-vis {
    position: relative;
    height: 80px;
    margin-bottom: 20px;
    overflow: hidden;
  }
  .network-vis canvas {
    width: 100%;
    height: 100%;
  }

  @media (max-width: 768px) {
    .main-grid { grid-template-columns: 1fr; }
    .projects-grid { grid-template-columns: 1fr; }
    .header { grid-template-columns: 1fr; }
    .contact-grid { text-align: left; }
    .contact-item { justify-content: flex-start; }
    .name { font-size: 36px; letter-spacing: 4px; }
  }
</style>
</head>
<body>

<!-- Custom cursor -->
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- Animated grid background -->
<div class="bg-grid"></div>

<!-- HUD corners -->
<div class="hud-corner hud-tl">
  <div>SYSTEM // ONLINE</div>
  <div class="data-stream" id="sysTime">--:--:--</div>
</div>
<div class="hud-corner hud-tr">
  <div>GR-2026 // AGRI-AI</div>
  <div class="data-stream">VERSION 3.0.1</div>
</div>
<div class="hud-corner hud-bl">
  <div class="data-stream">AGR_ENG // DATA_ANALYST</div>
</div>
<div class="hud-corner hud-br">
  <div class="data-stream">PONDICHERRY // INDIA</div>
</div>

<!-- Floating particles -->
<div id="particles"></div>

<div class="container">

  <!-- HEADER -->
  <header class="header">
    <div>
      <div class="header-badge">
        <div class="badge-dot"></div>
        <span>Profile // Active</span>
        <span style="color: rgba(0,255,136,0.4)">·</span>
        <span>B.Tech Agricultural Engineering</span>
      </div>
      <h1 class="name" id="mainName">GOKUL RAJ</h1>
      <p class="tagline">
        <span>Agricultural Engineering</span> · Data Analyst · <span>AI Enthusiast</span>
      </p>
    </div>
    <div class="contact-grid">
      <div class="contact-item">
        <span>+91 8807844079</span>
        <div class="icon">📞</div>
      </div>
      <div class="contact-item">
        <span>gokul2005.08.3@gmail.com</span>
        <div class="icon">✉</div>
      </div>
      <div class="contact-item">
        <span>github.com/gokul2005083-source</span>
        <div class="icon">⌗</div>
      </div>
      <div class="contact-item">
        <span>Pondicherry — 605009</span>
        <div class="icon">◎</div>
      </div>
    </div>
  </header>

  <!-- MAIN GRID -->
  <div class="main-grid">

    <!-- SIDEBAR -->
    <aside class="sidebar">

      <!-- Summary panel -->
      <div class="section-title">
        <span class="num">01</span> Profile
      </div>
      <div class="panel" style="margin-bottom: 36px;">
        <div class="corner-dot"></div>
        <div class="corner-dot2"></div>
        <p class="summary-text">
          Dynamic Agricultural Engineering student and Data Analyst with dual expertise spanning precision agriculture and advanced data science. Passionate about bridging the gap between agri-tech and data-driven innovation.
        </p>
      </div>

      <!-- Proficiency bars -->
      <div class="section-title">
        <span class="num">02</span> Proficiency
      </div>
      <div class="panel" style="margin-bottom: 36px;" id="skillBars">
        <div class="corner-dot"></div>
        <div class="stat-item">
          <div class="stat-header"><span>Python / Pandas</span><span>90%</span></div>
          <div class="stat-bar"><div class="stat-fill" data-width="90"></div></div>
        </div>
        <div class="stat-item">
          <div class="stat-header"><span>Power BI / Excel</span><span>88%</span></div>
          <div class="stat-bar"><div class="stat-fill" data-width="88"></div></div>
        </div>
        <div class="stat-item">
          <div class="stat-header"><span>Machine Learning</span><span>80%</span></div>
          <div class="stat-bar"><div class="stat-fill" data-width="80"></div></div>
        </div>
        <div class="stat-item">
          <div class="stat-header"><span>Agricultural Eng.</span><span>92%</span></div>
          <div class="stat-bar"><div class="stat-fill" data-width="92"></div></div>
        </div>
        <div class="stat-item">
          <div class="stat-header"><span>SQL / Data Pipelines</span><span>82%</span></div>
          <div class="stat-bar"><div class="stat-fill" data-width="82"></div></div>
        </div>
        <div class="stat-item">
          <div class="stat-header"><span>Deep Learning</span><span>72%</span></div>
          <div class="stat-bar"><div class="stat-fill" data-width="72"></div></div>
        </div>
      </div>

      <!-- Skills -->
      <div class="section-title">
        <span class="num">03</span> Tech Stack
      </div>
      <div class="panel" style="margin-bottom: 36px;">
        <div class="corner-dot"></div>
        <div class="skill-cat">Programming</div>
        <span class="skill-tag"><span class="dot"></span>Python</span>
        <span class="skill-tag"><span class="dot"></span>SQL</span>
        <span class="skill-tag"><span class="dot"></span>Pandas</span>
        <span class="skill-tag"><span class="dot"></span>Matplotlib</span>
        <span class="skill-tag"><span class="dot"></span>Seaborn</span>
        <span class="skill-tag"><span class="dot"></span>C</span>
        <span class="skill-tag"><span class="dot"></span>Git</span>

        <div class="skill-cat">Data & BI</div>
        <span class="skill-tag"><span class="dot"></span>Power BI</span>
        <span class="skill-tag"><span class="dot"></span>Excel</span>
        <span class="skill-tag"><span class="dot"></span>Power Query</span>
        <span class="skill-tag"><span class="dot"></span>Pipelines</span>
        <span class="skill-tag"><span class="dot"></span>Predictive Analytics</span>

        <div class="skill-cat">AI / LLM Tools</div>
        <span class="skill-tag"><span class="dot"></span>ML / DL</span>
        <span class="skill-tag"><span class="dot"></span>ChatGPT</span>
        <span class="skill-tag"><span class="dot"></span>Claude AI</span>
        <span class="skill-tag"><span class="dot"></span>Gemini</span>
        <span class="skill-tag"><span class="dot"></span>NotebookLM</span>

        <div class="skill-cat">Agricultural Eng.</div>
        <span class="skill-tag"><span class="dot"></span>Precision Agri</span>
        <span class="skill-tag"><span class="dot"></span>Irrigation Design</span>
        <span class="skill-tag"><span class="dot"></span>Soil & Water</span>
        <span class="skill-tag"><span class="dot"></span>Farm Machinery</span>
        <span class="skill-tag"><span class="dot"></span>Greenhouse Tech</span>
        <span class="skill-tag"><span class="dot"></span>Organic Farming</span>
        <span class="skill-tag"><span class="dot"></span>Beekeeping</span>
      </div>

      <!-- Education -->
      <div class="section-title">
        <span class="num">04</span> Education
      </div>
      <div class="edu-card">
        <div style="font-family: 'Orbitron', monospace; font-size: 12px; font-weight: 700; color: #fff; margin-bottom: 6px;">B.TECH — AGRICULTURAL ENGINEERING</div>
        <div style="font-family: 'Space Mono', monospace; font-size: 10px; color: var(--green); margin-bottom: 10px;">2022 — 2026</div>
        <div style="font-size: 12px; color: var(--muted); line-height: 1.6;">Perunthalaivar Kamarajar Institute of Engineering & Technology</div>
      </div>

      <!-- Strengths -->
      <div class="section-title" style="margin-top: 32px;">
        <span class="num">05</span> Strengths
      </div>
      <div class="strengths-grid">
        <div class="strength-item">Field Knowledge</div>
        <div class="strength-item">Modern Farming</div>
        <div class="strength-item">Farmer Comms</div>
        <div class="strength-item">Team Work</div>
        <div class="strength-item">Data Driven</div>
        <div class="strength-item">Problem Solving</div>
      </div>

    </aside>

    <!-- MAIN CONTENT -->
    <main class="main-content">

      <!-- Experience -->
      <div class="section-title">
        <span class="num">06</span> Experience
      </div>

      <div class="exp-item">
        <div class="corner-dot"></div>
        <div class="exp-header">
          <div>
            <div class="exp-title">DATA ANALYTICS INTERN</div>
            <div class="exp-company">▸ Novitech R&D Pvt Ltd, Pondicherry</div>
          </div>
          <div class="exp-date">2024</div>
        </div>
        <div class="exp-bullet">Designed and delivered interactive Power BI dashboards enabling real-time business performance monitoring</div>
        <div class="exp-bullet">Conducted trend analysis and comparative studies to extract actionable business insights</div>
        <div class="exp-bullet">Built end-to-end data pipelines for cleaning, transforming, and visualizing raw datasets</div>
        <div class="exp-bullet">Collaborated with cross-functional teams to present data-driven recommendations to stakeholders</div>
      </div>

      <div class="exp-item">
        <div class="corner-dot"></div>
        <div class="exp-header">
          <div>
            <div class="exp-title">AGRICULTURAL ENGINEERING INTERN</div>
            <div class="exp-company">▸ ICAR — Krishi Vigyan Kendra, Puducherry</div>
          </div>
          <div class="exp-date">2023 — 2024</div>
        </div>
        <div class="exp-bullet">Gained hands-on exposure to sustainable farming systems and organic cultivation techniques</div>
        <div class="exp-bullet">Assisted in field-level implementation of precision agriculture tools and smart irrigation systems</div>
        <div class="exp-bullet">Participated in farmer education initiatives and rural extension outreach programs</div>
        <div class="exp-bullet">Supported crop management, greenhouse operations, and soil health monitoring activities</div>
      </div>

      <div class="exp-item">
        <div class="corner-dot"></div>
        <div class="exp-header">
          <div>
            <div class="exp-title">AI & ML RESEARCH</div>
            <div class="exp-company">▸ Self-Initiated / Private Projects</div>
          </div>
          <div class="exp-date">2023 — PRESENT</div>
        </div>
        <div class="exp-bullet">Developed supervised and unsupervised machine learning models for real-world datasets</div>
        <div class="exp-bullet">Applied deep learning techniques for predictive analytics and pattern recognition</div>
        <div class="exp-bullet">Experimented with LLM tools (ChatGPT, Claude, Gemini) for automation workflows</div>
      </div>

      <!-- Projects -->
      <div class="section-title" style="margin-top: 40px;">
        <span class="num">07</span> Key Projects
      </div>

      <div class="projects-grid">
        <div class="project-card">
          <span class="project-icon">📊</span>
          <div class="project-name">BOOK SALES DATA ANALYSIS</div>
          <div class="project-desc">Sales trend analysis & visualization using Python, Pandas, and Matplotlib with deep market insights</div>
        </div>
        <div class="project-card">
          <span class="project-icon">🎵</span>
          <div class="project-name">TAMIL ARTISTS STREAMING</div>
          <div class="project-desc">Streaming pattern analysis using Python & Seaborn with comparative interactive dashboards</div>
        </div>
        <div class="project-card">
          <span class="project-icon">🎬</span>
          <div class="project-name">AMAZON PRIME CONTENT</div>
          <div class="project-desc">Global content distribution & genre analysis using Power BI with interactive visual stories</div>
        </div>
        <div class="project-card">
          <span class="project-icon">🦠</span>
          <div class="project-name">COVID-19 ANALYTICS PIPELINE</div>
          <div class="project-desc">End-to-end data pipeline with predictive modeling and interactive visualizations</div>
        </div>
        <div class="project-card" style="grid-column: 1 / -1;">
          <span class="project-icon">🏍</span>
          <div class="project-name">TOP 10 POPULAR BIKES DASHBOARD</div>
          <div class="project-desc">Interactive Power BI dashboard with KPIs, slicers & comparison visuals — comprehensive market analysis with drill-through capabilities</div>
        </div>
      </div>

      <!-- Certifications -->
      <div class="section-title" style="margin-top: 40px;">
        <span class="num">08</span> Certifications
      </div>

      <div class="cert-item">
        <div style="flex:1;">
          <div class="cert-name">IBM — Data Fundamentals</div>
        </div>
        <div class="cert-issuer">IBM</div>
      </div>
      <div class="cert-item">
        <div style="flex:1;">
          <div class="cert-name">Gemini Certified University Student</div>
        </div>
        <div class="cert-issuer">Google</div>
      </div>
      <div class="cert-item">
        <div style="flex:1;">
          <div class="cert-name">AI is Revolutionizing Every Field</div>
        </div>
        <div class="cert-issuer">Online</div>
      </div>
      <div class="cert-item">
        <div style="flex:1;">
          <div class="cert-name">Microsoft Power BI Certifications</div>
        </div>
        <div class="cert-issuer">Microsoft</div>
      </div>
      <div class="cert-item">
        <div style="flex:1;">
          <div class="cert-name">Data Visualization Certification</div>
        </div>
        <div class="cert-issuer">Online</div>
      </div>

      <!-- Workshops -->
      <div class="section-title" style="margin-top: 40px;">
        <span class="num">09</span> Workshops
      </div>
      <div class="panel">
        <div class="corner-dot"></div>
        <div class="exp-bullet" style="font-size: 13px;">ICAR Agricultural Training Programs</div>
        <div class="exp-bullet" style="font-size: 13px;">Savishkar National Workshop — R.V. College of Engineering</div>
        <div class="exp-bullet" style="font-size: 13px;">Agricultural Innovation & Sustainability Programs</div>
      </div>

    </main>
  </div>

</div>

<script>
// Custom cursor
const cursor = document.getElementById('cursor');
const cursorRing = document.getElementById('cursorRing');
let mx = 0, my = 0, rx = 0, ry = 0;

document.addEventListener('mousemove', e => {
  mx = e.clientX; my = e.clientY;
  cursor.style.left = mx + 'px';
  cursor.style.top = my + 'px';
});

function animateRing() {
  rx += (mx - rx) * 0.12;
  ry += (my - ry) * 0.12;
  cursorRing.style.left = rx + 'px';
  cursorRing.style.top = ry + 'px';
  requestAnimationFrame(animateRing);
}
animateRing();

document.querySelectorAll('a, button, .skill-tag, .project-card, .cert-item, .exp-item').forEach(el => {
  el.addEventListener('mouseenter', () => {
    cursorRing.style.transform = 'translate(-50%,-50%) scale(1.5)';
    cursorRing.style.borderColor = 'rgba(0,255,136,0.8)';
  });
  el.addEventListener('mouseleave', () => {
    cursorRing.style.transform = 'translate(-50%,-50%) scale(1)';
    cursorRing.style.borderColor = 'rgba(0,255,136,0.5)';
  });
});

// Floating particles
const pContainer = document.getElementById('particles');
for (let i = 0; i < 30; i++) {
  const p = document.createElement('div');
  p.className = 'particle';
  p.style.cssText = `
    left: ${Math.random() * 100}%;
    animation-duration: ${6 + Math.random() * 10}s;
    animation-delay: ${Math.random() * 8}s;
    --drift: ${(Math.random() - 0.5) * 100}px;
    opacity: ${0.2 + Math.random() * 0.4};
    width: ${1 + Math.random() * 3}px;
    height: ${1 + Math.random() * 3}px;
  `;
  pContainer.appendChild(p);
}

// Live clock
function updateClock() {
  const now = new Date();
  document.getElementById('sysTime').textContent =
    now.toTimeString().slice(0, 8);
}
setInterval(updateClock, 1000);
updateClock();

// Animate skill bars on scroll
const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.querySelectorAll('.stat-fill').forEach(bar => {
        setTimeout(() => {
          bar.style.width = bar.dataset.width + '%';
        }, 200);
      });
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.3 });

observer.observe(document.getElementById('skillBars'));

// Stagger animation for exp items
document.querySelectorAll('.exp-item, .project-card, .cert-item, .strength-item').forEach((el, i) => {
  el.style.opacity = '0';
  el.style.transform = 'translateY(20px)';
  el.style.transition = `opacity 0.5s ease ${i * 0.08}s, transform 0.5s ease ${i * 0.08}s, border-color 0.3s, background 0.3s, box-shadow 0.3s`;

  const obs = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
        obs.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  obs.observe(el);
});

// DNA canvas animation in background
const canvas = document.createElement('canvas');
canvas.className = 'dna-canvas';
document.body.appendChild(canvas);
const ctx = canvas.getContext('2d');

function resizeDNA() {
  canvas.width = 300;
  canvas.height = window.innerHeight;
}
resizeDNA();
window.addEventListener('resize', resizeDNA);

let dnaT = 0;
function drawDNA() {
  ctx.clearRect(0, 0, 300, canvas.height);
  const nodes = 20;
  const spacing = canvas.height / nodes;

  for (let i = 0; i < nodes; i++) {
    const y = i * spacing + dnaT % spacing;
    const x1 = 80 + Math.sin(y * 0.02) * 60;
    const x2 = 80 - Math.sin(y * 0.02) * 60;

    ctx.beginPath();
    ctx.arc(x1, y, 4, 0, Math.PI * 2);
    ctx.fillStyle = '#00ff88';
    ctx.fill();

    ctx.beginPath();
    ctx.arc(x2, y, 4, 0, Math.PI * 2);
    ctx.fillStyle = '#00e5ff';
    ctx.fill();

    ctx.beginPath();
    ctx.moveTo(x1, y);
    ctx.lineTo(x2, y);
    ctx.strokeStyle = 'rgba(0,255,136,0.3)';
    ctx.lineWidth = 1;
    ctx.stroke();
  }

  // Draw helix curves
  ctx.beginPath();
  for (let y = 0; y < canvas.height; y += 2) {
    const x = 80 + Math.sin(y * 0.02 + dnaT * 0.02) * 60;
    if (y === 0) ctx.moveTo(x, y); else ctx.lineTo(x, y);
  }
  ctx.strokeStyle = 'rgba(0,255,136,0.2)';
  ctx.lineWidth = 1.5;
  ctx.stroke();

  ctx.beginPath();
  for (let y = 0; y < canvas.height; y += 2) {
    const x = 80 - Math.sin(y * 0.02 + dnaT * 0.02) * 60;
    if (y === 0) ctx.moveTo(x, y); else ctx.lineTo(x, y);
  }
  ctx.strokeStyle = 'rgba(0,229,255,0.2)';
  ctx.lineWidth = 1.5;
  ctx.stroke();

  dnaT += 0.5;
  requestAnimationFrame(drawDNA);
}
drawDNA();
</script>
</body>
</html>
