<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NAPA Community Based Organisation</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>

/* ── CSS Variables ── */
:root {
  --green-deep:   #0f4c2a;
  --green-mid:    #15803d;
  --green-light:  #22c55e;
  --gold:         #d4a84b;
  --gold-light:   #f5d68a;
  --cream:        #faf7f2;
  --text-dark:    #1a1a1a;
  --text-mid:     #4a4a4a;
  --text-light:   #7a7a7a;
  --white:        #ffffff;
  --radius-sm:    8px;
  --radius-md:    16px;
  --radius-lg:    24px;
  --shadow-sm:    0 2px 12px rgba(0,0,0,0.07);
  --shadow-md:    0 8px 32px rgba(0,0,0,0.12);
  --shadow-lg:    0 20px 60px rgba(0,0,0,0.16);
  --transition:   0.35s cubic-bezier(0.22,0.61,0.36,1);
}

/* ── Reset ── */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--cream);
  color: var(--text-dark);
  line-height: 1.65;
  overflow-x: hidden;
}

/* ── Scrollbar ── */
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: var(--cream); }
::-webkit-scrollbar-thumb { background: var(--green-mid); border-radius: 3px; }

/* ── Navbar ── */
nav {
  position: sticky;
  top: 0;
  z-index: 100;
  background: var(--green-deep);
  padding: 0 5%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 68px;
  box-shadow: 0 2px 20px rgba(0,0,0,0.25);
}

.nav-brand {
  font-family: 'Playfair Display', serif;
  color: var(--gold);
  font-size: 1.1rem;
  font-weight: 700;
  letter-spacing: 0.5px;
  text-decoration: none;
  white-space: nowrap;
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
}

.nav-links a {
  color: rgba(255,255,255,0.8);
  text-decoration: none;
  font-size: 0.875rem;
  font-weight: 500;
  letter-spacing: 0.3px;
  transition: color var(--transition);
  position: relative;
  padding-bottom: 4px;
}

.nav-links a::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0;
  width: 0; height: 2px;
  background: var(--gold);
  transition: width var(--transition);
}

.nav-links a:hover { color: var(--gold); }
.nav-links a:hover::after { width: 100%; }

/* ── Hero ── */
.hero {
  position: relative;
  min-height: 92vh;
  background: linear-gradient(135deg, var(--green-deep) 0%, #1a6b3a 50%, #0d3d20 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  overflow: hidden;
  padding: 80px 5%;
}

/* decorative circles */
.hero::before {
  content: '';
  position: absolute;
  width: 600px; height: 600px;
  border-radius: 50%;
  border: 1px solid rgba(212,168,75,0.15);
  top: -100px; right: -100px;
  animation: spin 40s linear infinite;
}
.hero::after {
  content: '';
  position: absolute;
  width: 400px; height: 400px;
  border-radius: 50%;
  border: 1px solid rgba(212,168,75,0.1);
  bottom: -80px; left: -80px;
  animation: spin 30s linear infinite reverse;
}
@keyframes spin { to { transform: rotate(360deg); } }

.hero-badge {
  display: inline-block;
  background: rgba(212,168,75,0.18);
  border: 1px solid rgba(212,168,75,0.4);
  color: var(--gold-light);
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding: 6px 18px;
  border-radius: 100px;
  margin-bottom: 24px;
  animation: fadeUp 0.8s ease both;
}

.hero-inner { position: relative; z-index: 2; max-width: 760px; }

.hero h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.4rem, 6vw, 4.5rem);
  font-weight: 900;
  color: var(--white);
  line-height: 1.15;
  margin-bottom: 24px;
  animation: fadeUp 0.9s 0.1s ease both;
}

.hero h1 span { color: var(--gold); }

.hero p {
  font-size: 1.1rem;
  color: rgba(255,255,255,0.75);
  max-width: 540px;
  margin: 0 auto 36px;
  animation: fadeUp 0.9s 0.2s ease both;
}

.hero-actions {
  display: flex;
  gap: 14px;
  justify-content: center;
  flex-wrap: wrap;
  animation: fadeUp 0.9s 0.3s ease both;
}

.btn-primary {
  display: inline-block;
  padding: 14px 32px;
  background: var(--gold);
  color: var(--green-deep);
  font-weight: 700;
  font-size: 0.925rem;
  border-radius: var(--radius-sm);
  text-decoration: none;
  letter-spacing: 0.3px;
  transition: transform var(--transition), box-shadow var(--transition), background var(--transition);
  box-shadow: 0 4px 20px rgba(212,168,75,0.35);
}
.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 30px rgba(212,168,75,0.5);
  background: var(--gold-light);
}

