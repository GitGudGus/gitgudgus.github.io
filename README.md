<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Gus — Developer & Builder</title>
  <link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,600;1,400&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #FAF8F5;
      --warm-white: #FFFEFB;
      --sand: #F0EBE3;
      --sand-dark: #E2D9CE;
      --sage: #7A9E87;
      --sage-light: #A8C5B0;
      --sage-dark: #5A7A66;
      --text-dark: #2C2A27;
      --text-mid: #5C5851;
      --text-light: #8C8880;
      --accent: #C4855A;
      --accent-light: #E8B898;
      --radius: 20px;
      --radius-sm: 12px;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--cream);
      color: var(--text-dark);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      padding: 20px 48px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(250, 248, 245, 0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(226, 217, 206, 0.4);
    }

    .nav-logo {
      font-family: 'Lora', serif;
      font-size: 1.2rem;
      color: var(--text-dark);
      text-decoration: none;
      font-weight: 600;
    }

    .nav-links {
      display: flex;
      gap: 32px;
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      color: var(--text-mid);
      font-size: 0.9rem;
      font-weight: 500;
      letter-spacing: 0.02em;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--sage-dark); }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 120px 48px 80px;
      position: relative;
      overflow: hidden;
    }

    .hero-bg {
      position: absolute;
      inset: 0;
      pointer-events: none;
      overflow: hidden;
    }

    .hero-blob {
      position: absolute;
      border-radius: 50%;
      filter: blur(80px);
      opacity: 0.35;
    }

    .blob-1 {
      width: 600px; height: 600px;
      background: radial-gradient(circle, var(--sage-light), transparent);
      top: -100px; right: -100px;
      animation: float 8s ease-in-out infinite;
    }

    .blob-2 {
      width: 400px; height: 400px;
      background: radial-gradient(circle, var(--accent-light), transparent);
      bottom: 0; left: -80px;
      animation: float 10s ease-in-out infinite reverse;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0) scale(1); }
      50% { transform: translateY(-30px) scale(1.05); }
    }

    .hero-content {
      max-width: 760px;
      position: relative;
      z-index: 1;
      opacity: 0;
      transform: translateY(30px);
      animation: fadeUp 0.9s ease forwards 0.2s;
    }

    @keyframes fadeUp {
      to { opacity: 1; transform: translateY(0); }
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: var(--sand);
      border: 1px solid var(--sand-dark);
      padding: 6px 16px;
      border-radius: 100px;
      font-size: 0.82rem;
      font-weight: 500;
      color: var(--sage-dark);
      margin-bottom: 28px;
      letter-spacing: 0.04em;
    }

    .tag-dot {
      width: 7px; height: 7px;
      background: var(--sage);
      border-radius: 50%;
      animation: pulse 2s ease infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    .hero h1 {
      font-family: 'Lora', serif;
      font-size: clamp(3rem, 7vw, 5.5rem);
      line-height: 1.1;
      color: var(--text-dark);
      margin-bottom: 12px;
    }

    .hero h1 em {
      font-style: italic;
      color: var(--sage-dark);
    }

    .hero-sub {
      font-size: clamp(1rem, 2vw, 1.2rem);
      color: var(--text-mid);
      max-width: 540px;
      margin-bottom: 44px;
      font-weight: 300;
      line-height: 1.7;
    }

    .hero-ctas {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
    }

    .btn {
      padding: 14px 28px;
      border-radius: 100px;
      font-size: 0.95rem;
      font-weight: 500;
      text-decoration: none;
      transition: all 0.25s;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      border: none;
      font-family: 'DM Sans', sans-serif;
    }

    .btn-primary {
      background: var(--text-dark);
      color: var(--warm-white);
    }

    .btn-primary:hover {
      background: var(--sage-dark);
      transform: translateY(-2px);
      box-shadow: 0 8px 24px rgba(90, 122, 102, 0.3);
    }

    .btn-secondary {
      background: var(--sand);
      color: var(--text-dark);
      border: 1px solid var(--sand-dark);
    }

    .btn-secondary:hover {
      background: var(--sand-dark);
      transform: translateY(-2px);
    }

    /* ── SECTIONS ── */
    section {
      padding: 100px 48px;
    }

    .section-label {
      font-size: 0.78rem;
      font-weight: 600;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--sage-dark);
      margin-bottom: 16px;
    }

    .section-title {
      font-family: 'Lora', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      line-height: 1.2;
      color: var(--text-dark);
      margin-bottom: 20px;
    }

    /* ── ABOUT ── */
    .about {
      background: var(--warm-white);
    }

    .about-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 80px;
      align-items: center;
    }

    .about-text p {
      color: var(--text-mid);
      font-size: 1.05rem;
      line-height: 1.8;
      margin-bottom: 20px;
      font-weight: 300;
    }

    .about-text p strong {
      color: var(--text-dark);
      font-weight: 500;
    }

    .about-stats {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
    }

    .stat-card {
      background: var(--sand);
      border-radius: var(--radius);
      padding: 28px 24px;
      border: 1px solid var(--sand-dark);
      transition: transform 0.2s;
    }

    .stat-card:hover { transform: translateY(-4px); }

    .stat-num {
      font-family: 'Lora', serif;
      font-size: 2.4rem;
      color: var(--text-dark);
      line-height: 1;
      margin-bottom: 6px;
    }

    .stat-num span { color: var(--sage-dark); }

    .stat-label {
      font-size: 0.85rem;
      color: var(--text-light);
      font-weight: 400;
    }

    /* ── PROJECTS ── */
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
      gap: 24px;
    }

    .project-card {
      background: var(--warm-white);
      border-radius: var(--radius);
      padding: 36px 32px;
      border: 1px solid var(--sand-dark);
      transition: all 0.3s;
      position: relative;
      overflow: hidden;
      opacity: 0;
      transform: translateY(24px);
    }

    .project-card.visible {
      animation: fadeUp 0.6s ease forwards;
    }

    .project-card:nth-child(2) { animation-delay: 0.1s; }
    .project-card:nth-child(3) { animation-delay: 0.2s; }

    .project-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--sage-light), var(--sage-dark));
      opacity: 0;
      transition: opacity 0.3s;
    }

    .project-card:hover::before { opacity: 1; }
    .project-card:hover {
      transform: translateY(-6px);
      box-shadow: 0 20px 48px rgba(44, 42, 39, 0.08);
    }

    .project-icon {
      width: 48px; height: 48px;
      background: var(--sand);
      border-radius: var(--radius-sm);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.4rem;
      margin-bottom: 20px;
    }

    .project-title {
      font-family: 'Lora', serif;
      font-size: 1.3rem;
      color: var(--text-dark);
      margin-bottom: 8px;
    }

    .project-desc {
      font-size: 0.92rem;
      color: var(--text-mid);
      line-height: 1.7;
      margin-bottom: 24px;
      font-weight: 300;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .tag {
      font-size: 0.75rem;
      font-weight: 500;
      padding: 4px 12px;
      border-radius: 100px;
      background: var(--sand);
      color: var(--text-mid);
      border: 1px solid var(--sand-dark);
    }

    .tag.highlight {
      background: rgba(122, 158, 135, 0.15);
      color: var(--sage-dark);
      border-color: rgba(122, 158, 135, 0.3);
    }

    /* ── SKILLS ── */
    .skills {
      background: var(--warm-white);
    }

    .skills-inner {
      max-width: 1100px;
      margin: 0 auto;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
      margin-top: 48px;
    }

    .skill-group {
      background: var(--sand);
      border-radius: var(--radius);
      padding: 28px 24px;
      border: 1px solid var(--sand-dark);
    }

    .skill-group-title {
      font-size: 0.78rem;
      font-weight: 600;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--sage-dark);
      margin-bottom: 16px;
    }

    .skill-list {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .skill-list li {
      font-size: 0.92rem;
      color: var(--text-mid);
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .skill-list li::before {
      content: '';
      width: 5px; height: 5px;
      background: var(--sage-light);
      border-radius: 50%;
      flex-shrink: 0;
    }

    /* ── CONTACT ── */
    .contact {
      background: var(--text-dark);
      color: var(--warm-white);
      text-align: center;
      padding: 120px 48px;
    }

    .contact .section-label { color: var(--sage-light); }

    .contact .section-title {
      color: var(--warm-white);
      margin-bottom: 16px;
    }

    .contact-sub {
      color: rgba(255,255,255,0.55);
      font-size: 1.05rem;
      max-width: 440px;
      margin: 0 auto 48px;
      font-weight: 300;
    }

    .contact-links {
      display: flex;
      justify-content: center;
      gap: 16px;
      flex-wrap: wrap;
    }

    .contact-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 14px 28px;
      border-radius: 100px;
      text-decoration: none;
      font-weight: 500;
      font-size: 0.95rem;
      transition: all 0.25s;
    }

    .link-ghost {
      background: rgba(255,255,255,0.08);
      color: var(--warm-white);
      border: 1px solid rgba(255,255,255,0.15);
    }

    .link-ghost:hover {
      background: rgba(255,255,255,0.14);
      transform: translateY(-2px);
    }

    .link-sage {
      background: var(--sage);
      color: var(--warm-white);
    }

    .link-sage:hover {
      background: var(--sage-dark);
      transform: translateY(-2px);
    }

    /* ── FOOTER ── */
    footer {
      background: var(--text-dark);
      border-top: 1px solid rgba(255,255,255,0.06);
      padding: 24px 48px;
      text-align: center;
      color: rgba(255,255,255,0.25);
      font-size: 0.82rem;
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      nav { padding: 16px 24px; }
      .hero { padding: 100px 24px 60px; }
      section { padding: 72px 24px; }
      .about-inner { grid-template-columns: 1fr; gap: 48px; }
      .projects-grid { grid-template-columns: 1fr; }
      .skills-grid { grid-template-columns: 1fr 1fr; }
      .nav-links { gap: 20px; }
    }

    @media (max-width: 600px) {
      .skills-grid { grid-template-columns: 1fr; }
      .projects-header { flex-direction: column; align-items: flex-start; gap: 16px; }
      .about-stats { grid-template-columns: 1fr 1fr; }
      nav { padding: 14px 20px; }
      .nav-links { display: none; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <a href="#" class="nav-logo">Gus.</a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg">
      <div class="hero-blob blob-1"></div>
      <div class="hero-blob blob-2"></div>
    </div>
    <div class="hero-content">
      <div class="hero-tag">
        <span class="tag-dot"></span>
        Available for freelance work
      </div>
      <h1>Building things<br/><em>people actually use.</em></h1>
      <p class="hero-sub">
        I'm a software developer specializing in iOS apps and full-stack web development. 
        I help businesses and teams ship real, polished products — fast.
      </p>
      <div class="hero-ctas">
        <a href="#projects" class="btn btn-primary">See my work ↓</a>
        <a href="#contact" class="btn btn-secondary">Get in touch</a>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section class="about" id="about">
    <div class="about-inner">
      <div class="about-text">
        <div class="section-label">About me</div>
        <h2 class="section-title">A builder who came from the business world.</h2>
        <p>
          I didn't always write code. I came from the business industry, which means I think 
          about <strong>why</strong> software gets built just as much as <strong>how</strong>. 
          I transitioned into computer science in 2022, earned my Bachelor's at Florida 
          International University, and haven't looked back.
        </p>
        <p>
          I've led teams, shipped apps to the App Store, contributed to open-source platforms 
          with tens of thousands of users, and built e-commerce products from the ground up. 
          I work across the full stack — whatever your project needs.
        </p>
        <a href="#contact" class="btn btn-primary" style="margin-top:8px;">Let's work together →</a>
      </div>
      <div class="about-stats">
        <div class="stat-card">
          <div class="stat-num">10<span>k+</span></div>
          <div class="stat-label">Monthly active users on open-source project</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">3<span>+</span></div>
          <div class="stat-label">Shipped apps & platforms</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">3<span>yrs</span></div>
          <div class="stat-label">Full-stack & mobile development</div>
        </div>
        <div class="stat-card">
          <div class="stat-num"><span>∞</span></div>
          <div class="stat-label">Business context most devs lack</div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="projects-inner">
      <div class="projects-header">
        <div>
          <div class="section-label">Selected work</div>
          <h2 class="section-title">Projects I'm proud of.</h2>
        </div>
        <a href="https://github.com/GitGudGus" target="_blank" class="btn btn-secondary" style="white-space:nowrap">
          GitHub ↗
        </a>
      </div>
      <div class="projects-grid">

        <div class="project-card">
          <div class="project-icon">📍</div>
          <div class="project-title">LocalEventFinder</div>
          <p class="project-desc">
            Lead developer on a native iOS app connecting users to local events. 
            Built end-to-end with SwiftUI, Firebase backend, and real-time data sync.
          </p>
          <div class="project-tags">
            <span class="tag highlight">iOS</span>
            <span class="tag">SwiftUI</span>
            <span class="tag">Firebase</span>
            <span class="tag">Lead Dev</span>
          </div>
        </div>

        <div class="project-card">
          <div class="project-icon">🔧</div>
          <div class="project-title">Baserow.io</div>
          <p class="project-desc">
            Open-source contributor to a no-code database platform with 10,000+ monthly active users. 
            Shipped improved error handling across undo/restore flows in a distributed system.
          </p>
          <div class="project-tags">
            <span class="tag highlight">Open Source</span>
            <span class="tag">Python</span>
            <span class="tag">Docker</span>
            <span class="tag">10k+ MAU</span>
          </div>
        </div>

        <div class="project-card">
          <div class="project-icon">🛍️</div>
          <div class="project-title">Doodlebyte Co.</div>
          <p class="project-desc">
            Built a full e-commerce platform from the ground up — migrating from vanilla HTML 
            to a scalable Next.js/React architecture while preserving the brand's playful aesthetic.
          </p>
          <div class="project-tags">
            <span class="tag highlight">Web</span>
            <span class="tag">Next.js</span>
            <span class="tag">React</span>
            <span class="tag">E-commerce</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="skills" id="skills">
    <div class="skills-inner">
      <div class="section-label">What I work with</div>
      <h2 class="section-title">Skills & technologies.</h2>
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
            <li>Tailwind CSS</li>
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
          <div class="skill-group-title">Tools & More</div>
          <ul class="skill-list">
            <li>Git / GitHub</li>
            <li>Streamlit</li>
            <li>Agile workflows</li>
            <li>Team leadership</li>
            <li>Business strategy</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="contact" id="contact">
    <div class="section-label">Get in touch</div>
    <h2 class="section-title">Let's build something together.</h2>
    <p class="contact-sub">
      Whether you have a project in mind or just want to explore what's possible — I'd love to hear from you.
    </p>
    <div class="contact-links">
      <a href="mailto:your@email.com" class="contact-link link-sage">
        ✉️ Send me an email
      </a>
      <a href="https://github.com/GitGudGus" target="_blank" class="contact-link link-ghost">
        GitHub ↗
      </a>
      <a href="https://linkedin.com/in/yourhandle" target="_blank" class="contact-link link-ghost">
        LinkedIn ↗
      </a>
    </div>
  </section>

  <footer>
    Designed & built by Gus · 2025
  </footer>

  <script>
    // Scroll-reveal for project cards
    const cards = document.querySelectorAll('.project-card');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.15 });
    cards.forEach(card => observer.observe(card));
  </script>

</body>
</html>
