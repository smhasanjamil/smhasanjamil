<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>S M Hasan Jamil — Backend Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Mono:ital,wght@0,400;0,500;1,400&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #090d10;
    --bg2: #0e1318;
    --bg3: #131920;
    --accent: #00e5a0;
    --accent2: #00b4ff;
    --accent3: #ff6b35;
    --text: #e8edf2;
    --muted: #5a6a78;
    --border: rgba(255,255,255,0.07);
    --border2: rgba(0,229,160,0.2);
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Ambient background */
  body::before {
    content: '';
    position: fixed;
    top: -200px; left: -200px;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(0,229,160,0.06) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }
  body::after {
    content: '';
    position: fixed;
    bottom: -200px; right: -200px;
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(0,180,255,0.05) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 32px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    margin-bottom: 64px;
    animation: fadeUp 0.8s ease both;
  }
  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.18em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .hero-eyebrow::before {
    content: '';
    width: 28px; height: 1px;
    background: var(--accent);
  }
  .hero-name {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(64px, 12vw, 108px);
    line-height: 0.9;
    letter-spacing: 0.01em;
    color: var(--text);
    margin-bottom: 8px;
  }
  .hero-name .accent { color: var(--accent); }
  .hero-title {
    font-family: 'DM Mono', monospace;
    font-size: 14px;
    color: var(--muted);
    margin-bottom: 28px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .hero-title .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 2s ease-in-out infinite;
  }
  .hero-bio {
    font-size: 17px;
    line-height: 1.75;
    color: #8fa3b4;
    max-width: 560px;
    margin-bottom: 36px;
    font-weight: 300;
  }
  .hero-bio strong { color: var(--text); font-weight: 500; }
  .hero-links {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }
  .btn {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.05em;
    padding: 10px 20px;
    border-radius: 6px;
    text-decoration: none;
    transition: all 0.2s;
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }
  .btn-primary {
    background: var(--accent);
    color: #001a10;
    font-weight: 500;
  }
  .btn-primary:hover { background: #00ffb3; transform: translateY(-1px); }
  .btn-ghost {
    border: 1px solid var(--border);
    color: var(--muted);
  }
  .btn-ghost:hover { border-color: var(--border2); color: var(--accent); }

  /* ── SECTION LABEL ── */
  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.18em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 14px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ROLE CARD ── */
  .role-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent);
    border-radius: 10px;
    padding: 28px 32px;
    margin-bottom: 64px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 24px;
    animation: fadeUp 0.8s 0.15s ease both;
  }
  .role-main .company {
    font-size: 20px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 4px;
  }
  .role-main .position {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    color: var(--accent);
    margin-bottom: 4px;
  }
  .role-main .period {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }
  .role-badge {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 6px 14px;
    background: rgba(0,229,160,0.08);
    border: 1px solid rgba(0,229,160,0.2);
    border-radius: 20px;
    color: var(--accent);
    white-space: nowrap;
  }

  /* ── SKILLS ── */
  .skills-section { margin-bottom: 64px; animation: fadeUp 0.8s 0.25s ease both; }
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 16px;
  }
  .skill-group {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px 22px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .skill-group:hover { border-color: var(--border2); transform: translateY(-2px); }
  .skill-group-title {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 14px;
  }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 8px; }
  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    padding: 5px 11px;
    border-radius: 5px;
    background: var(--bg3);
    border: 1px solid var(--border);
    color: #8fa3b4;
    transition: all 0.15s;
  }
  .tag:hover { color: var(--text); border-color: rgba(255,255,255,0.15); }
  .tag.hot {
    background: rgba(0,229,160,0.07);
    border-color: rgba(0,229,160,0.18);
    color: var(--accent);
  }
  .tag.learning {
    background: rgba(255,107,53,0.07);
    border-color: rgba(255,107,53,0.2);
    color: var(--accent3);
    font-style: italic;
  }
  .tag.infra {
    background: rgba(0,180,255,0.07);
    border-color: rgba(0,180,255,0.2);
    color: var(--accent2);
  }

  /* ── STATS ── */
  .stats-section { margin-bottom: 64px; animation: fadeUp 0.8s 0.35s ease both; }
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 24px;
  }
  .stat-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px 16px;
    text-align: center;
    transition: all 0.2s;
  }
  .stat-card:hover { border-color: var(--border2); transform: translateY(-2px); }
  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 40px;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 4px;
  }
  .stat-lbl {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    color: var(--muted);
    text-transform: uppercase;
  }
  .github-imgs {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }
  .github-imgs img {
    width: 100%;
    border-radius: 10px;
    border: 1px solid var(--border);
  }

  /* ── PROJECTS ── */
  .projects-section { margin-bottom: 64px; animation: fadeUp 0.8s 0.4s ease both; }
  .project-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 24px 28px;
    margin-bottom: 12px;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 20px;
    transition: all 0.2s;
    text-decoration: none;
    color: inherit;
    display: block;
  }
  .project-card:hover { border-color: rgba(0,180,255,0.25); transform: translateX(4px); }
  .project-top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
  .project-name {
    font-size: 16px;
    font-weight: 500;
    color: var(--text);
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .project-name .live-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 2s ease-in-out infinite;
  }
  .project-arrow {
    font-family: 'DM Mono', monospace;
    font-size: 18px;
    color: var(--muted);
    transition: color 0.2s, transform 0.2s;
  }
  .project-card:hover .project-arrow { color: var(--accent2); transform: translate(2px,-2px); }
  .project-desc {
    font-size: 14px;
    color: #5a6a78;
    line-height: 1.6;
    margin-bottom: 14px;
  }
  .project-stack { display: flex; gap: 6px; flex-wrap: wrap; }
  .project-tag {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 3px 9px;
    border-radius: 4px;
    background: var(--bg3);
    border: 1px solid var(--border);
    color: var(--muted);
  }

  /* ── CONTACT ── */
  .contact-section { animation: fadeUp 0.8s 0.45s ease both; }
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
  }
  .contact-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px 22px;
    text-decoration: none;
    color: inherit;
    transition: all 0.2s;
    display: block;
  }
  .contact-card:hover { border-color: var(--border2); transform: translateY(-2px); }
  .contact-icon {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    margin-bottom: 6px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }
  .contact-val {
    font-size: 14px;
    font-weight: 500;
    color: var(--accent);
  }

  /* ── FOOTER ── */
  .footer {
    margin-top: 80px;
    padding-top: 28px;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }
  .footer-sig { color: var(--accent); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: #1e2a35; border-radius: 3px; }

  @media (max-width: 600px) {
    .stats-grid { grid-template-columns: repeat(2, 1fr); }
    .contact-grid { grid-template-columns: 1fr 1fr; }
    .github-imgs { grid-template-columns: 1fr; }
    .role-card { flex-direction: column; gap: 12px; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-eyebrow">Available for collaboration</div>
    <div class="hero-name">S M Hasan<br/><span class="accent">Jamil</span></div>
    <div class="hero-title">
      <span class="dot"></span>
      Backend Engineer &nbsp;·&nbsp; Team Lead &nbsp;·&nbsp; Full Stack Developer
    </div>
    <p class="hero-bio">
      I build <strong>scalable backend systems</strong> and lead engineering teams that ship.
      Currently architecting APIs, cloud infra, and distributed services at
      <strong>SM Technology</strong>. Clean code. Reliable systems. Effective teams.
    </p>
    <div class="hero-links">
      <a class="btn btn-primary" href="https://hasan-jamil.vercel.app/" target="_blank">↗ Portfolio</a>
      <a class="btn btn-ghost" href="mailto:smhasanjamil14@gmail.com">✉ Email</a>
      <a class="btn btn-ghost" href="https://www.linkedin.com/in/smhasanjamil27/" target="_blank">in LinkedIn</a>
      <a class="btn btn-ghost" href="https://github.com/smhasanjamil" target="_blank">⌥ GitHub</a>
    </div>
  </div>

  <!-- ROLE -->
  <div class="role-card">
    <div class="role-main">
      <div class="company">SM Technology</div>
      <div class="position">Backend Engineer · Team Lead</div>
      <div class="period">Jun 2025 – Present</div>
    </div>
    <div class="role-badge">⬤ &nbsp;Currently here</div>
  </div>

  <!-- SKILLS -->
  <div class="skills-section">
    <div class="section-label">Tech Stack</div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-title">Frontend</div>
        <div class="skill-tags">
          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
          <span class="tag">Tailwind</span>
          <span class="tag">JavaScript</span>
          <span class="tag">TypeScript</span>
          <span class="tag">React</span>
          <span class="tag">Next.js</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Backend</div>
        <div class="skill-tags">
          <span class="tag hot">Node.js</span>
          <span class="tag hot">Express</span>
          <span class="tag hot">Prisma</span>
          <span class="tag hot">REST APIs</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Database</div>
        <div class="skill-tags">
          <span class="tag hot">PostgreSQL</span>
          <span class="tag">MongoDB</span>
          <span class="tag">Mongoose</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Infrastructure & DevOps</div>
        <div class="skill-tags">
          <span class="tag infra">Docker</span>
          <span class="tag infra">AWS</span>
          <span class="tag infra">Nginx</span>
          <span class="tag infra">CI/CD</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Currently Learning</div>
        <div class="skill-tags">
          <span class="tag learning">Golang</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Ask me about</div>
        <div class="skill-tags">
          <span class="tag">TypeScript</span>
          <span class="tag">Next.js</span>
          <span class="tag">PostgreSQL</span>
          <span class="tag">Docker</span>
          <span class="tag">Prisma</span>
        </div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-section">
    <div class="section-label">GitHub Activity</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-num" id="repos">—</div>
        <div class="stat-lbl">Repos</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" id="followers">—</div>
        <div class="stat-lbl">Followers</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">2+</div>
        <div class="stat-lbl">Yrs Exp</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">10+</div>
        <div class="stat-lbl">Projects</div>
      </div>
    </div>
    <div class="github-imgs">
      <img src="https://github-readme-stats.vercel.app/api?username=smhasanjamil&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0e1318&title_color=00e5a0&icon_color=00b4ff&text_color=8fa3b4&border_radius=10" alt="GitHub Stats" loading="lazy"/>
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=smhasanjamil&theme=tokyonight&hide_border=true&background=0e1318&ring=00e5a0&fire=ff6b35&currStreakLabel=00e5a0&border_radius=10" alt="GitHub Streak" loading="lazy"/>
    </div>
    <div style="margin-top:16px;">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=smhasanjamil&theme=tokyo-night&hide_border=true&bg_color=0e1318&color=8fa3b4&line=00e5a0&point=00b4ff&area=true&area_color=00e5a0" alt="Activity Graph" style="width:100%;border-radius:10px;border:1px solid rgba(255,255,255,0.07);" loading="lazy"/>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="projects-section">
    <div class="section-label">Featured Projects</div>
    <a class="project-card" href="https://github.com/smhasanjamil/feedme" target="_blank">
      <div class="project-top">
        <div class="project-name"><span class="live-dot"></span> Feedme</div>
        <div class="project-arrow">↗</div>
      </div>
      <div class="project-desc">Currently building — a full-stack food delivery platform with real-time order tracking, restaurant management, and payment integration.</div>
      <div class="project-stack">
        <span class="project-tag">Next.js</span>
        <span class="project-tag">Node.js</span>
        <span class="project-tag">PostgreSQL</span>
        <span class="project-tag">Prisma</span>
        <span class="project-tag">Docker</span>
      </div>
    </a>
    <a class="project-card" href="https://hasan-jamil.vercel.app/" target="_blank">
      <div class="project-top">
        <div class="project-name">Portfolio</div>
        <div class="project-arrow">↗</div>
      </div>
      <div class="project-desc">Personal portfolio showcasing projects, experience, and technical skills built with modern web technologies.</div>
      <div class="project-stack">
        <span class="project-tag">React</span>
        <span class="project-tag">Tailwind</span>
        <span class="project-tag">Vercel</span>
      </div>
    </a>
  </div>

  <!-- CONTACT -->
  <div class="contact-section">
    <div class="section-label">Connect</div>
    <div class="contact-grid">
      <a class="contact-card" href="mailto:smhasanjamil14@gmail.com">
        <div class="contact-icon">Email</div>
        <div class="contact-val">smhasanjamil14@gmail.com</div>
      </a>
      <a class="contact-card" href="https://www.linkedin.com/in/smhasanjamil27/" target="_blank">
        <div class="contact-icon">LinkedIn</div>
        <div class="contact-val">smhasanjamil27</div>
      </a>
      <a class="contact-card" href="https://x.com/smhasanjamil" target="_blank">
        <div class="contact-icon">Twitter / X</div>
        <div class="contact-val">@smhasanjamil</div>
      </a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <span>S M Hasan Jamil · Backend Engineer</span>
    <span class="footer-sig">Dhaka, Bangladesh</span>
  </div>

</div>

<script>
  fetch('https://api.github.com/users/smhasanjamil')
    .then(r => r.json())
    .then(d => {
      if (d.public_repos !== undefined) document.getElementById('repos').textContent = d.public_repos;
      if (d.followers !== undefined) document.getElementById('followers').textContent = d.followers;
    })
    .catch(() => {});
</script>
</body>
</html>