.btn-outline {
  display: inline-block;
  padding: 14px 32px;
  border: 2px solid rgba(255,255,255,0.4);
  color: var(--white);
  font-weight: 600;
  font-size: 0.925rem;
  border-radius: var(--radius-sm);
  text-decoration: none;
  transition: border-color var(--transition), background var(--transition);
}
.btn-outline:hover {
  border-color: var(--gold);
  background: rgba(212,168,75,0.1);
}

/* ── Section wrapper ── */
.section {
  padding: 90px 5%;
}
.section-inner {
  max-width: 1100px;
  margin: 0 auto;
}

.section-label {
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--green-mid);
  margin-bottom: 10px;
}

.section-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.8rem, 3.5vw, 2.8rem);
  font-weight: 700;
  color: var(--text-dark);
  line-height: 1.2;
  margin-bottom: 16px;
}

.section-subtitle {
  font-size: 1rem;
  color: var(--text-mid);
  max-width: 560px;
  line-height: 1.7;
}

/* ── Stats bar ── */
.stats-bar {
  background: var(--green-deep);
  padding: 50px 5%;
}
.stats-grid {
  max-width: 1100px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2px;
}
.stat-item {
  text-align: center;
  padding: 30px 20px;
  position: relative;
}
.stat-item + .stat-item::before {
  content: '';
  position: absolute;
  left: 0; top: 20%; bottom: 20%;
  width: 1px;
  background: rgba(255,255,255,0.12);
}
.stat-num {
  font-family: 'Playfair Display', serif;
  font-size: 3rem;
  font-weight: 900;
  color: var(--gold);
  line-height: 1;
  margin-bottom: 6px;
}
.stat-label {
  font-size: 0.85rem;
  color: rgba(255,255,255,0.65);
  font-weight: 500;
  letter-spacing: 0.3px;
}

/* ── About ── */
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}
@media(max-width:768px){ .about-grid { grid-template-columns: 1fr; gap: 40px; } }

.about-visual {
  position: relative;
}
.about-img-frame {
  width: 100%;
  aspect-ratio: 4/3;
  background: linear-gradient(135deg, #22c55e22, #15803d33);
  border-radius: var(--radius-lg);
  border: 2px solid rgba(21,128,61,0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
.about-icon {
  font-size: 5rem;
  opacity: 0.25;
}
.about-badge {
  position: absolute;
  bottom: -20px; right: -20px;
  background: var(--gold);
  color: var(--green-deep);
  padding: 16px 20px;
  border-radius: var(--radius-md);
  font-family: 'Playfair Display', serif;
  font-weight: 700;
  font-size: 1.6rem;
  line-height: 1;
  box-shadow: var(--shadow-md);
}
.about-badge small { display: block; font-family: 'DM Sans', sans-serif; font-size: 0.7rem; font-weight: 500; margin-top: 3px; }

.about-content .section-subtitle { max-width: 100%; margin-bottom: 28px; }

.about-pillars {
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.pillar {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 0.925rem;
  font-weight: 500;
  color: var(--text-mid);
}
.pillar-dot {
  width: 10px; height: 10px;
  border-radius: 50%;
  background: var(--green-mid);
  flex-shrink: 0;
}

/* ── Programs ── */
.programs-section { background: var(--white); }

.programs-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
  margin-top: 48px;
}

.program-card {
  border: 1px solid #e8e8e8;
  border-radius: var(--radius-md);
  padding: 36px 28px;
  transition: transform var(--transition), box-shadow var(--transition), border-color var(--transition);
  position: relative;
  overflow: hidden;
}
.program-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--green-mid), var(--green-light));
  opacity: 0;
  transition: opacity var(--transition);
}
.program-card:hover {
  transform: translateY(-6px);
  box-shadow: var(--shadow-lg);
  border-color: transparent;
}
.program-card:hover::before { opacity: 1; }

.program-icon {
  width: 52px; height: 52px;
  background: rgba(21,128,61,0.08);
  border-radius: var(--radius-sm);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.6rem;
  margin-bottom: 20px;
}
.program-card h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 10px;
  color: var(--text-dark);
}
.program-card p {
  font-size: 0.9rem;
  color: var(--text-light);
  line-height: 1.7;
}

