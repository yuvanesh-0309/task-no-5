<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#f5f4ef">
  <title>Brand. — Build better. Work smarter.</title>

  <style>
    @import url('https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Space+Grotesk:wght@400;500;600;700&display=swap');

    :root {
      --ink: #121210;
      --paper: #f5f4ef;
      --white: #fffefa;
      --purple: #9472ff;
      --yellow: #e8f83d;
      --muted: #66645d;
      --line: #d8d6cf;
      --font: 'Space Grotesk', Arial, sans-serif;
      --mono: 'DM Mono', monospace;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      background: var(--paper);
      color: var(--ink);
      font-family: var(--font);
    }
    a { color: inherit; text-decoration: none; }
    .wrap { width: min(1120px, calc(100% - 44px)); margin: auto; }

    .header {
      position: sticky;
      top: 0;
      z-index: 10;
      background: rgba(245, 244, 239, .94);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--ink);
    }
    .nav {
      height: 70px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
    }
    .brand {
      display: flex;
      align-items: center;
      gap: 9px;
      font-weight: 700;
      letter-spacing: -.04em;
    }
    .brand-icon {
      width: 30px;
      height: 30px;
      background: var(--purple);
      border: 1.5px solid var(--ink);
      box-shadow: 3px 3px var(--ink);
      display: grid;
      place-items: center;
    }
    .nav-links {
      display: flex;
      align-items: center;
      gap: 28px;
      font-size: 12px;
      font-weight: 700;
    }
    .nav-links a:not(.nav-button):hover { color: #7150dc; }
    .nav-button, .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 12px 15px;
      background: var(--purple);
      border: 1.5px solid var(--ink);
      box-shadow: 3px 3px var(--ink);
      font-size: 11px;
      font-weight: 700;
      text-transform: uppercase;
      transition: .18s;
    }
    .nav-button:hover, .button:hover {
      transform: translate(2px, 2px);
      box-shadow: 1px 1px var(--ink);
    }
    .menu {
      display: none;
      border: 1px solid var(--ink);
      background: transparent;
      padding: 8px;
      font: 10px var(--mono);
    }

    .hero {
      padding: 65px 0 55px;
      border-bottom: 1px solid var(--line);
      overflow: hidden;
    }
    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 1.04fr;
      gap: 40px;
      align-items: center;
    }
    .eyebrow {
      display: inline-block;
      padding: 7px 10px;
      background: var(--yellow);
      border: 1px solid var(--ink);
      box-shadow: 3px 3px var(--ink);
      font: 10px var(--mono);
      text-transform: uppercase;
    }
    .hero h1 {
      font-size: clamp(48px, 6.5vw, 76px);
      line-height: .93;
      letter-spacing: -.075em;
      margin: 22px 0 17px;
    }
    .hero h1 mark { background: var(--purple); color: var(--ink); }
    .hero p {
      max-width: 430px;
      color: #55534e;
      line-height: 1.65;
      font-size: 15px;
      margin: 0 0 24px;
    }
    .hero-actions {
      display: flex;
      align-items: center;
      gap: 19px;
      flex-wrap: wrap;
    }
    .demo-link {
      font-size: 12px;
      font-weight: 700;
      display: inline-flex;
      gap: 8px;
      align-items: center;
    }
    .play {
      border: 1px solid var(--ink);
      width: 22px;
      height: 22px;
      border-radius: 50%;
      display: grid;
      place-items: center;
      font-size: 9px;
    }

    .dashboard {
      position: relative;
      background: var(--purple);
      border: 1.5px solid var(--ink);
      box-shadow: 7px 7px var(--ink);
      padding: 15px;
    }
    .spark {
      position: absolute;
      right: -13px;
      top: -14px;
      background: var(--yellow);
      border: 1px solid var(--ink);
      width: 38px;
      height: 38px;
      display: grid;
      place-items: center;
    }
    .dash-window {
      background: var(--white);
      border: 1px solid var(--ink);
      height: 300px;
      display: grid;
      grid-template-columns: 82px 1fr;
      overflow: hidden;
    }
    .dash-side { background: var(--ink); padding: 13px 9px; }
    .dash-logo {
      width: 20px;
      height: 20px;
      border-radius: 50%;
      background: var(--yellow);
      margin-bottom: 23px;
    }
    .side-line {
      height: 5px;
      background: #65645f;
      margin: 13px 3px;
    }
    .side-line.active { background: var(--yellow); width: 80%; }
    .dash-main { padding: 17px; }
    .dash-title { font-size: 12px; font-weight: 700; }
    .dash-sub { font: 8px var(--mono); color: var(--muted); margin-top: 3px; }
    .chart {
      height: 112px;
      margin: 15px 0 10px;
      background: #f4f2ed;
      border: 1px solid var(--line);
    }
    .chart svg { width: 100%; height: 100%; }
    .dash-bottom {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 7px;
    }
    .dash-stat {
      height: 82px;
      border: 1px solid var(--ink);
      padding: 8px;
      background: var(--yellow);
    }
    .dash-stat:nth-child(2) { background: #f0eee8; }
    .dash-stat:nth-child(3) { background: var(--purple); }
    .dash-stat b { font-size: 19px; display: block; }
    .dash-stat small { font: 7px var(--mono); }

    .section {
      padding: 58px 0;
      border-bottom: 1px solid var(--line);
    }
    .section-head {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 25px;
      margin-bottom: 25px;
    }
    .kicker {
      font: 10px var(--mono);
      letter-spacing: .1em;
      text-transform: uppercase;
      color: var(--muted);
    }
    h2 {
      font-size: clamp(30px, 4vw, 46px);
      letter-spacing: -.065em;
      line-height: 1;
      margin: 8px 0 0;
    }
    .section-head p {
      max-width: 390px;
      margin: 0;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.6;
    }

    .features {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 12px;
    }
    .feature {
      border: 1px solid var(--ink);
      background: var(--white);
      padding: 17px;
      min-height: 170px;
      transition: .2s;
    }
    .feature:hover {
      transform: translateY(-4px);
      box-shadow: 4px 4px var(--ink);
    }
    .icon {
      width: 38px;
      height: 38px;
      display: grid;
      place-items: center;
      background: var(--yellow);
      border: 1px solid var(--ink);
      font-size: 18px;
    }
    .feature:nth-child(even) .icon { background: var(--purple); }
    .feature h3 { font-size: 14px; margin: 17px 0 5px; }
    .feature p {
      font-size: 11px;
      line-height: 1.55;
      color: var(--muted);
      margin: 0;
    }

    .plans {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 13px;
    }
    .plan {
      position: relative;
      background: var(--white);
      border: 1px solid var(--ink);
      padding: 20px;
    }
    .plan.popular {
      background: #f1edff;
      box-shadow: 4px 4px var(--ink);
    }
    .plan-tag {
      position: absolute;
      right: 11px;
      top: 11px;
      background: var(--yellow);
      padding: 4px 6px;
      font: 8px var(--mono);
      text-transform: uppercase;
    }
    .plan h3 { font-size: 15px; margin: 0 0 5px; }
    .plan p { font-size: 11px; color: var(--muted); margin: 0; }
    .price {
      font-size: 29px;
      font-weight: 700;
      letter-spacing: -.06em;
      margin: 16px 0;
    }
    .price small {
      font-size: 10px;
      font-weight: 400;
      color: var(--muted);
      letter-spacing: 0;
    }
    .plan .button {
      width: 100%;
      background: var(--white);
      font-size: 10px;
    }
    .popular .button { background: var(--purple); }
    .plan ul {
      list-style: none;
      padding: 12px 0 0;
      margin: 12px 0 0;
      border-top: 1px solid var(--line);
      font-size: 10px;
      line-height: 2;
    }
    .plan li::before {
      content: '✓';
      font-weight: bold;
      margin-right: 7px;
    }

    .cta-section { padding: 55px 0; }
    .cta-box {
      background: var(--yellow);
      border: 1.5px solid var(--ink);
      box-shadow: 6px 6px var(--ink);
      padding: 29px 32px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 22px;
    }
    .cta-box h2 { font-size: clamp(27px, 4vw, 40px); margin: 0; }
    .cta-box p { font-size: 12px; color: #4e4d43; margin: 7px 0 0; }
    .cta-box .button { background: var(--white); }
    .footer {
      border-top: 1px solid var(--line);
      padding: 19px 0;
      color: var(--muted);
      font: 10px var(--mono);
    }
    .footer .wrap {
      display: flex;
      justify-content: space-between;
      gap: 12px;
      flex-wrap: wrap;
    }

    .modal {
      display: none;
      position: fixed;
      inset: 0;
      background: #111a;
      z-index: 20;
      place-items: center;
      padding: 20px;
    }
    .modal.open { display: grid; }
    .modal-card {
      width: min(500px, 100%);
      background: var(--white);
      border: 1.5px solid var(--ink);
      box-shadow: 6px 6px var(--ink);
      padding: 24px;
      position: relative;
    }
    .modal-card h2 { font-size: 28px; }
    .modal-card p { font-size: 13px; color: var(--muted); }
    .close {
      position: absolute;
      right: 14px;
      top: 14px;
      background: none;
      border: 1px solid var(--ink);
      font-size: 18px;
      cursor: pointer;
    }
    .modal-demo {
      height: 180px;
      background: var(--purple);
      border: 1px solid var(--ink);
      display: grid;
      place-items: center;
      font-size: 38px;
    }

    @media (max-width: 850px) {
      .hero-grid { grid-template-columns: 1fr; gap: 35px; }
      .dashboard { max-width: 580px; width: 100%; margin: auto; }
      .features { grid-template-columns: repeat(2, 1fr); }
    }
    @media (max-width: 620px) {
      .wrap { width: calc(100% - 30px); }
      .nav { height: 62px; }
      .menu { display: block; }
      .nav-links {
        display: none;
        position: absolute;
        top: 62px;
        left: 0;
        right: 0;
        padding: 18px 20px 22px;
        background: var(--paper);
        border-bottom: 1px solid var(--ink);
        align-items: flex-start;
        flex-direction: column;
        gap: 17px;
      }
      .nav-links.open { display: flex; }
      .hero { padding: 43px 0; }
      .hero h1 { font-size: clamp(49px, 14vw, 68px); }
      .dashboard { padding: 9px; }
      .dash-window { height: 240px; grid-template-columns: 62px 1fr; }
      .dash-main { padding: 12px; }
      .chart { height: 82px; }
      .dash-stat { height: 66px; padding: 6px; }
      .dash-stat b { font-size: 16px; }
      .section { padding: 42px 0; }
      .section-head {
        align-items: flex-start;
        flex-direction: column;
        gap: 11px;
      }
      .features { gap: 8px; }
      .feature { padding: 13px; min-height: 160px; }
      .plans { grid-template-columns: 1fr; }
      .cta-box {
        align-items: flex-start;
        flex-direction: column;
        padding: 24px;
      }
      .footer .wrap { font-size: 9px; }
    }
    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after { transition: none !important; }
    }
  </style>
</head>
<body>
  <header class="header">
    <nav class="nav wrap" aria-label="Main navigation">
      <a class="brand" href="#home"><span class="brand-icon">B</span> BRAND.</a>
      <button class="menu" aria-expanded="false" aria-controls="nav-links">MENU</button>
      <div class="nav-links" id="nav-links">
        <a href="#home">Home</a>
        <a href="#features">Features</a>
        <a href="#pricing">Pricing</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
        <a class="nav-button" href="#pricing">Get started ↗</a>
      </div>
    </nav>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="wrap hero-grid">
        <div>
          <span class="eyebrow">A better way to work</span>
          <h1>Build better.<br>Work smarter.<br><mark>Grow</mark> faster.</h1>
          <p>One simple platform to help your team streamline workflows, collaborate in real time, and achieve more together.</p>
          <div class="hero-actions">
            <a class="button" href="#pricing">Get started →</a>
            <a class="demo-link" href="#demo" id="open-demo">Watch demo <b class="play">▶</b></a>
          </div>
        </div>

        <div class="dashboard" aria-label="Illustration of a team analytics dashboard">
          <span class="spark">✳</span>
          <div class="dash-window">
            <aside class="dash-side">
              <div class="dash-logo"></div>
              <div class="side-line active"></div>
              <div class="side-line"></div>
              <div class="side-line"></div>
              <div class="side-line"></div>
              <div class="side-line"></div>
            </aside>
            <div class="dash-main">
              <div class="dash-title">Team overview</div>
              <div class="dash-sub">Your work is moving forward</div>
              <div class="chart">
                <svg viewBox="0 0 400 110" preserveAspectRatio="none" aria-hidden="true">
                  <path d="M0 91 L55 72 L100 82 L152 45 L205 62 L258 31 L310 43 L365 13 L400 20"
                    fill="none" stroke="#141414" stroke-width="3"/>
                  <path d="M0 91 L55 72 L100 82 L152 45 L205 62 L258 31 L310 43 L365 13 L400 20 L400 110 L0 110Z"
                    fill="#9472ff" opacity=".24"/>
                  <g fill="#e8f83d" stroke="#141414" stroke-width="2">
                    <circle cx="55" cy="72" r="5"/>
                    <circle cx="152" cy="45" r="5"/>
                    <circle cx="258" cy="31" r="5"/>
                    <circle cx="365" cy="13" r="5"/>
                  </g>
                </svg>
              </div>
              <div class="dash-bottom">
                <div class="dash-stat"><b>72%</b><small>PRODUCTIVITY</small></div>
                <div class="dash-stat"><b>18</b><small>PROJECTS</small></div>
                <div class="dash-stat"><b>+24%</b><small>THIS MONTH</small></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="features">
      <div class="wrap">
        <div class="section-head">
          <div><div class="kicker">Everything in sync</div><h2>Tools that move work forward.</h2></div>
          <p>Bring your team and daily work together in one clear space, built to help you focus on progress.</p>
        </div>
        <div class="features">
          <article class="feature"><div class="icon">ϟ</div><h3>Fast & powerful</h3><p>Get through everyday work with less busywork and more focus.</p></article>
          <article class="feature"><div class="icon">♧</div><h3>Team collaboration</h3><p>Share updates, coordinate projects, and keep everyone aligned.</p></article>
          <article class="feature"><div class="icon">♢</div><h3>Secure & reliable</h3><p>Keep important team information protected and organized.</p></article>
          <article class="feature"><div class="icon">▥</div><h3>Useful insights</h3><p>See progress at a glance and make informed decisions.</p></article>
        </div>
      </div>
    </section>

    <section class="section" id="pricing">
      <div class="wrap">
        <div class="section-head">
          <div><div class="kicker">Simple, clear pricing</div><h2>A plan for your next stage.</h2></div>
          <p>Start with what you need. Upgrade as your team grows.</p>
        </div>
        <div class="plans">
          <article class="plan">
            <h3>Basic</h3><p>For individuals getting started.</p>
            <div class="price">$0 <small>/ month</small></div>
            <a class="button" href="#contact">Get started</a>
            <ul><li>Up to 3 projects</li><li>Core task tools</li><li>Community support</li></ul>
          </article>
          <article class="plan popular">
            <span class="plan-tag">Most popular</span>
            <h3>Pro</h3><p>For teams building momentum.</p>
            <div class="price">$19 <small>/ user / month</small></div>
            <a class="button" href="#contact">Start free trial</a>
            <ul><li>Unlimited projects</li><li>Team collaboration</li><li>Progress insights</li></ul>
          </article>
          <article class="plan">
            <h3>Business</h3><p>For organizations scaling up.</p>
            <div class="price">$49 <small>/ user / month</small></div>
            <a class="button" href="#contact">Talk to sales</a>
            <ul><li>Everything in Pro</li><li>Advanced permissions</li><li>Priority support</li></ul>
          </article>
        </div>
      </div>
    </section>

    <section class="cta-section" id="about">
      <div class="wrap">
        <div class="cta-box">
          <div>
            <h2>Ready to get started?</h2>
            <p>Join teams making room for better work. Start with a free plan today.</p>
          </div>
          <a class="button" href="#contact">Get started now →</a>
        </div>
      </div>
    </section>
  </main>

  <footer class="footer" id="contact">
    <div class="wrap">
      <span><strong>BRAND.</strong> © 2026 · All rights reserved.</span>
      <span>Product　Features　Pricing　Company　About　Contact</span>
      <a href="mailto:hello@example.com">hello@example.com</a>
    </div>
  </footer>

  <div class="modal" id="demo" role="dialog" aria-modal="true" aria-labelledby="demo-title">
    <div class="modal-card">
      <button class="close" aria-label="Close demo">×</button>
      <div class="modal-demo">▶</div>
      <h2 id="demo-title">Product demo</h2>
      <p>This demo area is ready for a video embed. Replace it with your product video URL when available.</p>
    </div>
  </div>

  <script>
    const menu = document.querySelector('.menu');
    const links = document.querySelector('.nav-links');

    menu.addEventListener('click', () => {
      const open = links.classList.toggle('open');
      menu.setAttribute('aria-expanded', open);
    });

    links.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        links.classList.remove('open');
        menu.setAttribute('aria-expanded', 'false');
      });
    });

    const modal = document.querySelector('.modal');

    document.querySelector('#open-demo').addEventListener('click', event => {
      event.preventDefault();
      modal.classList.add('open');
    });

    document.querySelector('.close').addEventListener('click', () => {
      modal.classList.remove('open');
    });

    modal.addEventListener('click', event => {
      if (event.target === modal) modal.classList.remove('open');
    });

    document.addEventListener('keydown', event => {
      if (event.key === 'Escape') modal.classList.remove('open');
    });
  </script>
</body>
</html>
