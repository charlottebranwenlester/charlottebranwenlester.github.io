# charlottebranwenlester.github.io
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Charlotte — IT & Tech</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0a0e14;
      --surface: #111620;
      --border: #1e2738;
      --accent: #00e5ff;
      --accent2: #7b5ea7;
      --text: #c9d4e8;
      --muted: #5a6a88;
      --white: #f0f4ff;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Mono', monospace;
      font-size: 14px;
      line-height: 1.7;
      overflow-x: hidden;
    }

    /* Grain overlay */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 9999;
      opacity: 0.4;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.2rem 3rem;
      border-bottom: 1px solid var(--border);
      background: rgba(10, 14, 20, 0.85);
      backdrop-filter: blur(12px);
    }

    .nav-logo {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: 1.1rem;
      color: var(--white);
      letter-spacing: -0.02em;
    }

    .nav-logo span { color: var(--accent); }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 0.8rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--accent); }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 0 3rem;
      position: relative;
      overflow: hidden;
    }

    .hero-grid-bg {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 60px 60px;
      opacity: 0.4;
      mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 30%, transparent 100%);
    }

    .hero-glow {
      position: absolute;
      width: 600px; height: 600px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(0,229,255,0.08) 0%, transparent 70%);
      top: 50%; left: 55%;
      transform: translate(-50%, -50%);
      pointer-events: none;
    }

    .hero-content {
      position: relative;
      max-width: 720px;
      animation: fadeUp 0.9s ease both;
    }

    .hero-tag {
      display: inline-block;
      border: 1px solid var(--accent);
      color: var(--accent);
      font-size: 0.7rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      padding: 0.3rem 0.8rem;
      border-radius: 2px;
      margin-bottom: 1.5rem;
      animation: fadeUp 0.9s 0.1s ease both;
    }

    h1 {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: clamp(2.8rem, 6vw, 5.5rem);
      line-height: 1.05;
      color: var(--white);
      letter-spacing: -0.03em;
      margin-bottom: 1.5rem;
      animation: fadeUp 0.9s 0.2s ease both;
    }

    h1 .accent { color: var(--accent); }

    .hero-desc {
      font-size: 0.95rem;
      color: var(--muted);
      max-width: 480px;
      margin-bottom: 2.5rem;
      animation: fadeUp 0.9s 0.3s ease both;
    }

    .hero-btns {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      animation: fadeUp 0.9s 0.4s ease both;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.75rem 1.6rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.8rem;
      letter-spacing: 0.05em;
      border-radius: 3px;
      text-decoration: none;
      transition: all 0.25s;
      cursor: pointer;
      border: none;
    }

    .btn-primary {
      background: var(--accent);
      color: var(--bg);
      font-weight: 500;
    }

    .btn-primary:hover {
      background: #33ecff;
      transform: translateY(-2px);
      box-shadow: 0 8px 30px rgba(0,229,255,0.25);
    }

    .btn-secondary {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
    }

    .btn-secondary:hover {
      border-color: var(--accent);
      color: var(--accent);
      transform: translateY(-2px);
    }

    /* scroll indicator */
    .scroll-hint {
      position: absolute;
      bottom: 2.5rem;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.4rem;
      color: var(--muted);
      font-size: 0.65rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      animation: fadeIn 1.5s 1s ease both;
    }

    .scroll-line {
      width: 1px;
      height: 40px;
      background: linear-gradient(to bottom, var(--accent), transparent);
      animation: scrollPulse 2s ease-in-out infinite;
    }

    /* ── SECTIONS ── */
    section {
      padding: 7rem 3rem;
      max-width: 1100px;
      margin: 0 auto;
    }

    .section-label {
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 0.8rem;
    }

    h2 {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: clamp(1.8rem, 3.5vw, 3rem);
      color: var(--white);
      letter-spacing: -0.02em;
      margin-bottom: 3rem;
    }

    /* ── ABOUT ── */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
    }

    .about-text p {
      color: var(--text);
      margin-bottom: 1rem;
      font-size: 0.9rem;
    }

    .about-text p:last-child { margin-bottom: 0; }

    .stat-block {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
    }

    .stat {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 1.5rem;
      border-radius: 4px;
      transition: border-color 0.3s;
    }

    .stat:hover { border-color: var(--accent); }

    .stat-num {
      font-family: 'Syne', sans-serif;
      font-size: 2rem;
      font-weight: 800;
      color: var(--accent);
      line-height: 1;
      margin-bottom: 0.4rem;
    }

    .stat-label {
      font-size: 0.72rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.1em;
    }

    /* ── SKILLS ── */
    #skills { background: var(--surface); max-width: 100%; padding: 7rem 3rem; }
    #skills > * { max-width: 1100px; margin-left: auto; margin-right: auto; }
    #skills h2 { max-width: 1100px; margin: 0 auto 3rem; }
    #skills .section-label { max-width: 1100px; margin: 0 auto 0.8rem; }

    .skills-grid {
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1rem;
    }

    .skill-card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 1.2rem 1.4rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
      transition: all 0.25s;
    }

    .skill-card:hover {
      border-color: var(--accent);
      transform: translateY(-3px);
      box-shadow: 0 8px 24px rgba(0,229,255,0.07);
    }

    .skill-icon {
      font-size: 1.4rem;
      flex-shrink: 0;
    }

    .skill-name {
      font-size: 0.82rem;
      color: var(--white);
    }

    /* ── PROJECTS ── */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 1.5rem;
    }

    .project-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 1.8rem;
      transition: all 0.3s;
      position: relative;
      overflow: hidden;
    }

    .project-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.3s;
    }

    .project-card:hover::before { transform: scaleX(1); }
    .project-card:hover { border-color: transparent; transform: translateY(-4px); }

    .project-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 1rem;
    }

    .project-emoji { font-size: 1.8rem; }

    .project-links { display: flex; gap: 0.5rem; }

    .project-link {
      color: var(--muted);
      text-decoration: none;
      font-size: 0.75rem;
      padding: 0.3rem 0.6rem;
      border: 1px solid var(--border);
      border-radius: 2px;
      transition: all 0.2s;
    }

    .project-link:hover { color: var(--accent); border-color: var(--accent); }

    .project-title {
      font-family: 'Syne', sans-serif;
      font-weight: 600;
      font-size: 1.1rem;
      color: var(--white);
      margin-bottom: 0.5rem;
    }

    .project-desc {
      font-size: 0.82rem;
      color: var(--muted);
      margin-bottom: 1.2rem;
      line-height: 1.6;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
    }

    .tag {
      font-size: 0.68rem;
      color: var(--accent);
      border: 1px solid rgba(0,229,255,0.25);
      padding: 0.2rem 0.6rem;
      border-radius: 2px;
      letter-spacing: 0.05em;
    }

    /* ── CONTACT ── */
    #contact {
      text-align: center;
    }

    #contact h2 { margin-bottom: 1rem; }

    .contact-sub {
      color: var(--muted);
      font-size: 0.9rem;
      margin-bottom: 2.5rem;
    }

    .contact-links {
      display: flex;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
    }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--border);
      padding: 2rem 3rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      color: var(--muted);
      font-size: 0.75rem;
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to   { opacity: 1; }
    }

    @keyframes scrollPulse {
      0%, 100% { opacity: 0.3; }
      50%       { opacity: 1; }
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { gap: 1rem; }
      #hero { padding: 0 1.5rem; }
      section { padding: 5rem 1.5rem; }
      .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
      footer { flex-direction: column; gap: 0.5rem; text-align: center; }
      #skills { padding: 5rem 1.5rem; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">charlotte<span>.</span>dev</div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section id="hero">
    <div class="hero-grid-bg"></div>
    <div class="hero-glow"></div>
    <div class="hero-content">
      <div class="hero-tag">Available for opportunities</div>
      <h1>Hi, I'm<br><span class="accent">Charlotte.</span></h1>
      <p class="hero-desc">
        IT enthusiast exploring networks, systems, and infastructure.
        I love solving technical problems and building things that work.
      </p>
      <div class="hero-btns">
        <a href="#projects" class="btn btn-primary">View My Work →</a>
        <a href="#contact" class="btn btn-secondary">Get In Touch</a>
      </div>
    </div>
    <div class="scroll-hint">
      <div class="scroll-line"></div>
      scroll
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="section-label">// about me</div>
    <h2>A bit about Charlotte</h2>
    <div class="about-grid">
      <div class="about-text">
        <p>
          I'm a passionate IT student and enthusiast with a strong interest in how technology shapes the world around us — from the networks that connect us to the systems that keep everything running.
        </p>
        <p>
          I enjoy digging into how things work under the hood — whether that's troubleshooting a tricky network issue, setting up a homelab, or learning a new scripting language. I'm always building, breaking, and learning.
        </p>
        <p>
          
        </p>
      </div>
      <div class="stat-block">
        <div class="stat">
          <div class="stat-num">5+</div>
          <div class="stat-label">Projects built</div>
        </div>
        <div class="stat">
          <div class="stat-num">10+</div>
          <div class="stat-label">Technologies explored</div>
        </div>
        <div class="stat">
          <div class="stat-num">∞</div>
          <div class="stat-label">Curiosity level</div>
        </div>
        <div class="stat">
          <div class="stat-num">24/7</div>
          <div class="stat-label">Always learning</div>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills">
    <div class="section-label">// tools & technologies</div>
    <h2>What I work with</h2>
    <div class="skills-grid">
      <div class="skill-card"><span class="skill-icon">🐧</span><span class="skill-name">Linux / CLI</span></div>
      <div class="skill-card"><span class="skill-icon">🌐</span><span class="skill-name">Networking</span></div>
      <div class="skill-card"><span class="skill-icon">🐍</span><span class="skill-name">Python</span></div>
      <div class="skill-card"><span class="skill-icon">🔒</span><span class="skill-name">Cybersecurity</span></div>
      <div class="skill-card"><span class="skill-icon">🐳</span><span class="skill-name">Docker</span></div>
      <div class="skill-card"><span class="skill-icon">☁️</span><span class="skill-name">Cloud (AWS/Azure)</span></div>
      <div class="skill-card"><span class="skill-icon">🗄️</span><span class="skill-name">Databases / SQL</span></div>
      <div class="skill-card"><span class="skill-icon">🖥️</span><span class="skill-name">Windows Server</span></div>
      <div class="skill-card"><span class="skill-icon">📜</span><span class="skill-name">Bash Scripting</span></div>
      <div class="skill-card"><span class="skill-icon">🔧</span><span class="skill-name">Hardware & IT Support</span></div>
      <div class="skill-card"><span class="skill-icon">🕸️</span><span class="skill-name">HTML / CSS</span></div>
      <div class="skill-card"><span class="skill-icon">📡</span><span class="skill-name">TCP/IP & Protocols</span></div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="section-label">// featured projects</div>
    <h2>Things I've built</h2>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-header">
          <span class="project-emoji">🏠</span>
          <div class="project-links">
            <a href="#" class="project-link">GitHub</a>
          </div>
        </div>
        <div class="project-title">Home Lab Setup</div>
        <div class="project-desc">A self-hosted home lab with virtualization, network monitoring, and a personal VPN server. Used for hands-on learning and experimentation.</div>
        <div class="project-tags">
          <span class="tag">Proxmox</span>
          <span class="tag">pfSense</span>
          <span class="tag">WireGuard</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <span class="project-emoji">🔍</span>
          <div class="project-links">
            <a href="#" class="project-link">GitHub</a>
          </div>
        </div>
        <div class="project-title">Network Scanner Script</div>
        <div class="project-desc">A Python script that scans a local network for active hosts, open ports, and running services. Outputs a clean summary report.</div>
        <div class="project-tags">
          <span class="tag">Python</span>
          <span class="tag">Nmap</span>
          <span class="tag">Networking</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <span class="project-emoji">📊</span>
          <div class="project-links">
            <a href="#" class="project-link">GitHub</a>
          </div>
        </div>
        <div class="project-title">System Monitor Dashboard</div>
        <div class="project-desc">A lightweight web dashboard that displays real-time CPU, RAM, disk, and network stats for a Linux server. Deployed via Docker.</div>
        <div class="project-tags">
          <span class="tag">Docker</span>
          <span class="tag">Bash</span>
          <span class="tag">Linux</span>
        </div>
      </div>

    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <div class="section-label">// let's connect</div>
    <h2>Get in touch</h2>
    <p class="contact-sub">Whether it's an opportunity, a question, or just to say hello — my inbox is open.</p>
    <div class="contact-links">
      <a href="mailto:charlotte@example.com" class="btn btn-primary">✉️ Email Me</a>
      <a href="https://github.com/yourusername" target="_blank" class="btn btn-secondary">GitHub</a>
      <a href="https://linkedin.com/in/yourprofile" target="_blank" class="btn btn-secondary">LinkedIn</a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div>© 2026 Charlotte — Built with ☕ and curiosity</div>
    <div>charlotte<span style="color:var(--accent)">.</span>dev</div>
  </footer>

</body>
</html>