/* ── Gallery ── */
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 220px 220px;
  gap: 12px;
  margin-top: 48px;
}
@media(max-width:640px){ .gallery-grid { grid-template-columns: 1fr; grid-template-rows: auto; } }

.gallery-item {
  border-radius: var(--radius-md);
  overflow: hidden;
  position: relative;
  background: linear-gradient(135deg, #d4edda, #a7f3c5);
}
.gallery-item:first-child {
  grid-row: span 2;
}
.gallery-item img {
  width: 100%; height: 100%;
  object-fit: cover;
  transition: transform 0.6s ease;
  display: block;
}
.gallery-item:hover img { transform: scale(1.06); }

.gallery-placeholder {
  width: 100%; height: 100%;
  min-height: 180px;
  background: linear-gradient(135deg, rgba(21,128,61,0.1), rgba(21,128,61,0.2));
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 8px;
  color: var(--green-mid);
  font-size: 2rem;
}
.gallery-placeholder span {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  opacity: 0.6;
}

/* ── Testimonial ── */
.testimonial-section {
  background: linear-gradient(135deg, var(--green-deep), #1f5c38);
  padding: 90px 5%;
  text-align: center;
}
.testimonial-inner {
  max-width: 680px;
  margin: 0 auto;
}
.quote-mark {
  font-family: 'Playfair Display', serif;
  font-size: 5rem;
  color: var(--gold);
  line-height: 0.5;
  margin-bottom: 28px;
  display: block;
}
.testimonial-text {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.3rem, 2.5vw, 1.8rem);
  color: var(--white);
  line-height: 1.55;
  font-style: italic;
  margin-bottom: 28px;
}
.testimonial-author {
  color: var(--gold-light);
  font-size: 0.875rem;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
}

/* ── Contact ── */
.contact-section { background: var(--cream); }
.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1.3fr;
  gap: 60px;
  margin-top: 48px;
  align-items: start;
}
@media(max-width:768px){ .contact-grid { grid-template-columns: 1fr; gap: 40px; } }

.contact-info { display: flex; flex-direction: column; gap: 24px; }
.contact-detail {
  display: flex;
  gap: 16px;
  align-items: flex-start;
}
.contact-icon {
  width: 44px; height: 44px;
  background: var(--green-deep);
  border-radius: var(--radius-sm);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
  flex-shrink: 0;
  color: var(--white);
}
.contact-detail-text h4 {
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: var(--green-mid);
  margin-bottom: 3px;
}
.contact-detail-text p {
  font-size: 0.925rem;
  color: var(--text-mid);
  line-height: 1.5;
}

/* Map */
.map-container {
  border-radius: var(--radius-md);
  overflow: hidden;
  margin-top: 28px;
  box-shadow: var(--shadow-sm);
  border: 1px solid rgba(0,0,0,0.08);
}

/* Contact Form */
.contact-form-card {
  background: var(--white);
  border-radius: var(--radius-lg);
  padding: 40px;
  box-shadow: var(--shadow-md);
}
.contact-form-card h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  margin-bottom: 24px;
  color: var(--text-dark);
}

.form-group { margin-bottom: 18px; }
.form-group label {
  display: block;
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  color: var(--text-mid);
  margin-bottom: 6px;
}

.form-control {
  width: 100%;
  padding: 12px 16px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.95rem;
  color: var(--text-dark);
  background: var(--cream);
  border: 1.5px solid #e0ddd8;
  border-radius: var(--radius-sm);
  transition: border-color var(--transition), box-shadow var(--transition);
  outline: none;
}
.form-control:focus {
  border-color: var(--green-mid);
  box-shadow: 0 0 0 3px rgba(21,128,61,0.1);
}
textarea.form-control { resize: vertical; min-height: 120px; }

.btn-submit {
  width: 100%;
  padding: 14px;
  background: var(--green-deep);
  color: var(--white);
  font-family: 'DM Sans', sans-serif;
  font-size: 0.95rem;
  font-weight: 600;
  border: none;
  border-radius: var(--radius-sm);
  cursor: pointer;
  transition: background var(--transition), transform var(--transition);
  letter-spacing: 0.3px;
}
.btn-submit:hover {
  background: var(--green-mid);
  transform: translateY(-2px);
}

