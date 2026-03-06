<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Gustavo Pineda — Developer</title>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:        #0C0C0F;
      --bg-2:      #111115;
      --bg-3:      #16161B;
      --border:    rgba(255,255,255,0.07);
      --border-hi: rgba(0,229,204,0.3);
      --text:      #E4E2DD;
      --text-mid:  #888580;
      --text-dim:  #4A4845;
      --cyan:      #00E5CC;
      --cyan-dim:  rgba(0,229,204,0.12);
      --cyan-glow: rgba(0,229,204,0.25);
      --orange:    #FF6B35;
      --mono: 'JetBrains Mono', monospace;
      --sans: 'DM Sans', sans-serif;
      --display: 'Syne', sans-serif;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: var(--sans);
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* ── GRID BACKGROUND ── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
      background-size: 48px 48px;
      pointer-events: none;
      z-index: 0;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      padding: 0 48px;
      height: 64px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(12,12,15,0.8);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: var(--mono);
      font-size: 0.9rem;
      color: var(--cyan);
      text-decoration: none;
      letter-spacing: 0.02em;
    }

    .nav-logo span { color: var(--text-mid); }

    .nav-links {
      display: flex;
      gap: 36px;
      list-style: none;
      align-items: center;
    }

    .nav-links a {
      text-decoration: none;
      color: var(--text-mid);
      font-size: 0.85rem;
      font-weight: 400;
      letter-spacing: 0.04em;
      transition: color 0.2s;
      font-family: var(--mono);
    }

    .nav-links a:hover { color: var(--cyan); }

    .nav-cta {
      padding: 8px 20px;
      border: 1px solid var(--border-hi);
      border-radius: 6px;
      color: var(--cyan) !important;
      transition: all 0.2s !important;
    }

    .nav-cta:hover {
      background: var(--cyan-dim) !important;
    }

    .nav-resume {
      padding: 8px 20px;
      border: 1px solid var(--border);
      border-radius: 6px;
      color: var(--text-mid) !important;
      transition: all 0.2s !important;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .nav-resume:hover {
      color: var(--text) !important;
      border-color: rgba(255,255,255,0.2) !important;
      background: rgba(255,255,255,0.04) !important;
    }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 64px 48px 80px;
      position: relative;
      z-index: 1;
    }

    .hero-glow {
      position: absolute;
      width: 700px; height: 700px;
      background: radial-gradient(circle, rgba(0,229,204,0.06) 0%, transparent 70%);
      top: 50%; left: 50%;
      transform: translate(-60%, -50%);
      pointer-events: none;
    }

    .hero-content {
      max-width: 900px;
      opacity: 0;
      transform: translateY(24px);
      animation: fadeUp 0.8s ease forwards 0.1s;
    }

    @keyframes fadeUp {
      to { opacity: 1; transform: translateY(0); }
    }

    .hero-eyebrow {
      font-family: var(--mono);
      font-size: 0.82rem;
      color: var(--cyan);
      letter-spacing: 0.06em;
      margin-bottom: 24px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .hero-eyebrow::before {
      content: '';
      display: inline-block;
      width: 32px; height: 1px;
      background: var(--cyan);
    }

    .hero h1 {
      font-family: var(--display);
      font-size: clamp(2.2rem, 4.5vw, 3.8rem);
      font-weight: 800;
      line-height: 1.0;
      color: var(--text);
      margin-bottom: 8px;
      letter-spacing: -0.02em;
    }

    .hero h1 .accent { color: var(--cyan); }

    .hero-sub {
      font-size: clamp(1rem, 1.8vw, 1.15rem);
      color: var(--text-mid);
      max-width: 520px;
      margin: 24px 0 48px;
      font-weight: 300;
      line-height: 1.75;
    }

    .hero-ctas {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
      align-items: center;
    }

    .btn {
      padding: 13px 28px;
      border-radius: 8px;
      font-size: 0.9rem;
      font-weight: 500;
      text-decoration: none;
      transition: all 0.2s;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      border: none;
      font-family: var(--sans);
      letter-spacing: 0.01em;
    }

    .btn-primary {
      background: var(--cyan);
      color: var(--bg);
      font-weight: 600;
    }

    .btn-primary:hover {
      background: #00ccb4;
      transform: translateY(-2px);
      box-shadow: 0 8px 32px var(--cyan-glow);
    }

    .btn-ghost {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
    }

    .btn-ghost:hover {
      border-color: rgba(255,255,255,0.2);
      background: rgba(255,255,255,0.04);
      transform: translateY(-2px);
    }

    .hero-scroll {
      position: absolute;
      bottom: 40px;
      left: 48px;
      display: flex;
      align-items: center;
      gap: 12px;
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--text-dim);
      letter-spacing: 0.08em;
    }

    .scroll-line {
      width: 48px; height: 1px;
      background: var(--text-dim);
    }

    /* ── SECTION BASE ── */
    section {
      padding: 100px 48px;
      position: relative;
      z-index: 1;
      scroll-margin-top: 80px;
    }

    .section-tag {
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--cyan);
      letter-spacing: 0.1em;
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .section-tag::before {
      content: '//';
      color: var(--text-dim);
    }

    .section-title {
      font-family: var(--display);
      font-size: clamp(2rem, 4vw, 2.8rem);
      font-weight: 700;
      color: var(--text);
      line-height: 1.15;
      margin-bottom: 16px;
      letter-spacing: -0.02em;
    }

    /* ── ABOUT ── */
    .about { background: var(--bg-2); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }

    .about-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 80px;
      align-items: start;
    }

    .about-text p {
      color: var(--text-mid);
      font-size: 1rem;
      line-height: 1.85;
      margin-bottom: 18px;
      font-weight: 300;
    }

    .about-text p strong { color: var(--text); font-weight: 500; }

    .about-terminal {
      background: var(--bg-3);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
    }

    .terminal-bar {
      background: rgba(255,255,255,0.04);
      padding: 12px 16px;
      display: flex;
      align-items: center;
      gap: 8px;
      border-bottom: 1px solid var(--border);
    }

    .t-dot {
      width: 10px; height: 10px;
      border-radius: 50%;
    }

    .t-dot.red   { background: #FF5F57; }
    .t-dot.yellow{ background: #FFBD2E; }
    .t-dot.green { background: #28CA41; }

    .terminal-body {
      padding: 24px;
      font-family: var(--mono);
      font-size: 0.82rem;
      line-height: 2;
    }

    .t-line { display: flex; gap: 12px; }
    .t-prompt { color: var(--cyan); user-select: none; }
    .t-cmd { color: var(--text); }
    .t-out { color: var(--text-mid); padding-left: 20px; }
    .t-out .hi { color: var(--cyan); }
    .t-out .org { color: var(--orange); }
    .t-cursor {
      display: inline-block;
      width: 8px; height: 14px;
      background: var(--cyan);
      vertical-align: middle;
      animation: blink 1.2s step-end infinite;
    }

    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }

    /* ── PROJECTS ── */
    .projects { background: var(--bg); }

    .projects-inner {
      max-width: 1100px;
      margin: 0 auto;
    }

    .projects-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      margin-bottom: 48px;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .project-card {
      background: var(--bg-2);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 32px 28px;
      transition: all 0.25s;
      position: relative;
      overflow: hidden;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeUp 0.55s ease forwards;
    }

    .project-card:nth-child(1) { animation-delay: 0.1s; }
    .project-card:nth-child(2) { animation-delay: 0.2s; }
    .project-card:nth-child(3) { animation-delay: 0.3s; }

    .project-card::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, var(--cyan-dim), transparent 60%);
      opacity: 0;
      transition: opacity 0.3s;
      pointer-events: none;
    }

    .project-card:hover {
      border-color: var(--border-hi);
      transform: translateY(-4px);
      box-shadow: 0 16px 48px rgba(0,0,0,0.4), 0 0 0 1px var(--border-hi);
    }

    .project-card:hover::after { opacity: 1; }

    .project-num {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--text-dim);
      letter-spacing: 0.1em;
      margin-bottom: 20px;
    }

    .project-title {
      font-family: var(--display);
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--text);
      margin-bottom: 10px;
      letter-spacing: -0.01em;
    }

    .project-desc {
      font-size: 0.88rem;
      color: var(--text-mid);
      line-height: 1.75;
      margin-bottom: 28px;
      font-weight: 300;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }

    .tag {
      font-family: var(--mono);
      font-size: 0.7rem;
      padding: 3px 10px;
      border-radius: 4px;
      background: rgba(255,255,255,0.05);
      color: var(--text-mid);
      border: 1px solid var(--border);
      letter-spacing: 0.04em;
    }

    .tag.hi {
      background: var(--cyan-dim);
      color: var(--cyan);
      border-color: rgba(0,229,204,0.2);
    }

    /* ── SKILLS ── */
    .skills { background: var(--bg-2); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }

    .skills-inner { max-width: 1100px; margin: 0 auto; }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 16px;
      margin-top: 48px;
    }

    .skill-group {
      background: var(--bg-3);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 24px 20px;
      transition: border-color 0.2s;
    }

    .skill-group:hover { border-color: var(--border-hi); }

    .skill-group-title {
      font-family: var(--mono);
      font-size: 0.7rem;
      font-weight: 500;
      letter-spacing: 0.1em;
      color: var(--cyan);
      margin-bottom: 18px;
      text-transform: uppercase;
    }

    .skill-list {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .skill-list li {
      font-size: 0.88rem;
      color: var(--text-mid);
      display: flex;
      align-items: center;
      gap: 10px;
      font-family: var(--mono);
    }

    .skill-list li::before {
      content: '›';
      color: var(--text-dim);
      font-size: 1rem;
    }

    /* ── CONTACT ── */
    .contact {
      background: var(--bg);
      text-align: center;
    }

    .contact-inner {
      max-width: 600px;
      margin: 0 auto;
    }

    .contact-sub {
      color: var(--text-mid);
      font-size: 1rem;
      max-width: 440px;
      margin: 0 auto 48px;
      font-weight: 300;
      line-height: 1.75;
    }

    .contact-links {
      display: flex;
      justify-content: center;
      gap: 14px;
      flex-wrap: wrap;
    }

    .contact-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 12px 24px;
      border-radius: 8px;
      text-decoration: none;
      font-weight: 500;
      font-size: 0.88rem;
      transition: all 0.2s;
      font-family: var(--mono);
      letter-spacing: 0.02em;
    }

    .link-cyan {
      background: var(--cyan);
      color: var(--bg);
      font-weight: 600;
    }

    .link-cyan:hover {
      background: #00ccb4;
      transform: translateY(-2px);
      box-shadow: 0 8px 32px var(--cyan-glow);
    }

    .link-outline {
      background: transparent;
      color: var(--text-mid);
      border: 1px solid var(--border);
    }

    .link-outline:hover {
      color: var(--text);
      border-color: rgba(255,255,255,0.2);
      transform: translateY(-2px);
    }

    .link-resume {
      background: transparent;
      color: var(--cyan);
      border: 1px solid var(--border-hi);
    }

    .link-resume:hover {
      background: var(--cyan-dim);
      transform: translateY(-2px);
    }

    /* ── FOOTER ── */
    footer {
      background: var(--bg-2);
      border-top: 1px solid var(--border);
      padding: 24px 48px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      position: relative;
      z-index: 1;
    }

    .footer-left {
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--text-dim);
    }

    .footer-left span { color: var(--cyan); }

    .footer-right {
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--text-dim);
    }

    /* ── DIVIDER ── */
    .divider {
      width: 48px; height: 2px;
      background: linear-gradient(90deg, var(--cyan), transparent);
      margin: 20px 0 40px;
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      nav { padding: 0 24px; }
      section { padding: 72px 24px; }
      .hero { padding: 64px 24px 80px; }
      .about-inner { grid-template-columns: 1fr; gap: 48px; }
      .projects-grid { grid-template-columns: 1fr; }
      .skills-grid { grid-template-columns: 1fr 1fr; }
      .nav-links { gap: 20px; }
      footer { flex-direction: column; gap: 8px; text-align: center; padding: 20px 24px; }
    }

    @media (max-width: 600px) {
      .skills-grid { grid-template-columns: 1fr; }
      .projects-header { flex-direction: column; align-items: flex-start; gap: 16px; }
      .nav-links { display: none; }
      .hero-scroll { display: none; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <a href="#" class="nav-logo">gp<span>@dev</span>:~$</a>
    <ul class="nav-links">
      <li><a href="#about">about</a></li>
      <li><a href="#projects">projects</a></li>
      <li><a href="#skills">skills</a></li>
      <li><a href="GPineda_Resume.pdf" download class="nav-resume">↓ resume</a></li>
      <li><a href="#contact" class="nav-cta">hire me</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-glow"></div>
    <div class="hero-content">
      <div class="hero-eyebrow">available for freelance work</div>
      <h1>Gustavo<br/>Pineda<span class="accent">.</span></h1>
      <p class="hero-sub">
        Software developer who builds iOS apps, full-stack web platforms, and everything in between. 
        I came from the business world — so I build things that actually make sense to ship.
      </p>
      <div class="hero-ctas">
        <a href="#projects" class="btn btn-primary">View my work</a>
        <a href="https://github.com/GitGudGus" target="_blank" class="btn btn-ghost">GitHub ↗</a>
      </div>
    </div>
    <div class="hero-scroll">
      <span class="scroll-line"></span>
      scroll to explore
    </div>
  </section>

  <!-- ABOUT -->
  <section class="about" id="about">
    <div class="about-inner">
      <div class="about-text">
        <div class="section-tag">about</div>
        <h2 class="section-title">I build for the end user, not the résumé.</h2>
        <div class="divider"></div>
        <p>
           I didn't always write code. I came from the business industry, which means I think 
          about <strong>why</strong> software gets built just as much as <strong>how</strong>. 
          I transitioned into computer science in 2023, earned my Bachelor's at Florida 
          International University, and haven't looked back.
        </p>
        <p>
          Since then I've led iOS app development, contributed to an open-source platform 
          with <strong>10,000+ monthly active users</strong>, and built full e-commerce systems 
          from scratch. I work across mobile and web — and having a business background means 
          I think about <strong>what to build</strong>, not just how.
        </p>
        <a href="#contact" class="btn btn-ghost" style="margin-top: 12px;">Let's talk →</a>
      </div>

      <div class="about-terminal">
        <div class="terminal-bar">
          <span class="t-dot red"></span>
          <span class="t-dot yellow"></span>
          <span class="t-dot green"></span>
        </div>
        <div class="terminal-body">
          <div class="t-line"><span class="t-prompt">~$</span><span class="t-cmd">whoami</span></div>
          <div class="t-out"><span class="hi">gustavo_pineda</span> — developer</div>
          <br/>
          <div class="t-line"><span class="t-prompt">~$</span><span class="t-cmd">cat stats.json</span></div>
          <div class="t-out">{</div>
          <div class="t-out">&nbsp;&nbsp;"open_source_users": <span class="hi">"10k+"</span>,</div>
          <div class="t-out">&nbsp;&nbsp;"shipped_projects": <span class="hi">3</span>,</div>
          <div class="t-out">&nbsp;&nbsp;"years_experience": <span class="hi">3</span>,</div>
          <div class="t-out">&nbsp;&nbsp;"background": <span class="org">"business + CS"</span></div>
          <div class="t-out">}</div>
          <br/>
          <div class="t-line"><span class="t-prompt">~$</span><span class="t-cmd">echo $STATUS</span></div>
          <div class="t-out"><span class="hi">open_to_work=true</span></div>
          <br/>
          <div class="t-line"><span class="t-prompt">~$</span><span class="t-cursor"></span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects" class="projects">
    <div class="projects-inner">
      <div class="projects-header">
        <div>
          <div class="section-tag">selected work</div>
          <h2 class="section-title">Things I've shipped.</h2>
        </div>
        <a href="https://github.com/GitGudGus" target="_blank" class="btn btn-ghost">
          All projects ↗
        </a>
      </div>
      <div class="projects-grid">

        <div class="project-card">
          <div class="project-num">01 — iOS</div>
          <div class="project-title">LocalEventFinder</div>
          <p class="project-desc">
            Led a team to build a native iOS app connecting users to events nearby. 
            End-to-end architecture, real-time Firebase sync, and shipped to the App Store.
          </p>
          <div class="project-tags">
            <span class="tag hi">Lead Dev</span>
            <span class="tag">SwiftUI</span>
            <span class="tag">Firebase</span>
            <span class="tag">iOS</span>
          </div>
        </div>

        <div class="project-card">
          <div class="project-num">02 — Open Source</div>
          <div class="project-title">Baserow.io</div>
          <p class="project-desc">
            Contributor to a no-code database platform with 10k+ monthly active users. 
            Shipped production error handling improvements across distributed undo/restore flows.
          </p>
          <div class="project-tags">
            <span class="tag hi">10k+ MAU</span>
            <span class="tag">Python</span>
            <span class="tag">Docker</span>
            <span class="tag">OSS</span>
          </div>
        </div>

        <div class="project-card">
          <div class="project-num">03 — Web</div>
          <div class="project-title">Doodlebyte Co.</div>
          <p class="project-desc">
            Built a full e-commerce platform — migrated a vanilla HTML/CSS codebase to a 
            scalable Next.js/React architecture without losing an ounce of brand character.
          </p>
          <div class="project-tags">
            <span class="tag hi">E-commerce</span>
            <span class="tag">Next.js</span>
            <span class="tag">React</span>
            <span class="tag">Full Stack</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="skills" id="skills">
    <div class="skills-inner">
      <div class="section-tag">stack</div>
      <h2 class="section-title">What I work with.</h2>
      <div class="skills-grid">
        <div class="skill-group">
          <div class="skill-group-title">Mobile</div>
          <ul class="skill-list">
            <li>Swift</li>
            <li>SwiftUI</li>
            <li>ParseSwift</li>
            <li>Firebase</li>
            <li>iOS SDK</li>
          </ul>
        </div>
        <div class="skill-group">
          <div class="skill-group-title">Frontend</div>
          <ul class="skill-list">
            <li>React</li>
            <li>Next.js</li>
            <li>JavaScript</li>
            <li>HTML / CSS</li>
            <li>Tailwind</li>
          </ul>
        </div>
        <div class="skill-group">
          <div class="skill-group-title">Backend</div>
          <ul class="skill-list">
            <li>Python</li>
            <li>Flask</li>
            <li>REST APIs</li>
            <li>SQL</li>
            <li>Docker</li>
          </ul>
        </div>
        <div class="skill-group">
          <div class="skill-group-title">Other</div>
          <ul class="skill-list">
            <li>Git / GitHub</li>
            <li>Streamlit</li>
            <li>Agile</li>
            <li>Team lead</li>
            <li>Biz strategy</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="contact" id="contact">
    <div class="contact-inner">
      <div class="section-tag" style="justify-content: center;">contact</div>
      <h2 class="section-title">Let's build something.</h2>
      <div class="divider" style="margin: 20px auto 32px;"></div>
      <p class="contact-sub">
        Have a project, an idea, or just want to talk shop? My inbox is open.
      </p>
      <div class="contact-links">
        <a href="mailto:guspineda93@gmail.com" class="contact-link link-cyan">
          ✉ Say Hello
        </a>
        <a href="GPineda_Resume.pdf" download class="contact-link link-resume">
          ↓ Download Resume
        </a>
        <a href="https://github.com/GitGudGus" target="_blank" class="contact-link link-outline">
          GitHub ↗
        </a>
        <a href="https://linkedin.com/in/g-pineda93/" target="_blank" class="contact-link link-outline">
          LinkedIn ↗
        </a>
      </div>
    </div>
  </section>

  <footer>
    <div class="footer-left">// designed & built by <span>Gustavo Pineda</span> · 2026</div>
    <div class="footer-right">Miami, FL</div>
  </footer>

  <script>// animations handled via CSS</script>

</body>
</html>
