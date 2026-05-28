
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap');
  :root {
    --orange: #FF6B1A;
    --orange-dark: #D94F00;
    --orange-glow: rgba(255,107,26,0.18);
    --black: #0D0D0D;
    --surface: #161616;
    --surface2: #1E1E1E;
    --border: rgba(255,107,26,0.25);
    --text: #F5F0EB;
    --muted: #888;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  .profile-root { background: var(--black); color: var(--text); font-family: 'Syne', sans-serif; padding: 0 0 3rem; min-height: 100vh; position: relative; overflow: hidden; }
  .bg-grid { position: absolute; top: 0; left: 0; right: 0; bottom: 0; background-image: linear-gradient(rgba(255,107,26,0.04) 1px, transparent 1px), linear-gradient(90deg, rgba(255,107,26,0.04) 1px, transparent 1px); background-size: 40px 40px; pointer-events: none; }
  .hero { position: relative; padding: 3rem 2rem 2rem; border-bottom: 1px solid var(--border); display: flex; align-items: center; gap: 2rem; }
  .avatar-wrap { flex-shrink: 0; width: 90px; height: 90px; border-radius: 50%; border: 2.5px solid var(--orange); background: var(--surface); display: flex; align-items: center; justify-content: center; font-family: 'Space Mono', monospace; font-size: 28px; font-weight: 700; color: var(--orange); box-shadow: 0 0 28px rgba(255,107,26,0.3); }
  .hero-text h1 { font-size: 2rem; font-weight: 800; color: var(--text); line-height: 1.1; }
  .hero-text h1 span { color: var(--orange); }
  .hero-text p { margin-top: 0.5rem; font-size: 0.85rem; color: var(--muted); font-family: 'Space Mono', monospace; letter-spacing: 0.03em; }
  .tag-row { margin-top: 0.9rem; display: flex; gap: 8px; flex-wrap: wrap; }
  .tag { font-size: 11px; font-family: 'Space Mono', monospace; padding: 4px 10px; border-radius: 3px; border: 1px solid var(--border); color: var(--orange); background: rgba(255,107,26,0.07); letter-spacing: 0.06em; text-transform: uppercase; }
  .section { padding: 1.6rem 2rem 0; position: relative; }
  .section-title { font-size: 11px; font-family: 'Space Mono', monospace; letter-spacing: 0.12em; text-transform: uppercase; color: var(--orange); margin-bottom: 1rem; display: flex; align-items: center; gap: 8px; }
  .section-title::after { content: ''; flex: 1; height: 1px; background: var(--border); }
  .readme-box { position: relative; background: var(--surface2); border: 1px solid var(--border); border-radius: 10px; overflow: hidden; }
  .readme-topbar { background: var(--surface); border-bottom: 1px solid var(--border); padding: 8px 14px; display: flex; align-items: center; gap: 6px; }
  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #E24B4A; } .dot-y { background: var(--orange); } .dot-g { background: #639922; }
  .readme-filename { font-family: 'Space Mono', monospace; font-size: 11px; color: var(--muted); margin-left: 4px; }
  .readme-content { padding: 1.2rem 1.4rem; }
  .code-line { font-family: 'Space Mono', monospace; font-size: 12px; line-height: 1.9; color: var(--muted); }
  .code-line .kw { color: var(--orange); }
  .code-line .str { color: #97C459; }
  .code-line .num { color: #FAC775; }
  .code-line .cmt { color: #444; }
  .orbit-badge-row { display: flex; gap: 8px; flex-wrap: wrap; margin-top: 10px; }
  .orbit-badge { font-size: 10px; font-family: 'Space Mono', monospace; padding: 3px 9px; border-radius: 3px; border: 1px solid var(--border); color: var(--orange); background: rgba(255,107,26,0.07); letter-spacing: 0.05em; }
  .orbit-badge.live { background: rgba(99,153,34,0.12); border-color: rgba(99,153,34,0.4); color: #97C459; }
  .tech-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(70px, 1fr)); gap: 10px; }
  .tech-pill { background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 0.7rem 0.5rem; display: flex; flex-direction: column; align-items: center; gap: 5px; font-size: 11px; font-family: 'Space Mono', monospace; color: var(--muted); text-align: center; }
  .tech-pill i { font-size: 22px; color: var(--orange); }
  .stats-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .stat-card { background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 1rem; display: flex; align-items: center; gap: 10px; }
  .stat-icon { width: 38px; height: 38px; border-radius: 8px; background: rgba(255,107,26,0.12); display: flex; align-items: center; justify-content: center; }
  .stat-icon i { font-size: 20px; color: var(--orange); }
  .stat-label { font-size: 11px; font-family: 'Space Mono', monospace; color: var(--muted); text-transform: uppercase; letter-spacing: 0.06em; }
  .stat-value { font-size: 1.1rem; font-weight: 800; color: var(--text); line-height: 1; margin-top: 3px; }
  .social-row { display: flex; gap: 10px; flex-wrap: wrap; }
  .social-btn { background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 0.65rem 1rem; display: flex; align-items: center; gap: 7px; color: var(--text); font-size: 13px; font-family: 'Space Mono', monospace; text-decoration: none; cursor: pointer; }
  .social-btn:hover { border-color: var(--orange); color: var(--orange); }
  .social-btn i { font-size: 17px; color: var(--orange); }
  .divider-line { height: 1px; background: var(--border); margin: 0.2rem 2rem 0; }
  .footer-bar { padding: 1.2rem 2rem 0; display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 0.5rem; }
  .footer-bar span { font-size: 11px; font-family: 'Space Mono', monospace; color: var(--muted); }
  .footer-bar span b { color: var(--orange); }
  .copy-badge { display: inline-flex; align-items: center; gap: 6px; font-size: 11px; font-family: 'Space Mono', monospace; color: var(--muted); border: 1px solid var(--border); padding: 4px 10px; border-radius: 3px; }
</style>

<div class="profile-root">
  <div class="bg-grid"></div>

  <div class="hero">
    <div class="avatar-wrap">PY</div>
    <div class="hero-text">
      <h1>Hey, I'm <span>Praveen</span> 👋</h1>
      <p>1st year AIML student → building cool stuff with data</p>
      <div class="tag-row">
        <span class="tag">Machine Learning</span>
        <span class="tag">Python</span>
        <span class="tag">Data Science</span>
        <span class="tag">Open to collab</span>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-title">🔭 Current project</div>
    <div class="readme-box">
      <div class="readme-topbar">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="readme-filename">orbit / app.py</span>
      </div>
      <div class="readme-content">
        <div class="code-line"><span class="cmt"># ORBIT — Claude-powered life companion</span></div>
        <div class="code-line"><span class="cmt"># Your life. In motion. All aligned.</span></div>
        <div class="code-line">&nbsp;</div>
        <div class="code-line">project = {</div>
        <div class="code-line">&nbsp;&nbsp;<span class="str">"desc"</span>: <span class="str">"AI life companion — habits, goals, vision"</span>,</div>
        <div class="code-line">&nbsp;&nbsp;<span class="str">"stack"</span>: [<span class="str">"Claude API"</span>, <span class="str">"HTML"</span>, <span class="str">"localStorage"</span>],</div>
        <div class="code-line">&nbsp;&nbsp;<span class="str">"features"</span>: [<span class="str">"Doom Meter"</span>, <span class="str">"Stakes Engine"</span>, <span class="str">"Memory"</span>],</div>
        <div class="code-line">&nbsp;&nbsp;<span class="str">"status"</span>: <span class="str">"🚀 v2 In Progress"</span>,</div>
        <div class="code-line">&nbsp;&nbsp;<span class="str">"url"</span>: <span class="str">"github.com/Praveen-2595/Orbit"</span></div>
        <div class="code-line">}</div>
        <div class="orbit-badge-row">
          <span class="orbit-badge live">✦ Live</span>
          <span class="orbit-badge">Claude API</span>
          <span class="orbit-badge">Single HTML</span>
          <span class="orbit-badge">Vercel Ready</span>
          <span class="orbit-badge">v2.0 · May 2026</span>
        </div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-title">🛠 Languages &amp; Tools</div>
    <div class="tech-grid">
      <div class="tech-pill"><i class="ti ti-brand-python" aria-hidden="true"></i>Python</div>
      <div class="tech-pill"><i class="ti ti-brain" aria-hidden="true"></i>Scikit</div>
      <div class="tech-pill"><i class="ti ti-table" aria-hidden="true"></i>Pandas</div>
      <div class="tech-pill"><i class="ti ti-math-function" aria-hidden="true"></i>NumPy</div>
      <div class="tech-pill"><i class="ti ti-database" aria-hidden="true"></i>MySQL</div>
      <div class="tech-pill"><i class="ti ti-brand-html5" aria-hidden="true"></i>HTML5</div>
      <div class="tech-pill"><i class="ti ti-code" aria-hidden="true"></i>C/C++</div>
    </div>
  </div>

  <div class="section">
    <div class="section-title">📊 GitHub Stats</div>
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-icon"><i class="ti ti-git-branch" aria-hidden="true"></i></div>
        <div>
          <div class="stat-label">Top Languages</div>
          <div class="stat-value" style="font-size:0.85rem; margin-top:5px;">Python · C · SQL</div>
        </div>
      </div>
      <div class="stat-card">
        <div class="stat-icon"><i class="ti ti-flame" aria-hidden="true"></i></div>
        <div>
          <div class="stat-label">Streak</div>
          <div class="stat-value" style="font-size:0.78rem; margin-top:5px;">github.com/<span style="color:var(--orange)">praveen-2595</span></div>
        </div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-title">🌐 Connect with me</div>
    <div class="social-row">
      <a class="social-btn" href="https://linkedin.com/in/praveen-yadav" target="_blank">
        <i class="ti ti-brand-linkedin" aria-hidden="true"></i> LinkedIn
      </a>
      <a class="social-btn" href="https://kaggle.com/praveenyadav25" target="_blank">
        <i class="ti ti-chart-line" aria-hidden="true"></i> Kaggle
      </a>
      <a class="social-btn" href="https://www.leetcode.com/Czdcp7owao" target="_blank">
        <i class="ti ti-terminal-2" aria-hidden="true"></i> LeetCode
      </a>
    </div>
  </div>

  <div class="divider-line" style="margin-top:1.8rem;"></div>

  <div class="footer-bar">
    <span>Built with <b>🔥</b> and <b>Claude API</b></span>
    <span class="copy-badge"><i class="ti ti-code" style="font-size:13px; color:var(--orange);" aria-hidden="true"></i>readme.md · praveen-2595</span>
  </div>
</div>
