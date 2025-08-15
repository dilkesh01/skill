<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Dilkesh | Full Stack Developer</title>
  <meta name="description" content="Professional portfolio showcasing development skills in web and software technologies">
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #0b1020;
      --glass: rgba(255,255,255,0.08);
      --border: rgba(255,255,255,0.18);
      --text: #eaf1ff;
      --muted: #b5c2ff;
      --accent: #7c8cff;
      --chip: rgba(124,140,255,0.14);
      --shadow: 0 10px 30px rgba(2, 12, 46, 0.35);
    }
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    html, body {
      height: 100%;
    }
    body {
      font-family: Poppins, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      color: var(--text);
      background:
        radial-gradient(1200px 800px at 10% -10%, #3b2aff33 8%, transparent 60%),
        radial-gradient(1000px 800px at 110% 10%, #00e5ff22 8%, transparent 60%),
        linear-gradient(180deg, #0a0f1f, #0a0c16);
      overflow-x: hidden;
      line-height: 1.6;
    }
    a {
      color: inherit;
      text-decoration: none;
    }
    .container {
      width: min(1100px, 92vw);
      margin: 0 auto;
      padding: 32px 0 80px;
    }

    /* Header Styles */
    header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
      margin-top: 10px;
    }
    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 10px 14px;
      border: 1px solid var(--border);
      border-radius: 14px;
      background: var(--glass);
      backdrop-filter: blur(10px);
      box-shadow: var(--shadow);
    }
    .brand .logo {
      width: 36px;
      height: 36px;
      display: grid;
      place-items: center;
      border-radius: 10px;
      background: linear-gradient(135deg, #7c8cff44, #00e5ff33);
    }
    .brand h1 {
      font-size: 1.05rem;
      margin: 0;
      letter-spacing: 0.3px;
    }
    .controls {
      display: flex;
      gap: 10px;
    }
    .btn {
      padding: 10px 14px;
      border-radius: 12px;
      border: 1px solid var(--border);
      background: var(--glass);
      color: var(--text);
      transition: transform 0.2s ease, box-shadow 0.2s ease, background 0.2s ease;
      box-shadow: var(--shadow);
      cursor: pointer;
      font-weight: 500;
    }
    .btn:hover {
      transform: translateY(-2px);
    }
    .btn.primary {
      background: linear-gradient(135deg, #7c8cff55, #00e5ff44);
    }

    /* Hero Section */
    .hero {
      margin: 36px 0 28px;
      display: grid;
      gap: 14px;
    }
    .hero h2 {
      font-size: clamp(1.8rem, 2.5vw + 1rem, 2.6rem);
      line-height: 1.15;
      margin: 0;
      letter-spacing: 0.3px;
    }
    .hero p {
      color: var(--muted);
      margin: 4px 0 0;
      max-width: 70ch;
    }

    /* Skills Section */
    section {
      margin-top: 32px;
    }
    .section-head {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 14px;
    }
    .section-head h3 {
      margin: 0;
      font-size: 1.25rem;
      letter-spacing: 0.4px;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 16px;
    }
    .card {
      position: relative;
      background: var(--glass);
      border: 1px solid var(--border);
      border-radius: 18px;
      padding: 18px 16px;
      backdrop-filter: blur(10px);
      box-shadow: var(--shadow);
      transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s ease;
      overflow: hidden;
    }
    .card:hover {
      transform: translateY(-6px);
      box-shadow: 0 14px 36px rgba(0, 0, 0, 0.45);
      border-color: #8ea0ff66;
    }
    .card::after {
      content: "";
      position: absolute;
      inset: -1px;
      background: radial-gradient(120px 80px at 20% -10%, #7c8cff22, transparent 60%);
      border-radius: 18px;
      pointer-events: none;
    }
    .top {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 10px;
    }
    .image-top {
      width: 44px;
      height: 44px;
      flex: 0 0 44px;
      border-radius: 12px;
      padding: 8px;
      background: linear-gradient(135deg, #10162a, #202b4e);
      border: 1px solid #2c3a72;
      display: grid;
      place-items: center;
    }
    .title {
      font-weight: 700;
      letter-spacing: 0.3px;
    }
    .desc {
      color: var(--muted);
      font-size: 0.95rem;
      line-height: 1.45;
    }

    .chips {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 12px;
    }
    .chip {
      padding: 6px 10px;
      border-radius: 999px;
      font-size: 0.8rem;
      background: var(--chip);
      border: 1px solid #7c8cff44;
    }

    /* Footer */
    footer {
      margin-top: 36px;
      display: flex;
      justify-content: center;
      color: #a6b0ff;
      font-size: 0.9rem;
      opacity: 0.8;
    }

    /* Animations */
    .reveal {
      opacity: 0;
      transform: translateY(10px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }
    .reveal.show {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
</head>
<body>
  <div class="container">
    <header class="reveal">
      <div class="brand">
        <div class="logo">🚀</div>
        <h1>Dilkesh — Full Stack Developer</h1>
      </div>
      <div class="controls">
        <button class="btn primary" onclick="document.querySelector('#contact').scrollIntoView({behavior:'smooth'})">Contact</button>
        <a class="btn" href="dilkesh-resume.pdf" target="_blank" rel="noopener">Download CV</a>
      </div>
    </header>

    <section class="hero reveal">
      <h2>Building fast, reliable software — from backend systems to modern web applications.</h2>
      <p>I'm a full stack developer focused on clean code, efficient algorithms, and delightful user experiences. Below are my core skills.</p>
    </section>

    <section id="skills">
      <div class="section-head reveal">
        <h3>Technical Skills</h3>
      </div>
      <div class="grid">
        <!-- Web Development -->
        <article class="card reveal">
          <div class="top">
            <div class="image-top" aria-hidden="true">
              <svg width="26" height="26" viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Web">
                <circle cx="24" cy="24" r="18" fill="#00bcd4" opacity=".85"/>
                <path d="M6 24h36M24 6v36" stroke="#fff" stroke-width="2"/>
                <path d="M12 12c6 6 18 6 24 0M12 36c6-6 18-6 24 0" stroke="#fff" stroke-width="2" fill="none"/>
              </svg>
            </div>
            <div>
              <div class="title">Web Development</div>
              <div class="desc">Modern responsive web applications with React, Node.js and modern frameworks.</div>
            </div>
          </div>
          <div class="chips">
            <span class="chip">React</span>
            <span class="chip">Node.js</span>
            <span class="chip">TypeScript</span>
          </div>
        </article>

        <!-- Frontend -->
        <article class="card reveal">
          <div class="top">
            <div class="image-top" aria-hidden="true">
              <svg width="26" height="26" viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Frontend">
                <rect x="6" y="6" width="36" height="36" rx="4" fill="#42a5f5" opacity=".85"/>
                <path d="M18 18h12v12H18z" fill="#fff" opacity=".8"/>
                <path d="M18 18l12 12M30 18l-12 12" stroke="#fff" stroke-width="2"/>
              </svg>
            </div>
            <div>
              <div class="title">Frontend</div>
              <div class="desc">Beautiful, accessible UIs with modern CSS and JavaScript frameworks.</div>
            </div>
          </div>
          <div class="chips">
            <span class="chip">HTML/CSS</span>
            <span class="chip">JavaScript</span>
            <span class="chip">Tailwind</span>
          </div>
        </article>

        <!-- Backend -->
        <article class="card reveal">
          <div class="top">
            <div class="image-top" aria-hidden="true">
              <svg width="26" height="26" viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Backend">
                <path d="M24 44a20 20 0 100-40 20 20 0 000 40z" fill="#5c6bc0" opacity=".85"/>
                <path d="M24 14a10 10 0 0110 10 10 10 0 01-10 10 10 10 0 01-10-10 10 10 0 0110-10z" fill="#fff" opacity=".8"/>
                <path d="M24 18a6 6 0 016 6 6 6 0 01-6 6 6 6 0 01-6-6 6 6 0 016-6z" fill="#5c6bc0"/>
              </svg>
            </div>
            <div>
              <div class="title">Backend</div>
              <div class="desc">Scalable server-side applications with robust APIs and services.</div>
            </div>
          </div>
          <div class="chips">
            <span class="chip">Node.js</span>
            <span class="chip">Express</span>
            <span class="chip">REST APIs</span>
          </div>
        </article>

        <!-- Database -->
        <article class="card reveal">
          <div class="top">
            <div class="image-top" aria-hidden="true">
              <svg width="26" height="26" viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Database">
                <ellipse cx="24" cy="12" rx="12" ry="6" fill="#4CAF50" opacity=".85"/>
                <path d="M36 12v12c0 3.3-5.4 6-12 6s-12-2.7-12-6V12" fill="#4CAF50" opacity=".6"/>
                <path d="M36 24v12c0 3.3-5.4 6-12 6s-12-2.7-12-6V24" fill="#4CAF50" opacity=".4"/>
              </svg>
            </div>
            <div>
              <div class="title">Database</div>
              <div class="desc">SQL and NoSQL database design, optimization, and scaling.</div>
            </div>
          </div>
          <div class="chips">
            <span class="chip">MongoDB</span>
            <span class="chip">PostgreSQL</span>
            <span class="chip">Redis</span>
          </div>
        </article>
      </div>
    </section>

    <section id="contact" class="reveal" style="margin-top:28px">
      <div class="section-head">
        <h3>Get in touch</h3>
      </div>
      <div class="card" style="display:flex; gap:12px; align-items:center;">
        <div class="image-top" aria-hidden="true">✉️</div>
        <div>
          <div class="title">Let's collaborate</div>
          <div class="desc">Have a project or opportunity? I'd love to hear about it.</div>
        </div>
        <div style="margin-left:auto; display:flex; gap:10px">
          <a class="btn" href="mailto:dilkesh@example.com">Email</a>
          <a class="btn primary" href="https://github.com/dilkesh-dev" target="_blank" rel="noopener">GitHub</a>
        </div>
      </div>
    </section>

    <footer>© <span id="year"></span> Dilkesh. All rights reserved.</footer>
  </div>

  <script>
    // Current year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Reveal on scroll
    const els = document.querySelectorAll('.reveal');
    const io = new IntersectionObserver(entries => {
      entries.forEach(e => {
        if(e.isIntersecting) { 
          e.target.classList.add('show'); 
          io.unobserve(e.target); 
        }
      });
    }, {threshold: 0.12});
    els.forEach(el => io.observe(el));

    // 3D tilt effect for cards
    const cards = document.querySelectorAll('.card');
    cards.forEach(card => {
      card.addEventListener('mousemove', (e) => {
        const r = card.getBoundingClientRect();
        const x = (e.clientX - r.left) / r.width - 0.5;
        const y = (e.clientY - r.top) / r.height - 0.5;
        card.style.transform = `perspective(700px) rotateX(${-y * 6}deg) rotateY(${x * 6}deg) translateY(-4px)`;
      });
      card.addEventListener('mouseleave', () => {
        card.style.transform = '';
      });
    });
  </script>
</body>
</html>
