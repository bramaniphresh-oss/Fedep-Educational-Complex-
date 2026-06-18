# Fedep-Educational-Complex-
A school's website 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Fedep Educational Complex – Kakumdo, Cape Coast</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Inter:wght@400;500;600&family=Oswald:wght@500;600&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --wine:    #6B1A2A;
    --wine-dk: #4A0F1C;
    --wine-lt: #8C2438;
    --gold:    #F5C400;
    --gold-lt: #FFD740;
    --gold-dk: #C9A000;
    --cream:   #FDF8EE;
    --ink:     #1A0A0F;
    --muted:   #7A5060;
    --white:   #FFFFFF;
    --radius:  6px;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--cream);
    color: var(--ink);
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    background: var(--wine-dk);
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 5vw;
    height: 64px;
    box-shadow: 0 2px 20px rgba(0,0,0,.35);
  }
  .nav-brand {
    display: flex; align-items: center; gap: 12px;
    text-decoration: none;
  }
  .nav-logo {
    width: 40px; height: 40px;
    background: var(--gold);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-family: 'Playfair Display', serif;
    font-weight: 900;
    color: var(--wine-dk);
    font-size: 16px;
    flex-shrink: 0;
    letter-spacing: -1px;
  }
  .nav-name {
    font-family: 'Oswald', sans-serif;
    font-size: 15px;
    color: var(--gold-lt);
    letter-spacing: .5px;
    line-height: 1.2;
  }
  .nav-name span { display: block; font-size: 10px; color: rgba(255,215,64,.6); font-family: 'Inter', sans-serif; letter-spacing: 1.5px; text-transform: uppercase; font-weight: 500; }
  .nav-links { display: flex; gap: 28px; list-style: none; }
  .nav-links a { color: rgba(255,255,255,.8); text-decoration: none; font-size: 13px; font-weight: 500; letter-spacing: .5px; text-transform: uppercase; transition: color .2s; }
  .nav-links a:hover { color: var(--gold-lt); }

  /* ── HERO ── */
  .hero {
    margin-top: 64px;
    min-height: calc(100vh - 64px);
    background: var(--wine-dk);
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: repeating-linear-gradient(
      45deg,
      transparent,
      transparent 60px,
      rgba(245,196,0,.03) 60px,
      rgba(245,196,0,.03) 61px
    );
    pointer-events: none;
  }
  .hero-left {
    display: flex; flex-direction: column; justify-content: center;
    padding: 80px 5vw 80px 8vw;
    position: relative; z-index: 1;
  }
  .hero-eyebrow {
    font-family: 'Oswald', sans-serif;
    font-size: 12px; letter-spacing: 3px; text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 20px;
    display: flex; align-items: center; gap: 12px;
  }
  .hero-eyebrow::before {
    content: '';
    display: block; width: 32px; height: 2px; background: var(--gold);
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(36px, 5vw, 68px);
    font-weight: 900;
    line-height: 1.05;
    color: var(--white);
    margin-bottom: 12px;
  }
  .hero h1 em {
    font-style: normal;
    color: var(--gold);
    display: block;
  }
  .hero-sub {
    font-size: 16px; color: rgba(255,255,255,.65);
    max-width: 420px;
    margin-bottom: 44px;
    line-height: 1.7;
  }
  .hero-cta {
    display: flex; gap: 16px; flex-wrap: wrap;
  }
  .btn-primary {
    background: var(--gold);
    color: var(--wine-dk);
    padding: 14px 32px;
    font-weight: 700;
    font-size: 14px;
    border: none; border-radius: var(--radius);
    cursor: pointer;
    text-decoration: none;
    letter-spacing: .5px;
    transition: background .2s, transform .15s;
    display: inline-block;
  }
  .btn-primary:hover { background: var(--gold-lt); transform: translateY(-1px); }
  .btn-outline {
    background: transparent;
    color: var(--white);
    padding: 13px 32px;
    font-weight: 600;
    font-size: 14px;
    border: 2px solid rgba(255,255,255,.3);
    border-radius: var(--radius);
    cursor: pointer;
    text-decoration: none;
    letter-spacing: .5px;
    transition: border-color .2s, color .2s;
    display: inline-block;
  }
  .btn-outline:hover { border-color: var(--gold); color: var(--gold); }

  .hero-right {
    position: relative;
    overflow: hidden;
  }
  .hero-right img {
    width: 100%; height: 100%;
    object-fit: cover;
    display: block;
    opacity: .85;
  }
  .hero-right::after {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(to right, var(--wine-dk) 0%, transparent 40%);
  }

  /* ── STAT BAR ── */
  .stat-bar {
    background: var(--gold);
    display: flex;
    justify-content: center;
  }
  .stat-bar-inner {
    display: flex;
    width: 100%;
    max-width: 1100px;
  }
  .stat-item {
    flex: 1;
    padding: 28px 20px;
    text-align: center;
    border-right: 1px solid rgba(107,26,42,.15);
  }
  .stat-item:last-child { border-right: none; }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 36px; font-weight: 900;
    color: var(--wine-dk);
    display: block;
  }
  .stat-label {
    font-size: 12px; font-weight: 600;
    color: var(--wine);
    text-transform: uppercase; letter-spacing: 1px;
  }

  /* ── SECTIONS ── */
  section { padding: 96px 8vw; }
  .section-eyebrow {
    font-family: 'Oswald', sans-serif;
    font-size: 11px; letter-spacing: 3px; text-transform: uppercase;
    color: var(--wine);
    margin-bottom: 12px;
  }
  h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(28px, 3.5vw, 48px);
    font-weight: 900;
    line-height: 1.1;
    color: var(--wine-dk);
    margin-bottom: 20px;
  }
  h2 .accent { color: var(--gold-dk); }
  .lead { font-size: 17px; color: var(--muted); max-width: 600px; line-height: 1.8; margin-bottom: 48px; }

  /* ── ABOUT ── */
  .about { background: var(--cream); }
  .about-grid {
    display: grid;
    grid-template-columns: 1.2fr 1fr;
    gap: 80px;
    align-items: center;
  }
  .about-img-wrap {
    position: relative;
  }
  .about-img-wrap img {
    width: 100%; border-radius: 8px;
    box-shadow: 16px 16px 0 var(--gold);
    display: block;
  }
  .about-badge {
    position: absolute;
    bottom: -20px; right: -20px;
    background: var(--wine);
    color: var(--white);
    padding: 20px 24px;
    border-radius: 6px;
    font-family: 'Oswald', sans-serif;
    font-size: 13px;
    letter-spacing: .5px;
    line-height: 1.4;
    box-shadow: 0 4px 20px rgba(0,0,0,.25);
  }
  .about-badge strong { display: block; font-size: 22px; color: var(--gold); }
  .feature-list { list-style: none; display: flex; flex-direction: column; gap: 16px; }
  .feature-list li {
    display: flex; align-items: flex-start; gap: 14px;
    font-size: 15px; color: var(--ink);
  }
  .feat-icon {
    width: 36px; height: 36px; flex-shrink: 0;
    background: var(--gold);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 16px;
    margin-top: 1px;
  }
  .feat-text strong { display: block; font-size: 15px; margin-bottom: 2px; }
  .feat-text span { color: var(--muted); font-size: 13px; }

  /* ── LEVELS ── */
  .levels { background: var(--wine-dk); }
  .levels h2 { color: var(--white); }
  .levels h2 .accent { color: var(--gold); }
  .levels .lead { color: rgba(255,255,255,.6); }
  .levels-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 24px;
  }
  .level-card {
    background: rgba(255,255,255,.05);
    border: 1px solid rgba(245,196,0,.2);
    border-radius: 10px;
    padding: 36px 28px;
    position: relative;
    overflow: hidden;
    transition: background .2s, transform .2s;
  }
  .level-card:hover { background: rgba(245,196,0,.08); transform: translateY(-4px); }
  .level-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 4px;
    background: var(--gold);
  }
  .level-emoji { font-size: 36px; margin-bottom: 16px; display: block; }
  .level-card h3 {
    font-family: 'Oswald', sans-serif;
    font-size: 20px; color: var(--white);
    margin-bottom: 8px;
  }
  .level-card p { font-size: 14px; color: rgba(255,255,255,.55); line-height: 1.6; }
  .level-tag {
    display: inline-block;
    margin-top: 16px;
    background: var(--gold);
    color: var(--wine-dk);
    font-size: 11px; font-weight: 700;
    padding: 4px 10px;
    border-radius: 20px;
    letter-spacing: .5px;
  }

  /* ── GALLERY ── */
  .gallery { background: var(--cream); }
  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 280px 280px;
    gap: 16px;
  }
  .gallery-item { border-radius: 8px; overflow: hidden; position: relative; }
  .gallery-item img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform .4s; }
  .gallery-item:hover img { transform: scale(1.04); }
  .gallery-item:nth-child(1) { grid-column: 1; grid-row: 1; }
  .gallery-item:nth-child(2) { grid-column: 2 / 4; grid-row: 1; }
  .gallery-item:nth-child(3) { grid-column: 1 / 3; grid-row: 2; }
  .gallery-item:nth-child(4) { grid-column: 3; grid-row: 2; }
  .gallery-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(to top, rgba(107,26,42,.7) 0%, transparent 50%);
    opacity: 0; transition: opacity .3s;
    display: flex; align-items: flex-end; padding: 20px;
  }
  .gallery-item:hover .gallery-overlay { opacity: 1; }
  .gallery-caption { color: var(--white); font-size: 13px; font-weight: 600; }

  /* ── FEDEP ── */
  .fedep { background: var(--gold); }
  .fedep-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }
  .fedep h2 { color: var(--wine-dk); }
  .fedep .lead { color: var(--wine); }
  .fedep-pillars { display: flex; flex-direction: column; gap: 20px; }
  .fedep-pillar {
    background: rgba(107,26,42,.08);
    border-left: 4px solid var(--wine);
    padding: 16px 20px;
    border-radius: 0 6px 6px 0;
  }
  .fedep-pillar h4 { font-family: 'Oswald', sans-serif; font-size: 16px; color: var(--wine-dk); margin-bottom: 4px; }
  .fedep-pillar p { font-size: 13px; color: var(--wine); line-height: 1.5; }
  .fedep-img img { width: 100%; border-radius: 8px; display: block; }

  /* ── CONTACT ── */
  .contact { background: var(--wine-dk); }
  .contact h2 { color: var(--white); }
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
  }
  .contact-info { display: flex; flex-direction: column; gap: 28px; }
  .contact-item { display: flex; gap: 16px; align-items: flex-start; }
  .contact-icon {
    width: 44px; height: 44px; flex-shrink: 0;
    background: rgba(245,196,0,.15);
    border: 1px solid rgba(245,196,0,.3);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
  }
  .contact-item h4 { font-size: 12px; text-transform: uppercase; letter-spacing: 1px; color: var(--gold); margin-bottom: 4px; font-weight: 600; }
  .contact-item p { font-size: 15px; color: rgba(255,255,255,.8); line-height: 1.5; }
  .contact-form { display: flex; flex-direction: column; gap: 16px; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .form-group { display: flex; flex-direction: column; gap: 6px; }
  .form-group label { font-size: 12px; font-weight: 600; color: rgba(255,255,255,.6); letter-spacing: .5px; text-transform: uppercase; }
  .form-group input,
  .form-group textarea,
  .form-group select {
    background: rgba(255,255,255,.07);
    border: 1px solid rgba(255,255,255,.15);
    border-radius: var(--radius);
    padding: 12px 16px;
    color: var(--white);
    font-size: 14px;
    font-family: 'Inter', sans-serif;
    transition: border-color .2s;
    outline: none;
  }
  .form-group input:focus,
  .form-group textarea:focus,
  .form-group select:focus { border-color: var(--gold); }
  .form-group textarea { resize: vertical; min-height: 110px; }
  .form-group select option { background: var(--wine-dk); }

  /* ── FOOTER ── */
  footer {
    background: var(--ink);
    padding: 40px 8vw;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 20px;
  }
  .footer-left { color: rgba(255,255,255,.5); font-size: 13px; }
  .footer-left strong { color: var(--gold); }
  .footer-links { display: flex; gap: 24px; }
  .footer-links a { color: rgba(255,255,255,.4); font-size: 13px; text-decoration: none; transition: color .2s; }
  .footer-links a:hover { color: var(--gold); }
  .footer-badge {
    background: var(--wine);
    color: var(--gold-lt);
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: .5px;
  }

  /* ── MOBILE ── */
  @media (max-width: 768px) {
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-right { height: 280px; }
    .hero-left { padding: 60px 6vw; }
    .stat-bar-inner { flex-wrap: wrap; }
    .stat-item { min-width: 50%; }
    section { padding: 64px 6vw; }
    .about-grid, .fedep-inner, .contact-grid { grid-template-columns: 1fr; gap: 40px; }
    .about-badge { position: static; margin-top: 20px; display: inline-block; }
    .gallery-grid { grid-template-columns: 1fr 1fr; grid-template-rows: auto; }
    .gallery-item { grid-column: auto !important; grid-row: auto !important; height: 200px; }
    .form-row { grid-template-columns: 1fr; }
    footer { flex-direction: column; text-align: center; }
    .footer-links { flex-wrap: wrap; justify-content: center; }
  }

  /* ── ANIMATIONS ── */
  @media (prefers-reduced-motion: no-preference) {
    .level-card, .gallery-item { transition: transform .25s, background .25s; }
    .btn-primary, .btn-outline { transition: all .2s; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-brand">
    <div class="nav-logo">FEC</div>
    <div class="nav-name">
      Fedep Educational Complex
      <span>Kakumdo · Cape Coast</span>
    </div>
  </a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#levels">Programmes</a></li>
    <li><a href="#gallery">Gallery</a></li>
    <li><a href="#fedep">F.E.D.E.P</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-left">
    <div class="hero-eyebrow">Kakumdo · Cape Coast · Ghana</div>
    <h1>
      Where Every Child
      <em>Rises.</em>
    </h1>
    <p class="hero-sub">
      A community-rooted school giving children from Nursery through JHS a 
      quality GES education — built on belonging, ambition, and care.
    </p>
    <div class="hero-cta">
      <a href="#contact" class="btn-primary">Enrol Your Child</a>
      <a href="#about" class="btn-outline">Learn More</a>
    </div>
  </div>
  <div class="hero-right">
    <img src="/mnt/user-data/uploads/797404.jpg" alt="Students celebrating at Fedep Educational Complex" />
  </div>
</section>

<!-- STAT BAR -->
<div class="stat-bar">
  <div class="stat-bar-inner">
    <div class="stat-item">
      <span class="stat-num">3</span>
      <span class="stat-label">School Divisions</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">GES</span>
      <span class="stat-label">Accredited Curriculum</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">KG–JHS</span>
      <span class="stat-label">Full Progression</span>
    </div>
    <div class="stat-item">
      <span class="stat-num">F.E.D.E.P</span>
      <span class="stat-label">Community Partner</span>
    </div>
  </div>
</div>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-grid">
    <div class="about-img-wrap">
      <img src="/mnt/user-data/uploads/797395.jpg" alt="Students at a formal event" />
      <div class="about-badge">
        <strong>Cape Coast</strong>
        Kakumdo, Ghana
      </div>
    </div>
    <div>
      <div class="section-eyebrow">Who We Are</div>
      <h2>A school that <span class="accent">belongs</span> to its community</h2>
      <p class="lead" style="margin-bottom: 32px;">
        Fedep Educational Complex is a private, community-based institution in Kakumdo, 
        a suburb of Cape Coast. We operate fully under the Ghana Education Service 
        curriculum, ensuring every pupil is prepared for national examinations and a 
        bright future.
      </p>
      <ul class="feature-list">
        <li>
          <div class="feat-icon">📍</div>
          <div class="feat-text">
            <strong>Community Rooted</strong>
            <span>Serving families in Kakumdo and surrounding suburbs of Cape Coast.</span>
          </div>
        </li>
        <li>
          <div class="feat-icon">📚</div>
          <div class="feat-text">
            <strong>GES Curriculum</strong>
            <span>Fully aligned with the Ghana Education Service standards at every level.</span>
          </div>
        </li>
        <li>
          <div class="feat-icon">🏆</div>
          <div class="feat-text">
            <strong>Nationally Recognised</strong>
            <span>Our students have represented Cape Coast at national competitions and events.</span>
          </div>
        </li>
        <li>
          <div class="feat-icon">🚌</div>
          <div class="feat-text">
            <strong>School Bus Service</strong>
            <span>Safe, reliable transport keeping pupils connected to school every day.</span>
          </div>
        </li>
      </ul>
    </div>
  </div>
</section>

<!-- LEVELS -->
<section class="levels" id="levels">
  <div class="section-eyebrow" style="color: rgba(245,196,0,.7);">Academic Programmes</div>
  <h2 style="margin-bottom: 12px;">From <span class="accent">first steps</span> to graduation</h2>
  <p class="lead">We guide every child through a seamless educational journey — from their earliest years in the classroom through to Junior High School completion.</p>
  <div class="levels-grid">
    <div class="level-card">
      <span class="level-emoji">🌱</span>
      <h3>Nursery / Crèche</h3>
      <p>A warm, safe environment for our youngest learners to develop language, motor skills, and a love of discovery.</p>
      <span class="level-tag">Ages 2–3</span>
    </div>
    <div class="level-card">
      <span class="level-emoji">🌼</span>
      <h3>Kindergarten</h3>
      <p>Play-based learning that builds numeracy, literacy, and social foundations through structured daily routines.</p>
      <span class="level-tag">Ages 4–5</span>
    </div>
    <div class="level-card">
      <span class="level-emoji">📖</span>
      <h3>Lower Primary</h3>
      <p>Core GES subjects introduced with hands-on activities, building reading, writing, and arithmetic confidence.</p>
      <span class="level-tag">Basic 1–3</span>
    </div>
    <div class="level-card">
      <span class="level-emoji">🔬</span>
      <h3>Upper Primary</h3>
      <p>Deeper subject engagement covering English, Mathematics, Science, RME, History, Creative Arts and ICT.</p>
      <span class="level-tag">Basic 4–6</span>
    </div>
    <div class="level-card">
      <span class="level-emoji">🎓</span>
      <h3>Junior High School</h3>
      <p>Full BECE preparation across all core subjects, with extracurricular activities and leadership development.</p>
      <span class="level-tag">JHS 1–3</span>
    </div>
  </div>
</section>

<!-- GALLERY -->
<section class="gallery" id="gallery">
  <div class="section-eyebrow">School Life</div>
  <h2>Our <span class="accent">students</span> in action</h2>
  <p class="lead">Every day at Fedep is filled with learning, laughter, and the joy of growing together.</p>
  <div class="gallery-grid">
    <div class="gallery-item">
      <img src="/mnt/user-data/uploads/797404.jpg" alt="Students cheering in class" />
      <div class="gallery-overlay"><span class="gallery-caption">Classroom celebration</span></div>
    </div>
    <div class="gallery-item">
      <img src="/mnt/user-data/uploads/797393.jpg" alt="Students in formal group photo" />
      <div class="gallery-overlay"><span class="gallery-caption">Group photo at school event</span></div>
    </div>
    <div class="gallery-item">
      <img src="/mnt/user-data/uploads/797391.jpg" alt="Students in the hall" />
      <div class="gallery-overlay"><span class="gallery-caption">Academic programme</span></div>
    </div>
    <div class="gallery-item">
      <img src="/mnt/user-data/uploads/797394.jpg" alt="School bus Kakumdo Cape Coast" />
      <div class="gallery-overlay"><span class="gallery-caption">Our school bus – Kakumdo</span></div>
    </div>
  </div>
</section>

<!-- FEDEP NGO -->
<section class="fedep" id="fedep">
  <div class="fedep-inner">
    <div>
      <div class="section-eyebrow" style="color: var(--wine);">Our Parent Organisation</div>
      <h2>The <span style="color:var(--wine-dk)">F.E.D.E.P</span> Mission</h2>
      <p class="lead" style="color: var(--wine); margin-bottom: 36px;">
        The Foundation for Economic Development and Educational Promotion is the 
        local NGO behind Fedep Educational Complex. Its mission: make quality 
        education accessible and drive community development in Kakumdo and beyond.
      </p>
      <div class="fedep-pillars">
        <div class="fedep-pillar">
          <h4>Educational Access</h4>
          <p>Removing barriers so every child in the community can attend and stay in school.</p>
        </div>
        <div class="fedep-pillar">
          <h4>Economic Development</h4>
          <p>Building capacity in Kakumdo through education, skills, and community partnerships.</p>
        </div>
        <div class="fedep-pillar">
          <h4>Community Partnership</h4>
          <p>Collaborating with parents, local leaders, and organisations for lasting impact.</p>
        </div>
      </div>
    </div>
    <div class="fedep-img">
      <img src="/mnt/user-data/uploads/797395.jpg" alt="Award ceremony — student recognised nationally" />
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <h2 style="color:var(--white); margin-bottom: 48px;">Get in <span style="color:var(--gold)">touch</span></h2>
  <div class="contact-grid">
    <div class="contact-info">
      <div class="contact-item">
        <div class="contact-icon">📍</div>
        <div>
          <h4>Address</h4>
          <p>Kakumdo, Cape Coast<br/>Central Region, Ghana<br/>P.O. Box AD 729</p>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📞</div>
        <div>
          <h4>Phone</h4>
          <p>0246 ··· ···· (see school bus for full number)</p>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">🎓</div>
        <div>
          <h4>Admissions</h4>
          <p>Nursery / KG through JHS 3<br/>Enrolment open — contact us to arrange a visit.</p>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">🚌</div>
        <div>
          <h4>School Bus</h4>
          <p>Transport service available for pupils.<br/>Ask about routes when you enquire.</p>
        </div>
      </div>
    </div>
    <div>
      <p style="color: rgba(255,255,255,.5); font-size: 14px; margin-bottom: 24px;">Fill in the form and we'll respond within one school day.</p>
      <div class="contact-form">
        <div class="form-row">
          <div class="form-group">
            <label>Parent / Guardian Name</label>
            <input type="text" placeholder="Kwame Mensah" />
          </div>
          <div class="form-group">
            <label>Phone Number</label>
            <input type="tel" placeholder="024 000 0000" />
          </div>
        </div>
        <div class="form-group">
          <label>Email Address</label>
          <input type="email" placeholder="you@example.com" />
        </div>
        <div class="form-group">
          <label>Child's Level of Interest</label>
          <select>
            <option value="">Select a level…</option>
            <option>Nursery / Crèche</option>
            <option>Kindergarten</option>
            <option>Lower Primary (Basic 1–3)</option>
            <option>Upper Primary (Basic 4–6)</option>
            <option>Junior High School (JHS 1–3)</option>
            <option>Other Enquiry</option>
          </select>
        </div>
        <div class="form-group">
          <label>Message</label>
          <textarea placeholder="Tell us a little about your child or your question…"></textarea>
        </div>
        <button class="btn-primary" style="align-self: flex-start; font-size: 15px; padding: 16px 36px;">Send Enquiry</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-left">
    <strong>Fedep Educational Complex</strong><br/>
    © 2025 · P.O. Box AD 729, Kakumdo · Cape Coast, Ghana
  </div>
  <nav class="footer-links">
    <a href="#about">About</a>
    <a href="#levels">Programmes</a>
    <a href="#gallery">Gallery</a>
    <a href="#fedep">F.E.D.E.P</a>
    <a href="#contact">Contact</a>
  </nav>
  <div class="footer-badge">GES Accredited</div>
</footer>

</body>
</html>
