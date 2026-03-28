<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Pavan Karthik — ML Engineer & AI Builder</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,500;0,9..144,700;1,9..144,300&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0a0a;
    --surface: #111111;
    --surface2: #171717;
    --border: rgba(255,255,255,0.07);
    --border-accent: rgba(220,80,60,0.3);
    --red: #dc503c;
    --red-soft: #e8705e;
    --red-dim: rgba(220,80,60,0.12);
    --text: #f0ece8;
    --text-2: #8a8580;
    --text-3: #4a4845;
    --mono: 'DM Mono', monospace;
    --serif: 'Fraunces', serif;
    --sans: 'DM Sans', sans-serif;
  }

  html { background: var(--bg); color: var(--text); font-family: var(--sans); }
  body { max-width: 860px; margin: 0 auto; padding: 60px 32px 100px; }

  /* ── HEADER ── */
  .header {
    position: relative;
    border: 1px solid var(--border);
    border-radius: 2px;
    padding: 56px 48px 48px;
    margin-bottom: 4px;
    overflow: hidden;
  }
  .header::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--red), transparent);
  }
  .header-corner {
    position: absolute;
    top: 0; right: 0;
    width: 80px; height: 80px;
    border-left: 1px solid var(--border-accent);
    border-bottom: 1px solid var(--border-accent);
    border-bottom-left-radius: 2px;
    pointer-events: none;
  }
  .header-corner-bl {
    position: absolute;
    bottom: 0; left: 0;
    width: 48px; height: 48px;
    border-right: 1px solid var(--border);
    border-top: 1px solid var(--border);
    border-top-right-radius: 2px;
    pointer-events: none;
  }

  .tag {
    font-family: var(--mono);
    font-size: 11px;
    font-weight: 400;
    letter-spacing: 0.12em;
    color: var(--red);
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .tag::before { content: ''; width: 24px; height: 1px; background: var(--red); }

  h1 {
    font-family: var(--serif);
    font-size: clamp(42px, 7vw, 72px);
    font-weight: 300;
    line-height: 1.0;
    letter-spacing: -0.02em;
    color: var(--text);
    margin-bottom: 6px;
  }
  h1 em {
    font-style: italic;
    color: var(--red-soft);
  }

  .subtitle {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text-2);
    letter-spacing: 0.08em;
    margin-top: 20px;
    display: flex;
    align-items: center;
    gap: 8px;
    flex-wrap: wrap;
  }
  .subtitle span { color: var(--text-3); }

  /* ── GRID LAYOUT ── */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4px;
    margin-bottom: 4px;
  }
  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 4px;
    margin-bottom: 4px;
  }

  /* ── PANEL ── */
  .panel {
    border: 1px solid var(--border);
    border-radius: 2px;
    padding: 32px;
    background: var(--surface);
    position: relative;
  }
  .panel.full { grid-column: 1 / -1; }
  .panel.accent { border-color: var(--border-accent); }

  .panel-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.15em;
    color: var(--text-3);
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .panel-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

  /* ── ABOUT ── */
  .about-text {
    font-family: var(--serif);
    font-size: 18px;
    font-weight: 300;
    line-height: 1.65;
    color: var(--text);
  }
  .about-text strong {
    font-weight: 500;
    color: var(--red-soft);
    font-style: italic;
  }

  /* ── STACK SECTION ── */
  .stack-group { margin-bottom: 24px; }
  .stack-group:last-child { margin-bottom: 0; }

  .stack-group-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.12em;
    color: var(--text-3);
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .chip-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .chip {
    font-family: var(--mono);
    font-size: 11px;
    font-weight: 400;
    letter-spacing: 0.04em;
    color: var(--text-2);
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 2px;
    padding: 5px 12px;
    transition: color 0.2s, border-color 0.2s;
    cursor: default;
  }
  .chip:hover { color: var(--text); border-color: rgba(255,255,255,0.15); }
  .chip.hot {
    color: var(--red-soft);
    border-color: var(--border-accent);
    background: var(--red-dim);
  }

  /* ── WHAT I BUILD ── */
  .build-item {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 16px 0;
    border-bottom: 1px solid var(--border);
  }
  .build-item:last-child { border-bottom: none; padding-bottom: 0; }
  .build-item:first-child { padding-top: 0; }

  .build-num {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--red);
    min-width: 28px;
    padding-top: 2px;
  }

  .build-title {
    font-size: 14px;
    font-weight: 500;
    color: var(--text);
    margin-bottom: 4px;
    letter-spacing: 0.01em;
  }
  .build-desc {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-2);
    line-height: 1.6;
  }

  /* ── STATS ROW ── */
  .stat-block {
    text-align: center;
    padding: 20px 0;
  }
  .stat-num {
    font-family: var(--serif);
    font-size: 40px;
    font-weight: 300;
    color: var(--text);
    line-height: 1;
    margin-bottom: 6px;
  }
  .stat-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.12em;
    color: var(--text-3);
    text-transform: uppercase;
  }
  .stat-divider {
    width: 1px;
    background: var(--border);
    margin: 20px 0;
  }

  /* ── CONTACT ── */
  .contact-link {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 16px 0;
    border-bottom: 1px solid var(--border);
    text-decoration: none;
    color: var(--text-2);
    transition: color 0.2s;
    cursor: pointer;
  }
  .contact-link:last-child { border-bottom: none; }
  .contact-link:hover { color: var(--text); }
  .contact-link:hover .link-arrow { color: var(--red); }

  .link-platform {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.1em;
    color: var(--text-3);
    text-transform: uppercase;
    min-width: 80px;
  }
  .link-handle { font-size: 14px; font-weight: 400; }
  .link-arrow {
    font-family: var(--mono);
    font-size: 14px;
    color: var(--text-3);
    transition: color 0.2s;
  }

  /* ── FOOTER ── */
  .footer {
    margin-top: 4px;
    border: 1px solid var(--border);
    border-radius: 2px;
    padding: 24px 32px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
  }
  .footer-left {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-3);
    letter-spacing: 0.08em;
  }
  .footer-left strong { color: var(--red); font-weight: 400; }
  .footer-right {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--text-3);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  /* ── SEPARATOR LINES ── */
  .sep { margin-bottom: 4px; }

  /* ── HIGHLIGHT BAR ── */
  .highlight-bar {
    height: 1px;
    background: linear-gradient(90deg, var(--red), transparent);
    margin-bottom: 4px;
    opacity: 0.4;
  }

  @media (max-width: 600px) {
    body { padding: 32px 20px 60px; }
    .header { padding: 36px 28px 32px; }
    .grid-2, .grid-3 { grid-template-columns: 1fr; }
    .panel.full { grid-column: 1; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<div class="header">
  <div class="header-corner"></div>
  <div class="header-corner-bl"></div>
  <div class="tag">ML Engineer · Flutter Developer · AI Builder</div>
  <h1>Pavan<br/><em>Karthik</em></h1>
  <p class="subtitle">
    Python <span>/</span> PyTorch <span>/</span> LangChain <span>/</span> Flutter <span>/</span> Firebase
    <span style="margin-left:12px; color: var(--text-3);">— Hyderabad, IN</span>
  </p>
</div>

<div class="highlight-bar"></div>

<!-- ABOUT + WHAT I BUILD -->
<div class="grid-2 sep">
  <div class="panel">
    <div class="panel-label">About</div>
    <p class="about-text">
      Turning raw data into <strong>intelligent systems</strong> — from LLM pipelines and agentic workflows to 
      AI-powered mobile apps. I build things that think.
    </p>
  </div>
  <div class="panel">
    <div class="panel-label">Focus Areas</div>
    <div class="build-item">
      <div class="build-num">01</div>
      <div>
        <div class="build-title">Agentic AI & LLM Pipelines</div>
        <div class="build-desc">RAG, tool-use, prompt engineering, vector DBs</div>
      </div>
    </div>
    <div class="build-item">
      <div class="build-num">02</div>
      <div>
        <div class="build-title">Deep Learning & Computer Vision</div>
        <div class="build-desc">CNNs, Transformers, GANs, diffusion models</div>
      </div>
    </div>
    <div class="build-item">
      <div class="build-num">03</div>
      <div>
        <div class="build-title">Flutter × AI Mobile Apps</div>
        <div class="build-desc">On-device ML, Firebase, Dart, smart interfaces</div>
      </div>
    </div>
  </div>
</div>

<!-- TECH STACK -->
<div class="panel full sep">
  <div class="panel-label">Tech Stack</div>
  <div class="grid-3" style="gap: 28px; margin-bottom:0;">
    <div class="stack-group">
      <div class="stack-group-label">Deep Learning</div>
      <div class="chip-row">
        <span class="chip hot">PyTorch</span>
        <span class="chip hot">TensorFlow</span>
        <span class="chip">Keras</span>
        <span class="chip hot">HuggingFace</span>
        <span class="chip">scikit-learn</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">LLM & Agentic</div>
      <div class="chip-row">
        <span class="chip hot">LangChain</span>
        <span class="chip hot">OpenAI API</span>
        <span class="chip">RAG</span>
        <span class="chip">Vector DBs</span>
        <span class="chip">Prompt Eng.</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">Data & Viz</div>
      <div class="chip-row">
        <span class="chip">NumPy</span>
        <span class="chip">Pandas</span>
        <span class="chip">Matplotlib</span>
        <span class="chip">Seaborn</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">Mobile & Backend</div>
      <div class="chip-row">
        <span class="chip hot">Flutter</span>
        <span class="chip hot">Dart</span>
        <span class="chip">Firebase</span>
        <span class="chip">MongoDB</span>
        <span class="chip">MySQL</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">Languages</div>
      <div class="chip-row">
        <span class="chip hot">Python</span>
        <span class="chip">Dart</span>
        <span class="chip">JavaScript</span>
        <span class="chip">SQL</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">DevOps & Deploy</div>
      <div class="chip-row">
        <span class="chip">Git</span>
        <span class="chip">GitHub</span>
        <span class="chip">Vercel</span>
        <span class="chip">Netlify</span>
        <span class="chip">Render</span>
      </div>
    </div>
  </div>
</div>

<!-- STATS + CONNECT -->
<div class="grid-2 sep">
  <div class="panel" style="display:flex; align-items:center; justify-content:space-around;">
    <div class="stat-block">
      <div class="stat-num">3+</div>
      <div class="stat-label">Years Building</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-block">
      <div class="stat-num">ML</div>
      <div class="stat-label">Primary Domain</div>
    </div>
    <div class="stat-divider"></div>
    <div class="stat-block">
      <div class="stat-num">∞</div>
      <div class="stat-label">Models Trained</div>
    </div>
  </div>

  <div class="panel accent">
    <div class="panel-label">Connect</div>
    <a class="contact-link" href="https://github.com/pavanakarthik12" target="_blank">
      <span class="link-platform">GitHub</span>
      <span class="link-handle">pavanakarthik12</span>
      <span class="link-arrow">↗</span>
    </a>
    <div class="contact-link">
      <span class="link-platform">LinkedIn</span>
      <span class="link-handle">Pavan Karthik</span>
      <span class="link-arrow">↗</span>
    </div>
    <div class="contact-link">
      <span class="link-platform">Open to</span>
      <span class="link-handle" style="color: var(--red-soft); font-family: var(--mono); font-size:12px;">Collab · Internships · Research</span>
      <span class="link-arrow" style="opacity:0"></span>
    </div>
  </div>
</div>

<!-- FOOTER -->
<div class="footer">
  <div class="footer-left">
    <strong>pavanakarthik12</strong> &nbsp;·&nbsp; ML Engineer &amp; AI Builder
  </div>
  <div class="footer-right">Turning data into intelligence</div>
</div>

</body>
</html>
