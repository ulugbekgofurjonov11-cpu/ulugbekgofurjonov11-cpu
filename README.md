<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ulugbek Gofurjonov</title>
<link href="https://fonts.googleapis.com/css2?family=Clash+Display:wght@400;500;600;700&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080c14;
    --surface: #0d1422;
    --border: #1a2540;
    --accent: #4f8ef7;
    --accent2: #7c3aed;
    --text: #e8edf5;
    --muted: #4a5568;
    --glow: rgba(79,142,247,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(79,142,247,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(79,142,247,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 780px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* HERO */
  .hero {
    text-align: center;
    padding: 80px 0 60px;
    animation: fadeUp 0.8s ease both;
  }

  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(79,142,247,0.08);
    border: 1px solid rgba(79,142,247,0.2);
    border-radius: 100px;
    padding: 6px 16px;
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 28px;
    animation: fadeUp 0.6s ease both;
  }

  .hero-tag::before {
    content: '';
    width: 6px;
    height: 6px;
    background: #22c55e;
    border-radius: 50%;
    box-shadow: 0 0 8px #22c55e;
    animation: pulse 2s infinite;
  }

  .hero h1 {
    font-family: 'Clash Display', sans-serif;
    font-size: clamp(42px, 8vw, 72px);
    font-weight: 700;
    line-height: 1.05;
    letter-spacing: -2px;
    background: linear-gradient(135deg, #ffffff 0%, #a8c4ff 50%, #7c3aed 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 16px;
    animation: fadeUp 0.7s ease 0.1s both;
  }

  .hero-sub {
    font-size: 13px;
    color: var(--muted);
    letter-spacing: 1px;
    margin-bottom: 40px;
    animation: fadeUp 0.7s ease 0.2s both;
  }

  .hero-sub span {
    color: var(--accent);
  }

  /* DIVIDER */
  .divider {
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 48px 0;
  }

  /* SECTION TITLE */
  .section-label {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* CODE BLOCK */
  .code-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
    animation: fadeUp 0.7s ease 0.3s both;
    box-shadow: 0 20px 60px rgba(0,0,0,0.4), inset 0 1px 0 rgba(255,255,255,0.03);
  }

  .code-header {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 14px 20px;
    border-bottom: 1px solid var(--border);
    background: rgba(255,255,255,0.02);
  }

  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }

  .code-filename {
    margin-left: auto;
    font-size: 11px;
    color: var(--muted);
  }

  .code-body {
    padding: 24px 28px;
    font-size: 13px;
    line-height: 2;
  }

  .c-keyword { color: #7c3aed; }
  .c-var { color: #4f8ef7; }
  .c-type { color: #22d3ee; }
  .c-string { color: #86efac; }
  .c-key { color: #e8edf5; }
  .c-comment { color: #374151; }
  .c-bool { color: #fb923c; }

  /* TECH STACK */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    gap: 12px;
    animation: fadeUp 0.7s ease 0.4s both;
  }

  .stack-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px 12px;
    text-align: center;
    transition: all 0.3s ease;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .stack-item::before {
    content: '';
    position: absolute;
    inset: 0;
    background: var(--glow);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .stack-item:hover::before { opacity: 1; }
  .stack-item:hover {
    border-color: rgba(79,142,247,0.4);
    transform: translateY(-4px);
    box-shadow: 0 12px 30px rgba(79,142,247,0.1);
  }

  .stack-icon { font-size: 26px; margin-bottom: 8px; display: block; }
  .stack-name { font-size: 10px; color: var(--muted); letter-spacing: 1px; text-transform: uppercase; }

  /* STATS */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    animation: fadeUp 0.7s ease 0.5s both;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s;
  }

  .stat-card:hover { border-color: rgba(79,142,247,0.3); }

  .stat-card::after {
    content: '';
    position: absolute;
    top: -30px;
    right: -30px;
    width: 80px;
    height: 80px;
    background: radial-gradient(circle, rgba(79,142,247,0.08), transparent 70%);
    border-radius: 50%;
  }

  .stat-num {
    font-family: 'Clash Display', sans-serif;
    font-size: 36px;
    font-weight: 700;
    color: var(--text);
    line-height: 1;
    margin-bottom: 6px;
  }

  .stat-label { font-size: 11px; color: var(--muted); letter-spacing: 1px; }

  /* CONTACT */
  .contact-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    animation: fadeUp 0.7s ease 0.6s both;
  }

  .contact-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 18px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    color: var(--text);
    text-decoration: none;
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    transition: all 0.25s ease;
    letter-spacing: 0.5px;
  }

  .contact-btn:hover {
    background: rgba(79,142,247,0.08);
    border-color: rgba(79,142,247,0.4);
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(79,142,247,0.1);
  }

  .contact-btn svg { width: 14px; height: 14px; }

  /* CONTRIBUTION GRAPH */
  .graph-container {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    animation: fadeUp 0.7s ease 0.7s both;
    overflow: hidden;
  }

  .graph-title {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .graph {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    gap: 3px;
  }

  .graph-col { display: flex; flex-direction: column; gap: 3px; }

  .graph-cell {
    width: 100%;
    aspect-ratio: 1;
    border-radius: 2px;
    background: #161b22;
    transition: transform 0.2s;
  }

  .graph-cell:hover { transform: scale(1.4); }
  .graph-cell.l1 { background: #0e4429; }
  .graph-cell.l2 { background: #006d32; }
  .graph-cell.l3 { background: #26a641; }
  .graph-cell.l4 { background: #39d353; }

  /* FOOTER */
  .footer {
    text-align: center;
    padding: 48px 0 24px;
    animation: fadeUp 0.7s ease 0.8s both;
  }

  .follow-badge {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: linear-gradient(135deg, rgba(79,142,247,0.1), rgba(124,58,237,0.1));
    border: 1px solid rgba(79,142,247,0.25);
    border-radius: 100px;
    padding: 12px 28px;
    font-size: 13px;
    color: var(--text);
    cursor: pointer;
    transition: all 0.3s;
    text-decoration: none;
    animation: glowPulse 3s infinite;
  }

  .follow-badge:hover {
    background: linear-gradient(135deg, rgba(79,142,247,0.2), rgba(124,58,237,0.2));
    transform: scale(1.04);
    box-shadow: 0 0 30px rgba(79,142,247,0.2);
  }

  .follow-dot {
    width: 8px;
    height: 8px;
    background: var(--accent);
    border-radius: 50%;
    box-shadow: 0 0 10px var(--accent);
    animation: pulse 1.5s infinite;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  @keyframes glowPulse {
    0%, 100% { box-shadow: 0 0 15px rgba(79,142,247,0.1); }
    50% { box-shadow: 0 0 30px rgba(79,142,247,0.25); }
  }

  @keyframes typing {
    from { width: 0; }
    to { width: 100%; }
  }

  .typing-line {
    overflow: hidden;
    white-space: nowrap;
    animation: typing 1.5s steps(40) 1s both;
    display: inline-block;
  }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-tag">Available for freelance</div>
    <h1>Ulugbek<br/>Gofurjonov</h1>
    <p class="hero-sub">
      <span>&lt;</span> Frontend Developer <span>/&gt;</span>
      &nbsp;·&nbsp; React & Next.js &nbsp;·&nbsp; Uzbekistan 🇺🇿
    </p>
  </div>

  <div class="divider"></div>

  <!-- ABOUT -->
  <div class="section-label">About</div>
  <div class="code-block">
    <div class="code-header">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
      <span class="code-filename">profile.ts</span>
    </div>
    <div class="code-body">
      <div><span class="c-keyword">const</span> <span class="c-var">ulugbek</span><span class="c-type">: Developer</span> = {</div>
      <div>&nbsp;&nbsp;<span class="c-key">name</span>     : <span class="c-string">"Ulugbek Gofurjonov"</span>,</div>
      <div>&nbsp;&nbsp;<span class="c-key">role</span>     : <span class="c-string">"Frontend Developer"</span>,</div>
      <div>&nbsp;&nbsp;<span class="c-key">location</span> : <span class="c-string">"Uzbekistan 🇺🇿"</span>,</div>
      <div>&nbsp;&nbsp;<span class="c-key">stack</span>    : [<span class="c-string">"React"</span>, <span class="c-string">"Next.js"</span>, <span class="c-string">"Tailwind"</span>],</div>
      <div>&nbsp;&nbsp;<span class="c-key">focus</span>    : <span class="c-string">"Clean UI · Performance · Scale"</span>,</div>
      <div>&nbsp;&nbsp;<span class="c-key">freelance</span>: <span class="c-bool">true</span>, <span class="c-comment">// open for opportunities 💼</span></div>
      <div>&nbsp;&nbsp;<span class="c-key">web</span>      : <span class="c-string">"ulugbek-gofurjonov.vercel.app"</span>,</div>
      <div>}</div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- TECH STACK -->
  <div class="section-label">Tech Stack</div>
  <div class="stack-grid">
    <div class="stack-item"><span class="stack-icon">🌐</span><span class="stack-name">HTML5</span></div>
    <div class="stack-item"><span class="stack-icon">🎨</span><span class="stack-name">CSS3</span></div>
    <div class="stack-item"><span class="stack-icon">⚡</span><span class="stack-name">JavaScript</span></div>
    <div class="stack-item"><span class="stack-icon">⚛️</span><span class="stack-name">React</span></div>
    <div class="stack-item"><span class="stack-icon">▲</span><span class="stack-name">Next.js</span></div>
    <div class="stack-item"><span class="stack-icon">💨</span><span class="stack-name">Tailwind</span></div>
    <div class="stack-item"><span class="stack-icon">🐙</span><span class="stack-name">GitHub</span></div>
    <div class="stack-item"><span class="stack-icon">🔺</span><span class="stack-name">Vercel</span></div>
  </div>

  <div class="divider"></div>

  <!-- STATS -->
  <div class="section-label">GitHub Stats</div>
  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-num" id="commits">0</div>
      <div class="stat-label">Total Commits</div>
    </div>
    <div class="stat-card">
      <div class="stat-num" id="repos">0</div>
      <div class="stat-label">Repositories</div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- CONTRIBUTION GRAPH -->
  <div class="graph-container">
    <div class="graph-title">Contribution Activity — 2024</div>
    <div class="graph" id="graph"></div>
  </div>

  <div class="divider"></div>

  <!-- CONTACT -->
  <div class="section-label">Contact</div>
  <div class="contact-grid">
    <a class="contact-btn" href="https://ulugbek-gofurjonov.vercel.app" target="_blank">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
      Portfolio
    </a>
    <a class="contact-btn" href="mailto:ulugbekgofurjonov001@gmail.com">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      Gmail
    </a>
    <a class="contact-btn" href="https://linkedin.com/in/ulugbek-gofurjonov" target="_blank">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
      LinkedIn
    </a>
    <a class="contact-btn" href="https://t.me/UlugbekGofurjonov" target="_blank">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.562 8.248-1.97 9.289c-.145.658-.537.818-1.084.508l-3-2.21-1.447 1.394c-.16.16-.295.295-.605.295l.213-3.053 5.56-5.023c.242-.213-.054-.333-.373-.12L7.17 14.71l-2.95-.924c-.64-.203-.654-.64.136-.954l11.526-4.443c.537-.194 1.006.131.68.859z"/></svg>
      Telegram
    </a>
    <a class="contact-btn" href="https://instagram.com/gofurrjonov" target="_blank">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
      Instagram
    </a>
  </div>

  <div class="divider"></div>

  <!-- FOOTER -->
  <div class="footer">
    <a class="follow-badge" href="https://github.com/ulugbekgofurjonov" target="_blank">
      <div class="follow-dot"></div>
      Follow on GitHub &nbsp;@ulugbekgofurjonov
    </a>
  </div>

</div>

<script>
  // Animated counters
  function animateCount(el, target, duration) {
    let start = 0;
    const step = target / (duration / 16);
    const timer = setInterval(() => {
      start += step;
      if (start >= target) { start = target; clearInterval(timer); }
      el.textContent = Math.floor(start) + (target >= 100 ? '+' : '');
    }, 16);
  }

  setTimeout(() => {
    animateCount(document.getElementById('commits'), 120, 1500);
    animateCount(document.getElementById('repos'), 18, 1200);
  }, 800);

  // Generate contribution graph
  const graph = document.getElementById('graph');
  const levels = [0,0,0,1,1,2,3,4];
  for (let w = 0; w < 52; w++) {
    const col = document.createElement('div');
    col.className = 'graph-col';
    for (let d = 0; d < 7; d++) {
      const cell = document.createElement('div');
      const lvl = levels[Math.floor(Math.random() * levels.length)];
      cell.className = 'graph-cell' + (lvl ? ' l' + lvl : '');
      col.appendChild(cell);
    }
    graph.appendChild(col);
  }
</script>

</body>
</html>