.success-msg {
  display: none;
  background: rgba(34,197,94,0.1);
  border: 1px solid rgba(34,197,94,0.3);
  color: #15803d;
  padding: 12px 16px;
  border-radius: var(--radius-sm);
  font-size: 0.9rem;
  font-weight: 500;
  margin-top: 12px;
  text-align: center;
}

/* ── Footer ── */
footer {
  background: var(--green-deep);
  padding: 48px 5% 24px;
}
.footer-inner {
  max-width: 1100px;
  margin: 0 auto;
}
.footer-top {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 40px;
  flex-wrap: wrap;
  padding-bottom: 36px;
  border-bottom: 1px solid rgba(255,255,255,0.1);
  margin-bottom: 24px;
}
.footer-brand {
  font-family: 'Playfair Display', serif;
  color: var(--gold);
  font-size: 1.3rem;
  font-weight: 700;
  margin-bottom: 10px;
}
.footer-tagline {
  color: rgba(255,255,255,0.5);
  font-size: 0.85rem;
}
.footer-links {
  display: flex;
  gap: 24px;
  list-style: none;
}
.footer-links a {
  color: rgba(255,255,255,0.55);
  text-decoration: none;
  font-size: 0.875rem;
  transition: color var(--transition);
}
.footer-links a:hover { color: var(--gold); }

.footer-copy {
  color: rgba(255,255,255,0.35);
  font-size: 0.8rem;
  text-align: center;
}

/* ── Animations ── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
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

/* ── WhatsApp Float Button ── */
.wa-float {
  position: fixed;
  bottom: 28px;
  right: 28px;
  z-index: 999;
  display: flex;
  align-items: center;
  gap: 10px;
  text-decoration: none;
}

.wa-bubble {
  background: #25D366;
  width: 58px; height: 58px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  box-shadow: 0 6px 24px rgba(37,211,102,0.45);
  transition: transform var(--transition), box-shadow var(--transition);
  position: relative;
}
.wa-bubble:hover {
  transform: scale(1.1);
  box-shadow: 0 10px 32px rgba(37,211,102,0.55);
}

/* Pulse ring */
.wa-bubble::before {
  content: '';
  position: absolute;
  width: 100%; height: 100%;
  border-radius: 50%;
  background: rgba(37,211,102,0.4);
  animation: waPulse 2s ease-out infinite;
}
@keyframes waPulse {
  0%   { transform: scale(1);   opacity: 0.7; }
  100% { transform: scale(1.9); opacity: 0; }
}

.wa-bubble svg {
  width: 30px; height: 30px;
  fill: white;
  position: relative; z-index: 1;
}

.wa-label {
  background: var(--white);
  color: var(--text-dark);
  font-size: 0.8rem;
  font-weight: 600;
  padding: 8px 14px;
  border-radius: 100px;
  box-shadow: var(--shadow-md);
  white-space: nowrap;
  opacity: 0;
  transform: translateX(10px);
  transition: opacity var(--transition), transform var(--transition);
  pointer-events: none;
}
.wa-float:hover .wa-label {
  opacity: 1;
  transform: translateX(0);
}

/* ── Mobile nav toggle ── */
.nav-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  flex-direction: column;
  gap: 5px;
}
.nav-toggle span {
  display: block;
  width: 22px; height: 2px;
  background: var(--white);
  border-radius: 2px;
  transition: transform var(--transition), opacity var(--transition);
}
@media(max-width:640px){
  .nav-toggle { display: flex; }
  .nav-links {
    position: absolute;
    top: 68px; left: 0; right: 0;
    background: var(--green-deep);
    flex-direction: column;
    gap: 0;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.4s ease;
  }
  .nav-links.open { max-height: 300px; }
  .nav-links li a {
    display: block;
    padding: 14px 5%;
    border-top: 1px solid rgba(255,255,255,0.07);
  }
}

</style>
</head>
<body>

<!-- ══ NAVBAR ══ -->
<nav>
  <a href="#" class="nav-brand">NAPA CBO</a>
  <button class="nav-toggle" id="navToggle" aria-label="Toggle menu">
    <span></span><span></span><span></span>
  </button>
  <ul class="nav-links" id="navLinks">
    <li><a href="#">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#programs">Programs</a></li>
    <li><a href="#gallery">Gallery</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- ══ HERO ══ -->
