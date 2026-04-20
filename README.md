<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Guau Couture: Haute Couture Canina — 24 abril 2026</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">

  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --menta:        #8FBC8F;
      --menta-dark:   #5E9A5E;
      --menta-pale:   #EEF6EE;
      --rosa:         #E8B4B8;
      --rosa-dark:    #C98A90;
      --negro:        #1A1A1A;
      --blanco:       #FAFAF8;
      --gris-suave:   #F2F2F0;
      --gris-texto:   #4A4A4A;
    }

    html { scroll-behavior: smooth; }

    body {
      background-color: var(--blanco);
      color: var(--negro);
      font-family: 'DM Sans', sans-serif;
      font-weight: 300;
      overflow-x: hidden;
    }

    /* ── BARRA SUPERIOR ── */
    .topbar {
      background: var(--negro);
      padding: 0.65rem 2rem;
      text-align: center;
      font-size: 0.62rem;
      letter-spacing: 0.32em;
      text-transform: uppercase;
      color: var(--menta);
    }

    /* ── NAV ── */
    nav {
      position: sticky;
      top: 0;
      z-index: 100;
      background: var(--blanco);
      border-bottom: 1px solid rgba(143,188,143,0.25);
      padding: 1.1rem 3rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-weight: 900;
      font-size: 1.1rem;
      letter-spacing: 0.08em;
      color: var(--negro);
      text-transform: uppercase;
    }

    .nav-logo span {
      color: var(--menta-dark);
      font-style: italic;
      font-weight: 700;
    }

    .nav-links {
      display: flex;
      gap: 2.5rem;
      list-style: none;
    }

    .nav-links a {
      font-size: 0.65rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--gris-texto);
      text-decoration: none;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--menta-dark); }

    .nav-cta {
      font-size: 0.62rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      background: var(--negro);
      color: var(--blanco);
      padding: 0.65rem 1.5rem;
      text-decoration: none;
      transition: background 0.25s, color 0.25s;
    }
    .nav-cta:hover { background: var(--menta-dark); }

    /* ── HERO ── */
    .hero {
      min-height: 96vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: stretch;
      position: relative;
      overflow: hidden;
    }

    .hero-left {
      background: var(--negro);
      padding: 6rem 5rem 6rem 6rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      position: relative;
      overflow: hidden;
    }

    .hero-left::after {
      content: '';
      position: absolute;
      width: 420px;
      height: 420px;
      border-radius: 50%;
      background: rgba(143,188,143,0.06);
      bottom: -120px;
      right: -120px;
      pointer-events: none;
    }

    .hero-eyebrow {
      font-size: 0.6rem;
      letter-spacing: 0.38em;
      text-transform: uppercase;
      color: var(--menta);
      margin-bottom: 2.5rem;
      opacity: 0;
      animation: fadeUp 0.8s ease forwards 0.3s;
    }

    .hero-title {
      font-family: 'Playfair Display', serif;
      font-weight: 900;
      font-size: clamp(3.5rem, 6vw, 6.5rem);
      line-height: 0.92;
      color: var(--blanco);
      text-transform: uppercase;
      letter-spacing: -0.01em;
      opacity: 0;
      animation: fadeUp 0.9s ease forwards 0.5s;
    }

    .hero-title .accent {
      display: block;
      color: var(--menta);
      font-style: italic;
      font-weight: 700;
      text-transform: none;
      font-size: 0.68em;
      letter-spacing: 0.01em;
      line-height: 1.1;
    }

    .hero-tagline {
      margin-top: 2.5rem;
      font-family: 'Playfair Display', serif;
      font-style: italic;
      font-size: 1.05rem;
      color: rgba(238,246,238,0.55);
      line-height: 1.6;
      max-width: 340px;
      opacity: 0;
      animation: fadeUp 0.9s ease forwards 0.75s;
    }

    .hero-date-strip {
      margin-top: 3.5rem;
      display: flex;
      align-items: center;
      gap: 1.5rem;
      opacity: 0;
      animation: fadeUp 0.8s ease forwards 0.95s;
    }

    .hero-date-strip .date-num {
      font-family: 'Playfair Display', serif;
      font-weight: 900;
      font-size: 3.8rem;
      color: var(--menta);
      line-height: 1;
    }

    .hero-date-strip .date-detail {
      display: flex;
      flex-direction: column;
      gap: 0.2rem;
    }

    .hero-date-strip .date-month {
      font-size: 0.62rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--blanco);
    }

    .hero-date-strip .date-place {
      font-size: 0.62rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: rgba(143,188,143,0.55);
    }

    .hero-date-strip .vline {
      width: 1px;
      height: 55px;
      background: rgba(143,188,143,0.3);
    }

    .hero-right {
      background: var(--menta-pale);
      display: flex;
      flex-direction: column;
      justify-content: center;
      position: relative;
      overflow: hidden;
    }

    .hero-right::before {
      content: 'COUTURE';
      position: absolute;
      font-family: 'Playfair Display', serif;
      font-weight: 900;
      font-size: 13vw;
      color: rgba(143,188,143,0.12);
      bottom: -2rem;
      right: -1rem;
      white-space: nowrap;
      pointer-events: none;
      letter-spacing: -0.02em;
      line-height: 1;
    }

    .hero-right-content {
      padding: 5rem 4rem 5rem 5rem;
      position: relative;
      z-index: 1;
    }

    .badge-evento {
      display: inline-block;
      background: var(--menta);
      color: var(--negro);
      font-size: 0.58rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      padding: 0.4rem 1rem;
      margin-bottom: 2.5rem;
      font-weight: 500;
      opacity: 0;
      animation: fadeUp 0.8s ease forwards 0.6s;
    }

    .hero-right h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.5rem, 2.5vw, 2.2rem);
      font-weight: 700;
      color: var(--negro);
      line-height: 1.2;
      margin-bottom: 1.5rem;
      opacity: 0;
      animation: fadeUp 0.9s ease forwards 0.8s;
    }

    .hero-right p {
      font-size: 0.95rem;
      line-height: 1.85;
      color: var(--gris-texto);
      max-width: 380px;
      opacity: 0;
      animation: fadeUp 0.9s ease forwards 1s;
    }

    .hero-right p + p { margin-top: 1.2rem; }

    /* ── INTRO ── */
    .intro {
      padding: 8rem 2rem;
      background: var(--blanco);
    }

    .intro-inner {
      max-width: 760px;
      margin: 0 auto;
      text-align: center;
    }

    .label {
      display: inline-block;
      font-size: 0.6rem;
      letter-spacing: 0.38em;
      text-transform: uppercase;
      color: var(--menta-dark);
      margin-bottom: 2rem;
    }

    .intro h2 {
      font-family: 'Playfair Display', serif;
      font-weight: 700;
      font-size: clamp(2rem, 4vw, 3rem);
      color: var(--negro);
      line-height: 1.18;
      margin-bottom: 2.5rem;
    }

    .intro h2 em {
      font-style: italic;
      color: var(--menta-dark);
    }

    .intro p {
      font-size: 1rem;
      line-height: 1.9;
      color: var(--gris-texto);
      margin-bottom: 1.4rem;
    }

    /* ── SEPARADOR ── */
    .sep {
      text-align: center;
      padding: 2rem;
      display: flex;
      align-items: center;
      gap: 1.5rem;
      max-width: 500px;
      margin: 0 auto;
    }
    .sep-line {
      flex: 1;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--menta), transparent);
    }
    .sep span { font-size: 0.85rem; color: var(--menta); letter-spacing: 0.3em; }

    /* ── PROGRAMA ── */
    .programa {
      background: var(--negro);
      padding: 7rem 2rem;
      position: relative;
      overflow: hidden;
    }

    .programa::before {
      content: 'PROGRAMME';
      position: absolute;
      font-family: 'Playfair Display', serif;
      font-weight: 900;
      font-size: 14vw;
      color: rgba(143,188,143,0.04);
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      white-space: nowrap;
      pointer-events: none;
      letter-spacing: 0.05em;
    }

    .programa-inner {
      max-width: 900px;
      margin: 0 auto;
      position: relative;
      z-index: 1;
    }

    .programa-header {
      text-align: center;
      margin-bottom: 5rem;
    }

    .programa-header .label { color: var(--menta); }

    .programa-header h2 {
      font-family: 'Playfair Display', serif;
      font-weight: 700;
      font-size: clamp(2rem, 4.5vw, 3.2rem);
      color: var(--blanco);
      line-height: 1.15;
    }

    .programa-header h2 em {
      font-style: italic;
      color: var(--menta);
    }

    .pases { display: flex; flex-direction: column; }

    .pase {
      display: grid;
      grid-template-columns: 130px 2px 1fr;
      gap: 0 2.5rem;
      padding: 2.8rem 0;
      position: relative;
    }

    .pase-hora { text-align: right; padding-top: 0.3rem; }

    .pase-hora .time {
      font-family: 'Playfair Display', serif;
      font-weight: 700;
      font-size: 1.5rem;
      color: var(--menta);
      display: block;
      line-height: 1;
    }

    .pase-hora .time-label {
      font-size: 0.58rem;
      letter-spacing: 0.28em;
      text-transform: uppercase;
      color: rgba(143,188,143,0.4);
      margin-top: 0.3rem;
      display: block;
    }

    .pase-line {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .pase-dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: var(--menta);
      flex-shrink: 0;
      margin-top: 0.4rem;
      transition: background 0.3s;
    }

    .pase:hover .pase-dot { background: var(--rosa); }

    .pase-vline {
      flex: 1;
      width: 1px;
      background: rgba(143,188,143,0.2);
      margin-top: 4px;
    }

    .pase:last-child .pase-vline { display: none; }

    .pase-body { padding-bottom: 1rem; }

    .pase-emoji {
      font-size: 1.2rem;
      display: block;
      margin-bottom: 0.6rem;
    }

    .pase-nombre {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem;
      font-weight: 700;
      color: var(--blanco);
      margin-bottom: 0.7rem;
      line-height: 1.2;
    }

    .pase-nombre em {
      font-style: italic;
      color: var(--menta);
      font-weight: 400;
    }

    .pase-desc {
      font-size: 0.9rem;
      line-height: 1.75;
      color: rgba(250,250,248,0.45);
      max-width: 520px;
    }

    /* ── INFO ── */
    .info {
      background: var(--blanco);
      padding: 7rem 2rem;
    }

    .info-inner { max-width: 1050px; margin: 0 auto; }

    .info-header { text-align: center; margin-bottom: 4.5rem; }

    .info-header h2 {
      font-family: 'Playfair Display', serif;
      font-weight: 700;
      font-size: clamp(2rem, 4vw, 2.8rem);
      color: var(--negro);
    }

    .info-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 0;
      margin-bottom: 4rem;
      border: 1px solid rgba(143,188,143,0.25);
    }

    .info-card {
      padding: 2.8rem 2rem;
      text-align: center;
      border-right: 1px solid rgba(143,188,143,0.25);
      transition: background 0.25s;
    }

    .info-card:last-child { border-right: none; }
    .info-card:hover { background: var(--menta-pale); }

    .info-card .icon { font-size: 1.8rem; display: block; margin-bottom: 1.1rem; }

    .info-card h3 {
      font-size: 0.58rem;
      letter-spacing: 0.32em;
      text-transform: uppercase;
      color: var(--menta-dark);
      margin-bottom: 0.8rem;
      font-weight: 500;
    }

    .info-card .val {
      font-family: 'Playfair Display', serif;
      font-size: 1.2rem;
      font-weight: 700;
      color: var(--negro);
      line-height: 1.35;
    }

    .info-card .sub {
      font-size: 0.75rem;
      color: #888;
      margin-top: 0.35rem;
      font-weight: 300;
    }

    .venue {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 0;
      border: 1px solid rgba(143,188,143,0.25);
    }

    .venue-left {
      background: var(--menta);
      padding: 3.5rem 3rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .venue-left .venue-tag {
      font-size: 0.58rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: rgba(26,26,26,0.55);
      margin-bottom: 1rem;
      font-weight: 500;
    }

    .venue-left h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1.9rem;
      font-weight: 900;
      color: var(--negro);
      line-height: 1.1;
    }

    .venue-left .venue-address {
      font-size: 0.8rem;
      color: rgba(26,26,26,0.6);
      letter-spacing: 0.05em;
      margin-top: 0.8rem;
    }

    .venue-right {
      background: var(--gris-suave);
      padding: 3.5rem 3rem;
    }

    .venue-right p {
      font-size: 0.95rem;
      line-height: 1.85;
      color: var(--gris-texto);
    }

    .venue-right p + p { margin-top: 1.1rem; }

    /* ── DRESS CODE (ROSA) ── */
    .dresscode {
      background: var(--rosa);
      padding: 5rem 2rem;
      text-align: center;
    }

    .dresscode h2 {
      font-family: 'Playfair Display', serif;
      font-weight: 900;
      font-size: clamp(1.8rem, 3.5vw, 2.6rem);
      color: var(--negro);
      margin-bottom: 0.8rem;
    }

    .dresscode p {
      font-size: 0.9rem;
      color: rgba(26,26,26,0.65);
      letter-spacing: 0.05em;
    }

    .dresscode-items {
      display: flex;
      justify-content: center;
      gap: 3rem;
      margin-top: 2.5rem;
      flex-wrap: wrap;
    }

    .dc-item { text-align: center; }
    .dc-item .dc-icon { font-size: 1.8rem; display: block; margin-bottom: 0.5rem; }
    .dc-item .dc-label {
      font-size: 0.62rem;
      letter-spacing: 0.28em;
      text-transform: uppercase;
      color: rgba(26,26,26,0.55);
      font-weight: 500;
    }
    .dc-item .dc-val {
      font-family: 'Playfair Display', serif;
      font-size: 1rem;
      font-weight: 700;
      color: var(--negro);
      margin-top: 0.2rem;
    }

    /* ── CTA ── */
    .cta-section {
      background: var(--negro);
      padding: 8rem 2rem;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .cta-section::before {
      content: '';
      position: absolute;
      width: 700px; height: 700px;
      border-radius: 50%;
      border: 1px solid rgba(143,188,143,0.08);
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
    }
    .cta-section::after {
      content: '';
      position: absolute;
      width: 450px; height: 450px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(143,188,143,0.05) 0%, transparent 70%);
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
    }

    .cta-inner { position: relative; z-index: 1; }

    .cta-section .label { color: var(--menta); }

    .cta-section h2 {
      font-family: 'Playfair Display', serif;
      font-weight: 700;
      font-size: clamp(2.2rem, 5vw, 3.8rem);
      color: var(--blanco);
      line-height: 1.1;
      margin-bottom: 1.2rem;
    }

    .cta-section h2 em {
      font-style: italic;
      color: var(--menta);
    }

    .cta-note {
      font-size: 0.82rem;
      color: rgba(250,250,248,0.35);
      margin-bottom: 3.5rem;
      letter-spacing: 0.06em;
    }

    .btn-reserva {
      display: inline-block;
      background: var(--menta);
      color: var(--negro);
      font-family: 'DM Sans', sans-serif;
      font-size: 0.7rem;
      font-weight: 500;
      letter-spacing: 0.28em;
      text-transform: uppercase;
      padding: 1.3rem 4rem;
      text-decoration: none;
      border: none;
      cursor: pointer;
      position: relative;
      overflow: hidden;
      transition: background 0.25s, transform 0.2s, box-shadow 0.2s;
    }

    .btn-reserva::before {
      content: '';
      position: absolute;
      inset: 0;
      background: rgba(255,255,255,0.2);
      transform: translateX(-105%);
      transition: transform 0.4s ease;
    }

    .btn-reserva:hover::before { transform: translateX(0); }
    .btn-reserva:hover {
      background: var(--menta-dark);
      transform: translateY(-2px);
      box-shadow: 0 10px 35px rgba(143,188,143,0.25);
    }
    .btn-reserva:active { transform: translateY(0); }

    .btn-sub {
      display: block;
      margin-top: 1.4rem;
      font-size: 0.68rem;
      color: rgba(143,188,143,0.3);
      letter-spacing: 0.12em;
    }

    /* ── FOOTER ── */
    footer {
      background: #111;
      padding: 4rem 3rem 3rem;
      display: grid;
      grid-template-columns: 1fr auto;
      align-items: end;
      gap: 2rem;
      border-top: 1px solid rgba(143,188,143,0.12);
    }

    .footer-logo {
      font-family: 'Playfair Display', serif;
      font-weight: 900;
      font-size: 1.3rem;
      color: var(--blanco);
      text-transform: uppercase;
      letter-spacing: 0.06em;
    }

    .footer-logo span {
      display: block;
      font-style: italic;
      font-weight: 400;
      font-size: 0.8rem;
      color: var(--menta);
      letter-spacing: 0.12em;
      margin-top: 0.1rem;
    }

    .footer-tagline {
      font-family: 'Playfair Display', serif;
      font-style: italic;
      font-size: 0.85rem;
      color: rgba(250,250,248,0.3);
      margin-top: 1.2rem;
    }

    .footer-copy {
      font-size: 0.65rem;
      color: rgba(143,188,143,0.25);
      letter-spacing: 0.1em;
      text-align: right;
    }

    /* ── ANIMACIONES ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      .hero { grid-template-columns: 1fr; min-height: auto; }
      .hero-left { padding: 5rem 2.5rem 4rem; }
      .hero-right-content { padding: 3rem 2.5rem; }
      .hero-right::before { display: none; }
      .info-grid { grid-template-columns: 1fr 1fr; }
      .info-card { border-bottom: 1px solid rgba(143,188,143,0.25); }
      .venue { grid-template-columns: 1fr; }
      footer { grid-template-columns: 1fr; }
      .footer-copy { text-align: left; }
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
    }

    @media (max-width: 580px) {
      .pase { grid-template-columns: 90px 2px 1fr; gap: 0 1.5rem; }
      .pase-hora .time { font-size: 1.1rem; }
      .hero-left { padding: 4rem 1.8rem 3rem; }
      .hero-right-content { padding: 2.5rem 1.8rem; }
      .dresscode-items { gap: 1.8rem; }
    }
  </style>
</head>
<body>

  <!-- ════ TOPBAR ════ -->
  <div class="topbar">
    Desfile · 24 abril 2026 · Hotel Palace Madrid · Aforo limitado
  </div>

  <!-- ════ NAV ════ -->
  <nav>
    <div class="nav-logo">Guau <span>Couture</span></div>
    <ul class="nav-links">
      <li><a href="#evento">El evento</a></li>
      <li><a href="#programa">Programa</a></li>
      <li><a href="#info">Información</a></li>
    </ul>
    <a href="#reserva" class="nav-cta">🐾 Reservar entrada</a>
  </nav>

  <!-- ════ HERO ════ -->
  <section class="hero">

    <div class="hero-left">
      <p class="hero-eyebrow">Guau Couture · Temporada 2026</p>
      <h1 class="hero-title">
        Haute<br>
        <span class="accent">Couture</span>
        Canina
      </h1>
      <p class="hero-tagline">
        La distincion no se compra.<br>Se hereda. O se viste.
      </p>
      <div class="hero-date-strip">
        <div class="date-num">24</div>
        <div class="vline"></div>
        <div class="date-detail">
          <span class="date-month">Abril · 2026</span>
          <span class="date-place">Hotel Palace · Madrid</span>
        </div>
      </div>
    </div>

    <div class="hero-right">
      <div class="hero-right-content">
        <span class="badge-evento">Desfile oficial</span>
        <h2>La primera gran pasarela de la maison</h2>
        <p>
          Tres pases. Dieciocho looks. Una cantidad no revelada de perros de alcurnia con más criterio estético que la mayoría de personas en sala.
        </p>
        <p>
          Guau Couture presenta su colección más ambiciosa desde que abrió sus puertas en 2019. El formato es nuevo. La exigencia, la de siempre.
        </p>
      </div>
    </div>

  </section>

  <!-- ════ INTRO ════ -->
  <section class="intro" id="evento">
    <div class="intro-inner">
      <span class="label reveal">El evento</span>
      <h2 class="reveal">
        Un desfile que se ha estado<br>
        <em>preparando cuatro años</em>
      </h2>
      <p class="reveal">
        Cada colección de Guau Couture parte de la misma pregunta: ¿por qué el lujo debería acabar en la correa? La respuesta, esta temporada, llega en forma de pasarela. Primera edición. Aforo de 180 personas. Sin repetición.
      </p>
      <p class="reveal">
        El desfile no es un escaparate. Es una declaración de intenciones sobre lo que significa vestir bien, sobre el trabajo de taller que hay detrás de cada pieza y, si somos sinceros, sobre el tipo de perro que merece un forro en Liberty estampado. El dress code para los propietarios también cuenta. Es de etiqueta rigurosa.
      </p>
    </div>
  </section>

  <div class="sep reveal">
    <div class="sep-line"></div>
    <span>✦</span>
    <div class="sep-line"></div>
  </div>

  <!-- ════ PROGRAMA ════ -->
  <section class="programa" id="programa">
    <div class="programa-inner">

      <div class="programa-header reveal">
        <span class="label">Programa oficial</span>
        <h2>El orden <em>del desfile</em></h2>
      </div>

      <div class="pases">

        <div class="pase reveal">
          <div class="pase-hora">
            <span class="time">18:30</span>
            <span class="time-label">Apertura</span>
          </div>
          <div class="pase-line">
            <div class="pase-dot"></div>
            <div class="pase-vline"></div>
          </div>
          <div class="pase-body">
            <span class="pase-emoji">🥂</span>
            <h3 class="pase-nombre"><em>Les Premiers Pas</em> — La llegada</h3>
            <p class="pase-desc">
              Cóctel de bienvenida en el vestíbulo del Palace mientras los primeros modelos caninos ocupan sus posiciones en backstage. El protocolo de presentación incluye, inevitablemente, un momento para fotografías con los invitados.
            </p>
          </div>
        </div>

        <div class="pase reveal">
          <div class="pase-hora">
            <span class="time">19:30</span>
            <span class="time-label">Pase I</span>
          </div>
          <div class="pase-line">
            <div class="pase-dot"></div>
            <div class="pase-vline"></div>
          </div>
          <div class="pase-body">
            <span class="pase-emoji">🌿</span>
            <h3 class="pase-nombre"><em>Saison Verte</em> — Colección Primavera</h3>
            <p class="pase-desc">
              Tejidos ligeros, lino belga en tonos caqui y marfil, los primeros abrigos impermeables con forro en Liberty estampado. Para el can de impecable porte que tiene agenda de mañana y prefiere parecer que no.
            </p>
          </div>
        </div>

        <div class="pase reveal">
          <div class="pase-hora">
            <span class="time">20:30</span>
            <span class="time-label">Pase II</span>
          </div>
          <div class="pase-line">
            <div class="pase-dot"></div>
            <div class="pase-vline"></div>
          </div>
          <div class="pase-body">
            <span class="pase-emoji">🖤</span>
            <h3 class="pase-nombre"><em>Nuit Absolue</em> — Black tie canino</h3>
            <p class="pase-desc">
              La colección de noche. Terciopelo azul medianoche, bordados en hilo de seda y los primeros collares con diamantes certificados de la firma. Algunos looks llevan más trabajo de taller que un traje sastre de alta costura hecho a medida.
            </p>
          </div>
        </div>

        <div class="pase reveal">
          <div class="pase-hora">
            <span class="time">21:30</span>
            <span class="time-label">Grand Final</span>
          </div>
          <div class="pase-line">
            <div class="pase-dot"></div>
            <div class="pase-vline"></div>
          </div>
          <div class="pase-body">
            <span class="pase-emoji">✦</span>
            <h3 class="pase-nombre"><em>Le Grand Final</em> — Desfile colectivo</h3>
            <p class="pase-desc">
              Todos los modelos, todas las colecciones, un único recorrido. La directora creativa Valeria Montoro cierra el desfile en persona. Hay champán, aplausos y, si todo sale según lo previsto, al menos un perro de alcurnia que roba el protagonismo al resto.
            </p>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ════ INFO ════ -->
  <section class="info" id="info">
    <div class="info-inner">

      <div class="info-header reveal">
        <span class="label">Información práctica</span>
        <h2>Todo lo que necesitas saber</h2>
      </div>

      <div class="info-grid">
        <div class="info-card reveal">
          <span class="icon">📅</span>
          <h3>Fecha</h3>
          <p class="val">Jueves, 24 de abril</p>
          <p class="sub">2026</p>
        </div>
        <div class="info-card reveal">
          <span class="icon">🕕</span>
          <h3>Acceso</h3>
          <p class="val">Desde las 18:00</p>
          <p class="sub">Desfile a las 18:30 h</p>
        </div>
        <div class="info-card reveal">
          <span class="icon">📍</span>
          <h3>Lugar</h3>
          <p class="val">Hotel Palace<br>Madrid</p>
          <p class="sub">Plaza de las Cortes, 7</p>
        </div>
        <div class="info-card reveal">
          <span class="icon">🎟</span>
          <h3>Aforo</h3>
          <p class="val">180 invitados</p>
          <p class="sub">Lista de espera activa</p>
        </div>
      </div>

      <div class="venue reveal">
        <div class="venue-left">
          <span class="venue-tag">Sede oficial del desfile</span>
          <h3>Hotel Palace<br>Madrid</h3>
          <p class="venue-address">Plaza de las Cortes, 7 · Madrid</p>
        </div>
        <div class="venue-right">
          <p>
            La cúpula de cristal del Palace tiene algo que los salones modernos no pueden comprar: memoria. Ha sido escenario de historia, política y secretos que nadie ha escrito. Esta noche añadiremos moda canina a esa lista.
          </p>
          <p>
            El Gran Salón estará adaptado con pasarela central de 18 metros, zona de butacas numeradas para propietarios e invitados de prensa, y un área reservada para los modelos en backstage. El acceso se realizará por la entrada principal desde las 18:00 h.
          </p>
        </div>
      </div>

    </div>
  </section>

  <!-- ════ DRESS CODE ════ -->
  <section class="dresscode">
    <span class="label reveal">Dress code</span>
    <h2 class="reveal">La etiqueta es parte del espectáculo</h2>
    <p class="reveal">Se ruega puntualidad. El lujo no espera, pero tampoco grita.</p>
    <div class="dresscode-items">
      <div class="dc-item reveal">
        <span class="dc-icon">🎩</span>
        <span class="dc-label">Propietarios</span>
        <p class="dc-val">Etiqueta rigurosa</p>
      </div>
      <div class="dc-item reveal">
        <span class="dc-icon">🐾</span>
        <span class="dc-label">Modelos</span>
        <p class="dc-val">Guau Couture</p>
      </div>
      <div class="dc-item reveal">
        <span class="dc-icon">📸</span>
        <span class="dc-label">Prensa</span>
        <p class="dc-val">Acreditación previa</p>
      </div>
    </div>
  </section>

  <!-- ════ CTA ════ -->
  <section class="cta-section" id="reserva">
    <div class="cta-inner">
      <span class="label reveal">Entradas</span>
      <h2 class="reveal">¿Tiene usted <em>entrada</em>?</h2>
      <p class="cta-note reveal">Aforo limitado · 180 butacas · Lista de espera activa</p>
      <a href="#" class="btn-reserva reveal" onclick="return false;">
        🐾&nbsp;&nbsp;Reservar mi entrada
      </a>
      <span class="btn-sub">Las entradas se asignan por orden de solicitud. Sin excepciones.</span>
    </div>
  </section>

  <!-- ════ FOOTER ════ -->
  <footer>
    <div>
      <div class="footer-logo">
        Guau Couture
        <span>Maison de Mode Canine — Madrid</span>
      </div>
      <p class="footer-tagline">"La distincion no se compra. Se hereda. O se viste."</p>
    </div>
    <p class="footer-copy">© 2026 Guau Couture.<br>Todos los derechos reservados.</p>
  </footer>

  <script>
    const reveals = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const siblings = [...entry.target.parentElement.querySelectorAll('.reveal:not(.visible)')];
          const idx = siblings.indexOf(entry.target);
          setTimeout(() => entry.target.classList.add('visible'), Math.min(idx, 3) * 90);
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.1 });
    reveals.forEach(el => observer.observe(el));
  </script>

</body>
</html>
