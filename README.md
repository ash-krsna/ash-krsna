<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Akash | Developer Portfolio</title>
  <meta name="description" content="Akash - Frontend Developer, React Learner, Cyber Security Enthusiast" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&family=Fira+Code:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #07111f;
      --bg-soft: #0b1728;
      --card: rgba(17, 25, 40, 0.62);
      --card-strong: rgba(15, 23, 42, 0.88);
      --border: rgba(148, 163, 184, 0.16);
      --text: #e5eefc;
      --muted: #9fb0c9;
      --primary: #38bdf8;
      --secondary: #22d3ee;
      --accent: #8b5cf6;
      --success: #22c55e;
      --shadow: 0 24px 60px rgba(0, 0, 0, 0.35);
      --radius-xl: 28px;
      --radius-lg: 22px;
      --radius-md: 16px;
      --max-width: 1180px;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: "Outfit", sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at top left, rgba(56, 189, 248, 0.14), transparent 30%),
        radial-gradient(circle at top right, rgba(139, 92, 246, 0.14), transparent 24%),
        radial-gradient(circle at bottom left, rgba(34, 211, 238, 0.1), transparent 22%),
        linear-gradient(135deg, #030712 0%, #07111f 45%, #0b1324 100%);
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(255,255,255,0.02) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.02) 1px, transparent 1px);
      background-size: 40px 40px;
      mask-image: linear-gradient(to bottom, rgba(0,0,0,0.4), transparent);
      pointer-events: none;
      z-index: -1;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .container {
      width: min(var(--max-width), calc(100% - 32px));
      margin: 0 auto;
    }

    .glass {
      background: var(--card);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
    }

    .section {
      padding: 100px 0;
    }

    .section-title {
      font-size: clamp(2rem, 4vw, 3rem);
      margin: 0 0 14px;
      line-height: 1.05;
    }

    .section-subtitle {
      max-width: 700px;
      margin: 0 0 36px;
      color: var(--muted);
      font-size: 1.05rem;
      line-height: 1.8;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 10px 16px;
      border-radius: 999px;
      font-size: 0.92rem;
      color: #d9f7ff;
      background: rgba(56, 189, 248, 0.08);
      border: 1px solid rgba(56, 189, 248, 0.18);
    }

    .badge-dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--secondary), var(--primary));
      box-shadow: 0 0 16px rgba(34, 211, 238, 0.8);
    }

    .btn-group {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      margin-top: 30px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      min-width: 160px;
      padding: 14px 22px;
      border-radius: 16px;
      border: 1px solid transparent;
      font-weight: 600;
      transition: transform 0.28s ease, box-shadow 0.28s ease, border-color 0.28s ease, background 0.28s ease;
      cursor: pointer;
    }

    .btn:hover {
      transform: translateY(-3px);
    }

    .btn-primary {
      color: #04111f;
      background: linear-gradient(135deg, var(--secondary), var(--primary));
      box-shadow: 0 18px 40px rgba(34, 211, 238, 0.24);
    }

    .btn-secondary {
      color: var(--text);
      border-color: rgba(148, 163, 184, 0.18);
      background: rgba(15, 23, 42, 0.55);
    }

    .btn-secondary:hover {
      border-color: rgba(56, 189, 248, 0.4);
      box-shadow: 0 16px 30px rgba(0, 0, 0, 0.22);
    }

    .nav-wrap {
      position: sticky;
      top: 18px;
      z-index: 50;
      padding-top: 18px;
    }

    .navbar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      padding: 14px 18px;
      border-radius: 22px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 700;
      letter-spacing: 0.04em;
    }

    .brand-mark {
      width: 42px;
      height: 42px;
      border-radius: 14px;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, var(--accent), var(--primary));
      color: white;
      font-family: "Fira Code", monospace;
      box-shadow: 0 10px 26px rgba(56, 189, 248, 0.24);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 18px;
      flex-wrap: wrap;
    }

    .nav-links a {
      color: var(--muted);
      font-weight: 500;
      transition: color 0.25s ease;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .hero {
      padding: 70px 0 80px;
      min-height: calc(100vh - 110px);
      display: flex;
      align-items: center;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 32px;
      align-items: center;
    }

    .hero-copy h1 {
      font-size: clamp(3rem, 7vw, 5.6rem);
      line-height: 0.95;
      margin: 18px 0 18px;
      letter-spacing: -0.05em;
    }

    .hero-copy h1 span {
      background: linear-gradient(135deg, #ffffff 0%, #c4f1ff 35%, #8be9ff 70%, #b794f4 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .typing-wrap {
      min-height: 44px;
      font-size: clamp(1rem, 2vw, 1.25rem);
      color: var(--secondary);
      font-family: "Fira Code", monospace;
      margin-bottom: 22px;
    }

    .typing-wrap::after {
      content: "|";
      margin-left: 4px;
      color: #8be9ff;
      animation: blink 0.8s infinite;
    }

    .hero-copy p {
      font-size: 1.08rem;
      line-height: 1.9;
      color: var(--muted);
      max-width: 650px;
      margin: 0;
    }

    .hero-card {
      border-radius: var(--radius-xl);
      padding: 24px;
      position: relative;
      overflow: hidden;
    }

    .hero-card::before {
      content: "";
      position: absolute;
      inset: auto -10% 65% auto;
      width: 200px;
      height: 200px;
      background: radial-gradient(circle, rgba(34,211,238,0.28), transparent 70%);
      pointer-events: none;
    }

    .terminal {
      border-radius: 22px;
      background: rgba(2, 6, 23, 0.84);
      border: 1px solid rgba(148, 163, 184, 0.12);
      overflow: hidden;
    }

    .terminal-top {
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 14px 16px;
      border-bottom: 1px solid rgba(148, 163, 184, 0.1);
    }

    .terminal-top span {
      width: 11px;
      height: 11px;
      border-radius: 50%;
      display: inline-block;
    }

    .terminal-top span:nth-child(1) { background: #f87171; }
    .terminal-top span:nth-child(2) { background: #facc15; }
    .terminal-top span:nth-child(3) { background: #4ade80; }

    .terminal-body {
      padding: 18px;
      font-family: "Fira Code", monospace;
      color: #b6ffe4;
      font-size: 0.94rem;
      line-height: 1.9;
    }

    .prompt {
      color: #67e8f9;
    }

    .cards-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 18px;
      margin-top: 26px;
    }

    .mini-card {
      padding: 18px;
      border-radius: var(--radius-md);
      background: rgba(15, 23, 42, 0.56);
      border: 1px solid rgba(148, 163, 184, 0.1);
    }

    .mini-card strong {
      display: block;
      font-size: 1.5rem;
      margin-top: 8px;
    }

    .mini-card span {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 28px;
    }

    .panel {
      padding: 28px;
      border-radius: var(--radius-xl);
    }

    .panel p,
    .panel li {
      color: var(--muted);
      line-height: 1.9;
      font-size: 1rem;
    }

    .list {
      margin: 0;
      padding-left: 18px;
    }

    .project-card {
      padding: 30px;
      border-radius: var(--radius-xl);
      position: relative;
      overflow: hidden;
      transition: transform 0.35s ease, border-color 0.35s ease, box-shadow 0.35s ease;
    }

    .project-card:hover {
      transform: translateY(-8px);
      border-color: rgba(56, 189, 248, 0.28);
      box-shadow: 0 28px 60px rgba(0, 0, 0, 0.35);
    }

    .project-card::after {
      content: "";
      position: absolute;
      inset: auto -60px -60px auto;
      width: 180px;
      height: 180px;
      background: radial-gradient(circle, rgba(56,189,248,0.18), transparent 70%);
      pointer-events: none;
    }

    .project-top {
      display: flex;
      justify-content: space-between;
      gap: 18px;
      align-items: start;
      margin-bottom: 20px;
    }

    .project-tag {
      padding: 8px 12px;
      border-radius: 999px;
      background: rgba(34, 197, 94, 0.12);
      color: #86efac;
      font-size: 0.88rem;
      border: 1px solid rgba(34, 197, 94, 0.18);
      white-space: nowrap;
    }

    .project-card h3 {
      margin: 0 0 10px;
      font-size: 1.6rem;
    }

    .project-card p {
      color: var(--muted);
      line-height: 1.9;
      margin: 0 0 20px;
    }

    .tech-pills,
    .skill-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .pill {
      padding: 9px 13px;
      border-radius: 999px;
      font-size: 0.9rem;
      background: rgba(15, 23, 42, 0.72);
      border: 1px solid rgba(148, 163, 184, 0.14);
      color: #d4def0;
    }

    .skill-columns {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 20px;
    }

    .skill-card {
      padding: 24px;
      border-radius: var(--radius-xl);
      transition: transform 0.28s ease, border-color 0.28s ease;
    }

    .skill-card:hover {
      transform: translateY(-6px);
      border-color: rgba(56, 189, 248, 0.26);
    }

    .skill-card h3 {
      margin: 0 0 16px;
      font-size: 1.2rem;
    }

    .skill-card ul {
      margin: 0;
      padding-left: 18px;
    }

    .skill-card li {
      color: var(--muted);
      line-height: 1.9;
    }

    .icons-panel {
      padding: 26px;
      border-radius: var(--radius-xl);
      margin-top: 28px;
      text-align: center;
    }

    .github-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 22px;
    }

    .github-card {
      padding: 26px;
      border-radius: var(--radius-xl);
    }

    .github-card p {
      color: var(--muted);
      line-height: 1.9;
    }

    .stats-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 18px;
      margin-top: 22px;
    }

    .stats-grid img,
    .stats-single img {
      width: 100%;
      border-radius: 18px;
      border: 1px solid rgba(148, 163, 184, 0.1);
    }

    .contact-card {
      padding: 30px;
      border-radius: var(--radius-xl);
      text-align: center;
    }

    .contact-card p {
      max-width: 700px;
      margin: 0 auto;
      color: var(--muted);
      line-height: 1.9;
    }

    footer {
      padding: 30px 0 60px;
      color: var(--muted);
      text-align: center;
    }

    .reveal {
      opacity: 0;
      transform: translateY(28px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    @keyframes blink {
      50% { opacity: 0; }
    }

    @media (max-width: 1024px) {
      .hero-grid,
      .about-grid,
      .skill-columns,
      .stats-grid {
        grid-template-columns: 1fr;
      }

      .hero {
        min-height: auto;
        padding-top: 40px;
      }
    }

    @media (max-width: 760px) {
      .section {
        padding: 76px 0;
      }

      .navbar {
        flex-direction: column;
        align-items: start;
      }

      .nav-links {
        gap: 12px;
      }

      .hero-copy h1 {
        font-size: 3rem;
      }

      .project-top {
        flex-direction: column;
      }

      .cards-grid {
        grid-template-columns: 1fr;
      }

      .btn {
        width: 100%;
      }

      .btn-group {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <div class="nav-wrap">
    <div class="container">
      <nav class="navbar glass">
        <a href="#home" class="brand">
          <div class="brand-mark">&lt;/&gt;</div>
          <span>Akash.dev</span>
        </a>
        <div class="nav-links">
          <a href="#about">About</a>
          <a href="#projects">Projects</a>
          <a href="#skills">Skills</a>
          <a href="#github">GitHub</a>
          <a href="#contact">Contact</a>
        </div>
      </nav>
    </div>
  </div>

  <header class="hero" id="home">
    <div class="container">
      <div class="hero-grid">
        <div class="hero-copy reveal">
          <div class="badge">
            <span class="badge-dot"></span>
            Modern Portfolio / Frontend + Security Vibe
          </div>
          <h1>Hi, I'm <span>Akash</span></h1>
          <div class="typing-wrap">
            <span id="typing"></span>
          </div>
          <p>
            Frontend Developer, React learner, and cyber security enthusiast building modern web experiences with clean UI, smooth interactions, and a strong developer mindset.
          </p>
          <div class="btn-group">
            <a class="btn btn-primary" href="#projects">View Projects</a>
            <a class="btn btn-secondary" href="https://github.com/ash-krsna" target="_blank" rel="noopener">GitHub Profile</a>
          </div>
          <div class="cards-grid">
            <div class="mini-card glass">
              <span>Current Focus</span>
              <strong>React + JS</strong>
            </div>
            <div class="mini-card glass">
              <span>Database Stack</span>
              <strong>MongoDB / MySQL</strong>
            </div>
            <div class="mini-card glass">
              <span>Mindset</span>
              <strong>Clean + Secure</strong>
            </div>
            <div class="mini-card glass">
              <span>Portfolio Style</span>
              <strong>Modern Dark UI</strong>
            </div>
          </div>
        </div>

        <div class="hero-card glass reveal">
          <div class="terminal">
            <div class="terminal-top">
              <span></span><span></span><span></span>
            </div>
            <div class="terminal-body">
              <div><span class="prompt">akash@portfolio:~$</span> whoami</div>
              <div>Frontend Developer | React Learner | Cyber Security Enthusiast</div>
              <br />
              <div><span class="prompt">akash@portfolio:~$</span> current-stack</div>
              <div>HTML / CSS / Bootstrap / JavaScript / React</div>
              <div>Node.js / MongoDB / MySQL</div>
              <br />
              <div><span class="prompt">akash@portfolio:~$</span> mission</div>
              <div>Build modern web apps with strong UI and a security-aware mindset.</div>
              <br />
              <div><span class="prompt">akash@portfolio:~$</span> status</div>
              <div>Learning. Building. Improving.</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>

  <section class="section" id="about">
    <div class="container">
      <div class="reveal">
        <div class="badge">
          <span class="badge-dot"></span>
          About Me
        </div>
        <h2 class="section-title">Building modern interfaces with a clean and curious mindset</h2>
        <p class="section-subtitle">
          I’m a passionate frontend developer focused on creating responsive, modern web applications while continuously learning the technologies that power full-stack development and secure systems.
        </p>
      </div>

      <div class="about-grid">
        <div class="panel glass reveal">
          <h3>Developer Profile</h3>
          <p>
            I enjoy building polished user interfaces and learning how great web products come together from frontend interactions to backend connectivity.
          </p>
          <ul class="list">
            <li>Passionate frontend developer building modern web applications</li>
            <li>Learning React, APIs, and full-stack development</li>
            <li>Exploring Cyber Security and ethical hacking</li>
            <li>Working with MongoDB and MySQL</li>
          </ul>
        </div>

        <div class="panel glass reveal">
          <h3>What drives me</h3>
          <p>
            I’m drawn to clean layouts, smooth user experiences, and thoughtful problem-solving. Alongside frontend development, I’m exploring web security fundamentals to better understand how to build safer and smarter applications.
          </p>
          <p>
            My goal is to grow into a developer who can create beautiful interfaces, connect them to real data, and understand the systems behind secure digital products.
          </p>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="projects">
    <div class="container">
      <div class="reveal">
        <div class="badge">
          <span class="badge-dot"></span>
          Featured Project
        </div>
        <h2 class="section-title">Project work that reflects my learning and design style</h2>
        <p class="section-subtitle">
          Here’s a featured project that highlights my approach to responsive design, dynamic UI behavior, and practical JavaScript-based interaction.
        </p>
      </div>

      <article class="project-card glass reveal">
        <div class="project-top">
          <div>
            <h3>Vehicle Tracker</h3>
            <p>
              A responsive web application that allows users to track vehicle details using dynamic UI and JavaScript-based interactions.
            </p>
          </div>
          <div class="project-tag">Live Project</div>
        </div>

        <div class="tech-pills" style="margin-bottom: 22px;">
          <span class="pill">HTML</span>
          <span class="pill">CSS</span>
          <span class="pill">JavaScript</span>
        </div>

        <div class="btn-group">
          <a class="btn btn-primary" href="https://ash-krsna.github.io/codex-" target="_blank" rel="noopener">Open Live Link</a>
          <a class="btn btn-secondary" href="https://github.com/ash-krsna" target="_blank" rel="noopener">View GitHub</a>
        </div>
      </article>
    </div>
  </section>

  <section class="section" id="skills">
    <div class="container">
      <div class="reveal">
        <div class="badge">
          <span class="badge-dot"></span>
          Skills
        </div>
        <h2 class="section-title">A growing stack across frontend, backend, databases, and security</h2>
        <p class="section-subtitle">
          My learning path is focused on modern frontend development while expanding into backend tools, databases, and cyber security fundamentals.
        </p>
      </div>

      <div class="skill-columns">
        <div class="skill-card glass reveal">
          <h3>Frontend</h3>
          <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>Bootstrap</li>
            <li>JavaScript</li>
            <li>React</li>
          </ul>
        </div>

        <div class="skill-card glass reveal">
          <h3>Backend & Database</h3>
          <ul>
            <li>Node.js</li>
            <li>MongoDB</li>
            <li>MySQL</li>
          </ul>
        </div>

        <div class="skill-card glass reveal">
          <h3>Cyber Security</h3>
          <ul>
            <li>Linux</li>
            <li>Networking Basics</li>
            <li>Web Security Fundamentals</li>
          </ul>
        </div>
      </div>

      <div class="icons-panel glass reveal">
        <h3 style="margin-top: 0;">Tools & Icons</h3>
        <img
          src="https://skillicons.dev/icons?i=html,css,bootstrap,js,react,nodejs,mongodb,mysql,linux,github,vscode&theme=dark"
          alt="Skill Icons"
          style="margin: 18px auto 0;"
        />
      </div>
    </div>
  </section>

  <section class="section" id="github">
    <div class="container">
      <div class="reveal">
        <div class="badge">
          <span class="badge-dot"></span>
          GitHub
        </div>
        <h2 class="section-title">My coding journey, activity, and language breakdown</h2>
        <p class="section-subtitle">
          Explore my GitHub profile and development stats to see my learning progress, project activity, and the technologies I work with most.
        </p>
      </div>

      <div class="github-grid">
        <div class="github-card glass reveal">
          <h3 style="margin-top: 0;">GitHub Profile</h3>
          <p>
            GitHub is where I document my learning, build projects, and continue sharpening my frontend and development skills.
          </p>
          <div class="btn-group">
            <a class="btn btn-primary" href="https://github.com/ash-krsna" target="_blank" rel="noopener">Visit GitHub</a>
          </div>

          <div class="stats-grid">
            <img
              src="https://github-readme-stats.vercel.app/api?username=ash-krsna&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=38BDF8&icon_color=22D3EE&text_color=C9D1D9"
              alt="GitHub Stats"
            />
            <img
              src="https://github-readme-stats.vercel.app/api/top-langs/?username=ash-krsna&layout=compact&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=38BDF8&text_color=C9D1D9"
              alt="Top Languages"
            />
          </div>

          <div class="stats-single" style="margin-top: 18px;">
            <img
              src="https://streak-stats.demolab.com?user=ash-krsna&theme=tokyonight&hide_border=true&background=0D1117&ring=38BDF8&fire=22D3EE&currStreakLabel=38BDF8"
              alt="GitHub Streak"
            />
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="contact">
    <div class="container">
      <div class="contact-card glass reveal">
        <div class="badge" style="justify-content:center;">
          <span class="badge-dot"></span>
          Contact
        </div>
        <h2 class="section-title">Let’s connect</h2>
        <p>
          If you’d like to follow my work, explore my projects, or connect through GitHub, feel free to reach out through my profile.
        </p>
        <div class="btn-group" style="justify-content:center;">
          <a class="btn btn-primary" href="https://github.com/ash-krsna" target="_blank" rel="noopener">GitHub Profile</a>
          <a class="btn btn-secondary" href="#home">Back to Top</a>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      Built with a modern dark UI, smooth interactions, and a portfolio-first design for Akash.
    </div>
  </footer>

  <script>
    const typingTarget = document.getElementById("typing");
    const typingTexts = [
      "Frontend Developer",
      "React Learner",
      "Cyber Security Enthusiast"
    ];

    let textIndex = 0;
    let charIndex = 0;
    let deleting = false;

    function typeLoop() {
      const currentText = typingTexts[textIndex];

      if (!deleting) {
        typingTarget.textContent = currentText.slice(0, charIndex + 1);
        charIndex++;

        if (charIndex === currentText.length) {
          deleting = true;
          setTimeout(typeLoop, 1400);
          return;
        }
      } else {
        typingTarget.textContent = currentText.slice(0, charIndex - 1);
        charIndex--;

        if (charIndex === 0) {
          deleting = false;
          textIndex = (textIndex + 1) % typingTexts.length;
        }
      }

      setTimeout(typeLoop, deleting ? 50 : 90);
    }

    typeLoop();

    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            entry.target.classList.add("visible");
          }
        });
      },
      { threshold: 0.16 }
    );

    document.querySelectorAll(".reveal").forEach((el) => observer.observe(el));
  </script>
</body>
</html>