<section class="hero">
  <div class="hero-inner">
    <div class="hero-badge">Magunga, Kenya</div>
    <h1>NAPA <span>Community</span><br>Based Organisation</h1>
    <p>Empowering communities through education, sustainability, and meaningful change — one family at a time.</p>
    <div class="hero-actions">
      <a href="#donate" class="btn-primary">Support Our Mission</a>
      <a href="#about" class="btn-outline">Learn More</a>
    </div>
  </div>
</section>

<!-- ══ STATS BAR ══ -->
<div class="stats-bar">
  <div class="stats-grid">
    <div class="stat-item">
      <div class="stat-num">500+</div>
      <div class="stat-label">Youth Empowered</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">200+</div>
      <div class="stat-label">Families Supported</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">10+</div>
      <div class="stat-label">Projects Completed</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">5+</div>
      <div class="stat-label">Years of Service</div>
    </div>
  </div>
</div>

<!-- ══ ABOUT ══ -->
<section class="section" id="about">
  <div class="section-inner">
    <div class="about-grid">
      <div class="about-visual reveal">
        <div class="about-img-frame">
          <div class="about-icon">🌿</div>
        </div>
        <div class="about-badge">
          Est. 2019
          <small>Magunga, Kenya</small>
        </div>
      </div>
      <div class="about-content reveal">
        <div class="section-label">Who We Are</div>
        <h2 class="section-title">Rooted in Community,<br>Growing Together</h2>
        <p class="section-subtitle">NAPA Community Based Organisation is committed to fostering positive change within local communities. We believe every person deserves access to opportunity, care, and a healthy environment to thrive.</p>
        <div class="about-pillars">
          <div class="pillar"><div class="pillar-dot"></div>Youth empowerment &amp; leadership development</div>
          <div class="pillar"><div class="pillar-dot"></div>Quality education support for underserved families</div>
          <div class="pillar"><div class="pillar-dot"></div>Environmental conservation &amp; sustainable practices</div>
          <div class="pillar"><div class="pillar-dot"></div>Health awareness &amp; community wellness programs</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ══ PROGRAMS ══ -->
<section class="section programs-section" id="programs">
  <div class="section-inner">
    <div class="reveal">
      <div class="section-label">What We Do</div>
      <h2 class="section-title">Our Programs</h2>
      <p class="section-subtitle">Three core pillars guide everything we do — each one designed to create lasting, generational change.</p>
    </div>
    <div class="programs-grid">
      <div class="program-card reveal">
        <div class="program-icon">🌟</div>
        <h3>Youth Empowerment</h3>
        <p>Equipping young people with leadership skills, mentorship, and resources to become confident changemakers in their communities.</p>
      </div>
      <div class="program-card reveal">
        <div class="program-icon">📚</div>
        <h3>Education Support</h3>
        <p>Providing scholarships, learning materials, and tutoring to ensure every child has access to quality education regardless of background.</p>
      </div>
      <div class="program-card reveal">
        <div class="program-icon">🌱</div>
        <h3>Environmental Conservation</h3>
        <p>Leading community tree-planting drives, waste management campaigns, and sustainable agriculture training across Magunga.</p>
      </div>
      <div class="program-card reveal">
        <div class="program-icon">❤️</div>
        <h3>Health Awareness</h3>
        <p>Running outreach clinics, health education workshops, and hygiene campaigns to improve community wellbeing.</p>
      </div>
      <div class="program-card reveal">
        <div class="program-icon">👨‍👩‍👧</div>
        <h3>Family Support</h3>
        <p>Assisting vulnerable families with food security, counselling, and access to essential social services.</p>
      </div>
      <div class="program-card reveal">
        <div class="program-icon">🤝</div>
        <h3>Community Partnerships</h3>
        <p>Building networks with local government, NGOs, and businesses to amplify our collective community impact.</p>
      </div>
    </div>
  </div>
</section>

<!-- ══ GALLERY ══ -->
<section class="section" id="gallery">
  <div class="section-inner">
    <div class="reveal">
      <div class="section-label">Our Work</div>
      <h2 class="section-title">Gallery</h2>
      <p class="section-subtitle">A glimpse into the lives we touch and the communities we serve every day.</p>
    </div>
    <div class="gallery-grid reveal">
      <div class="gallery-item">
        <div class="gallery-placeholder">🌿<span>Community</span></div>
      </div>
      <div class="gallery-item">
        <div class="gallery-placeholder">📚<span>Education</span></div>
      </div>
      <div class="gallery-item">
        <div class="gallery-placeholder">🌱<span>Environment</span></div>
      </div>
      <div class="gallery-item">
        <div class="gallery-placeholder">🌟<span>Youth</span></div>
      </div>
      <div class="gallery-item">
        <div class="gallery-placeholder">❤️<span>Health</span></div>
      </div>
    </div>
  </div>
</section>

<!-- ══ TESTIMONIAL ══ -->
<section class="testimonial-section">
  <div class="testimonial-inner reveal">
    <span class="quote-mark">"</span>
    <p class="testimonial-text">NAPA has completely transformed our community. My children now have access to education and opportunities I never dreamed possible. This organisation gives us real hope.</p>
    <div class="testimonial-author">— Community Member, Magunga</div>
  </div>
</section>

<!-- ══ CONTACT ══ -->
<section class="section contact-section" id="contact">
  <div class="section-inner">
    <div class="reveal">
      <div class="section-label">Get In Touch</div>
      <h2 class="section-title">Contact Us</h2>
      <p class="section-subtitle">Whether you want to volunteer, donate, or simply learn more — we'd love to hear from you.</p>
    </div>

    <div class="contact-grid">
      <div class="reveal">
        <div class="contact-info">
          <div class="contact-detail">
            <div class="contact-icon">📍</div>
            <div class="contact-detail-text">
              <h4>Address</h4>
              <p>Magunga, Kenya<br>P.O. Box 15 – 40307</p>
            </div>
          </div>
          <div class="contact-detail">
            <div class="contact-icon">✉️</div>
            <div class="contact-detail-text">
              <h4>Email</h4>
              <p>elizabethagawu6@gmail.com</p>
            </div>
          </div>
          <div class="contact-detail">
            <div class="contact-icon">📞</div>
            <div class="contact-detail-text">
              <h4>Phone</h4>
              <p>+254 715 706 355<br>+254 717 110 970</p>
            </div>
          </div>
        </div>
        <div class="map-container">
          <iframe
            src="https://maps.google.com/maps?q=orore+gwassi+kenya&t=&z=13&ie=UTF8&iwloc=&output=embed"
            width="100%" height="220" style="border:0; display:block;"
            loading="lazy" allowfullscreen>
          </iframe>
        </div>
      </div>

      <div class="contact-form-card reveal">
        <h3>Send Us a Message</h3>
        <form action="https://formspree.io/f/xqenaknz" method="POST" id="contactForm">
          <div class="form-group">
            <label for="name">Your Name</label>
            <input class="form-control" type="text" id="name" name="name" placeholder="e.g. Jane Wanjiku" required>
          </div>
          <div class="form-group">
            <label for="email">Email Address</label>
            <input class="form-control" type="email" id="email" name="email" placeholder="you@example.com" required>
          </div>
          <div class="form-group">
            <label for="message">Message</label>
            <textarea class="form-control" id="message" name="message" rows="5" placeholder="How can we help you?" required></textarea>
          </div>
          <button type="submit" class="btn-submit">Send Message →</button>
        </form>
        <div class="success-msg" id="successMsg">✅ Message sent successfully! We'll be in touch soon.</div>
      </div>
    </div>
  </div>
</section>

<!-- ══ FOOTER ══ -->
<footer>
  <div class="footer-inner">
    <div class="footer-top">
      <div>
        <div class="footer-brand">NAPA CBO</div>
        <div class="footer-tagline">Empowering Communities, Changing Lives</div>
      </div>
      <ul class="footer-links">
        <li><a href="#">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#programs">Programs</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
    <p class="footer-copy">© 2026 NAPA Community Based Organisation · Magunga, Kenya. All rights reserved.</p>
  </div>
</footer>

<!-- ══ WHATSAPP FLOAT ══ -->
<a class="wa-float" href="https://wa.me/254715706355" target="_blank" rel="noopener" aria-label="Chat on WhatsApp">
  <span class="wa-label">Chat with us</span>
  <div class="wa-bubble">
    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
      <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
    </svg>
  </div>
</a>

<script>
  // Mobile nav
  const toggle = document.getElementById('navToggle');
  const links  = document.getElementById('navLinks');
  toggle.addEventListener('click', () => links.classList.toggle('open'));

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));

  // Form success
  const form = document.getElementById('contactForm');
  const msg  = document.getElementById('successMsg');
  form.addEventListener('submit', () => {
    setTimeout(() => { msg.style.display = 'block'; }, 400);
  });
</script>
</body>
</html>
