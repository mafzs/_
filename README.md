
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bar Bolas – O ponto certo do seu happy hour</title>
  <meta name="description" content="Bar Bolas: petiscos, cervejas geladas, música ao vivo e o melhor happy hour da cidade!" />
  
  <!-- Configurações de URL e SEO -->
  <link rel="canonical" href="https://www.bardobolas.com.br" />
  <meta property="og:title" content="Bar Bolas – O ponto certo do seu happy hour" />
  <meta property="og:description" content="Petiscos, cervejas geladas e música ao vivo em Mongaguá." />
  <meta property="og:url" content="https://www.bardobolas.com.br" />
  <meta property="og:type" content="website" />

  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet" />
  <style>
/* === REMOVER MARCA D'ÁGUA DA PLATAFORMA (MANUS) === */
[id*="manus"], [class*="manus"], a[href*="manus.space"] {
  display: none !important;
  visibility: hidden !important;
  opacity: 0 !important;
  pointer-events: none !important;
}

/* ========================================
   BAR BOLAS – style.css
   Design: Rústico-moderno, cores quentes
======================================== */

/* === VARIÁVEIS E RESET === */
:root {
  --laranja:       #E8611A;
  --laranja-hover: #c9511a;
  --amarelo:       #F5A623;
  --amarelo-claro: #FFD166;
  --preto:         #1A1208;
  --preto-soft:    #2C2217;
  --marrom:        #5C3D2E;
  --madeira:       #8B6046;
  --creme:         #FFF8EE;
  --creme-escuro:  #F3E8D5;
  --cinza-texto:   #5A4A3A;
  --branco:        #FFFFFF;
  --verde-wa:      #25D366;
  --sombra:        0 4px 20px rgba(26,18,8,.15);
  --sombra-forte:  0 8px 40px rgba(26,18,8,.25);
  --radius:        12px;
  --radius-lg:     20px;
  --trans:         0.3s ease;
  --font-display:  'Bebas Neue', sans-serif;
  --font-body:     'Nunito', sans-serif;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  font-family: var(--font-body);
  background-color: var(--creme);
  color: var(--preto);
  line-height: 1.6;
  overflow-x: hidden;
}

img { max-width: 100%; display: block; }
a  { text-decoration: none; color: inherit; }
ul { list-style: none; }

/* === UTILITÁRIOS === */
.container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 20px;
}

.section { padding: 90px 0; }

.section-tag {
  display: inline-block;
  background: var(--amarelo-claro);
  color: var(--marrom);
  font-weight: 800;
  font-size: .78rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding: 6px 16px;
  border-radius: 50px;
  margin-bottom: 14px;
}

.section-tag.center { display: block; text-align: center; }

.section-title {
  font-family: var(--font-display);
  font-size: clamp(2rem, 5vw, 3.2rem);
  letter-spacing: 1px;
  line-height: 1.1;
  color: var(--preto);
  margin-bottom: 32px;
}
.section-title.center { text-align: center; }

/* === BOTÕES === */
.btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 30px;
  border-radius: 50px;
  font-family: var(--font-body);
  font-weight: 800;
  font-size: 1rem;
  cursor: pointer;
  transition: transform var(--trans), box-shadow var(--trans), background var(--trans);
  border: none;
}

.btn-primary {
  background: var(--laranja);
  color: var(--branco);
}
.btn-primary:hover {
  background: var(--laranja-hover);
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(232,97,26,.4);
}

.btn-outline {
  background: transparent;
  color: var(--branco);
  border: 2px solid rgba(255,255,255,.7);
}
.btn-outline:hover {
  background: rgba(255,255,255,.15);
  transform: translateY(-2px);
}



/* === HEADER === */
#header {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  padding: 0;
  transition: background var(--trans), box-shadow var(--trans), padding var(--trans);
}

#header.scrolled {
  background: rgba(26,18,8,.97);
  backdrop-filter: blur(12px);
  box-shadow: 0 2px 20px rgba(0,0,0,.3);
}

.header-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 72px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
}
.logo-icon { font-size: 1.8rem; }
.logo-text {
  font-family: var(--font-display);
  font-size: 1.6rem;
  letter-spacing: 2px;
  color: var(--branco);
  text-shadow: 0 2px 10px rgba(0,0,0,.3);
}

.nav-list {
  display: flex;
  align-items: center;
  gap: 8px;
}

.nav-link {
  color: rgba(255,255,255,.85);
  font-weight: 700;
  font-size: .95rem;
  padding: 8px 16px;
  border-radius: 50px;
  transition: color var(--trans), background var(--trans);
}
.nav-link:hover {
  color: var(--amarelo-claro);
  background: rgba(255,255,255,.1);
}

/* Hamburger */
.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 6px;
}
.hamburger span {
  width: 26px;
  height: 2px;
  background: var(--branco);
  border-radius: 2px;
  transition: transform var(--trans), opacity var(--trans);
}
.hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.hamburger.open span:nth-child(2) { opacity: 0; }
.hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

/* === HERO === */
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  background: var(--preto-soft) url('https://images.unsplash.com/photo-1514362545857-3bc16c4c7d1b?auto=format&fit=crop&q=80&w=1920') no-repeat center center/cover;
  overflow: hidden;
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    160deg,
    rgba(26,18,8,.82) 0%,
    rgba(92,61,46,.7) 50%,
    rgba(26,18,8,.88) 100%
  );
}

.hero-content {
  position: relative;
  z-index: 2;
  padding: 20px;
  max-width: 760px;
}

.hero-eyebrow {
  font-weight: 700;
  font-size: 1rem;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--amarelo-claro);
  margin-bottom: 12px;
}

.hero-title {
  font-family: var(--font-display);
  font-size: clamp(3.5rem, 14vw, 9rem);
  letter-spacing: 4px;
  line-height: .95;
  color: var(--branco);
  text-shadow: 0 4px 30px rgba(0,0,0,.4);
  margin-bottom: 20px;
}

.hero-subtitle {
  font-size: clamp(1.1rem, 3vw, 1.5rem);
  color: rgba(255,255,255,.9);
  font-weight: 600;
  margin-bottom: 40px;
}

.hero-btns {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
}

/* Badge flutuante */
.hero-badge {
  position: absolute;
  bottom: 40px;
  right: 40px;
  z-index: 2;
  background: var(--amarelo);
  color: var(--preto);
  width: 90px;
  height: 90px;
  border-radius: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-weight: 800;
  font-size: .75rem;
  text-transform: uppercase;
  letter-spacing: 1px;
  line-height: 1.2;
  box-shadow: var(--sombra-forte);
  animation: float 3s ease-in-out infinite;
}
.hero-badge strong { font-family: var(--font-display); font-size: 1.6rem; letter-spacing: 1px; }

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50%       { transform: translateY(-10px); }
}

/* === SOBRE === */
.sobre { background: var(--branco); }

.sobre-grid {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.sobre-text p {
  color: var(--cinza-texto);
  margin-bottom: 16px;
  font-size: 1.05rem;
}

.sobre-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 24px;
  justify-content: center;
}
.sobre-tags span {
  background: var(--creme-escuro);
  color: var(--marrom);
  padding: 8px 16px;
  border-radius: 50px;
  font-weight: 700;
  font-size: .88rem;
  display: flex;
  align-items: center;
  gap: 6px;
}

/* === DESTAQUES === */
.destaques { background: var(--preto-soft); }
.destaques .section-tag { background: rgba(245,166,35,.2); color: var(--amarelo-claro); }
.destaques .section-title { color: var(--branco); }

.destaques-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.destaque-card {
  background: rgba(255,255,255,.05);
  border: 1px solid rgba(255,255,255,.08);
  border-radius: var(--radius);
  padding: 32px 28px;
  transition: background var(--trans), transform var(--trans), border-color var(--trans);
}
.destaque-card:hover {
  background: rgba(255,255,255,.09);
  transform: translateY(-4px);
  border-color: rgba(245,166,35,.3);
}
.destaque-card h3 { color: var(--branco); font-size: 1.1rem; margin: 14px 0 8px; }
.destaque-card p  { color: rgba(255,255,255,.6); font-size: .95rem; }

.destaque-icon {
  width: 54px; height: 54px;
  background: linear-gradient(135deg, var(--laranja), var(--amarelo));
  border-radius: 14px;
  display: flex; align-items: center; justify-content: center;
  font-size: 1.4rem;
  color: var(--branco);
}

/* === SERVIÇOS === */
.servicos { background: var(--branco); }

.servicos-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-bottom: 48px;
}

.servico-card {
  background: var(--creme);
  border-radius: var(--radius);
  padding: 30px 24px;
  text-align: center;
  border: 2px solid transparent;
  transition: all var(--trans);
}
.servico-card:hover {
  border-color: var(--laranja);
  transform: translateY(-4px);
}
.servico-card i {
  font-size: 2rem;
  color: var(--laranja);
  margin-bottom: 14px;
}
.servico-card h3 { font-size: 1.05rem; margin-bottom: 8px; }
.servico-card p  { font-size: .9rem; color: var(--cinza-texto); }

.servico-card.sem-reserva {
  background: #FFF3F3;
  border-color: #FFD0D0;
}
.servico-card.sem-reserva i { color: #C0392B; }

/* Acessibilidade */
.acessibilidade {
  background: linear-gradient(135deg, var(--preto), var(--preto-soft));
  color: var(--branco);
  border-radius: var(--radius-lg);
  padding: 36px;
  margin-bottom: 36px;
}
.acessibilidade h3 {
  font-size: 1.3rem;
  margin-bottom: 22px;
  display: flex;
  align-items: center;
  gap: 12px;
  color: var(--amarelo-claro);
}
.aces-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 14px;
}
.aces-grid span {
  background: rgba(255,255,255,.08);
  padding: 12px 16px;
  border-radius: var(--radius);
  font-size: .9rem;
  display: flex;
  align-items: center;
  gap: 8px;
}
.aces-grid span i { color: var(--verde-wa); }

/* Ambiente e pagamentos */
.ambiente-pagamento {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
}
.ambiente-box, .pagamento-box {
  background: var(--creme-escuro);
  border-radius: var(--radius);
  padding: 28px;
}
.ambiente-box h3, .pagamento-box h3 {
  font-size: 1.1rem;
  margin-bottom: 16px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.ambiente-box h3 i, .pagamento-box h3 i { color: var(--laranja); }

.tags-row {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.tags-row span {
  background: var(--branco);
  border-radius: 50px;
  padding: 6px 14px;
  font-size: .85rem;
  font-weight: 700;
  color: var(--marrom);
  display: flex;
  align-items: center;
  gap: 6px;
}

/* === CONTATO === */
.contato { background: var(--creme-escuro); }

.contato-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  align-items: start;
}

.info-card {
  display: flex;
  gap: 18px;
  align-items: flex-start;
  background: var(--branco);
  border-radius: var(--radius);
  padding: 22px;
  margin-bottom: 16px;
  box-shadow: var(--sombra);
  transition: transform var(--trans);
}
.info-card:hover { transform: translateX(4px); }
.info-card > i {
  font-size: 1.4rem;
  color: var(--laranja);
  margin-top: 2px;
  flex-shrink: 0;
}
.info-card h4 { font-size: .85rem; text-transform: uppercase; letter-spacing: 1px; color: var(--madeira); margin-bottom: 6px; }
.info-card p  { color: var(--cinza-texto); font-size: .97rem; }
.info-card small {
  display: block;
  margin-top: 8px;
  color: var(--laranja-hover);
  font-weight: 700;
  font-size: .82rem;
  display: flex;
  align-items: center;
  gap: 6px;
}

.horario-table { width: 100%; border-collapse: collapse; }
.horario-table td { padding: 4px 0; font-size: .93rem; color: var(--cinza-texto); }
.horario-table td:last-child { text-align: right; font-weight: 700; color: var(--preto); }

.mapa {
  border-radius: var(--radius-lg);
  overflow: hidden;
  height: 440px;
  box-shadow: var(--sombra-forte);
}
.mapa iframe { display: block; }

/* === FOOTER === */
.footer {
  background: var(--preto);
  color: rgba(255,255,255,.7);
  padding: 64px 0 0;
}

.footer-inner {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: 48px;
  padding-bottom: 48px;
  border-bottom: 1px solid rgba(255,255,255,.08);
}

.footer-brand .logo-text {
  font-family: var(--font-display);
  font-size: 1.8rem;
  letter-spacing: 2px;
  display: block;
  margin-bottom: 12px;
}
.footer-brand p { font-size: .95rem; margin-bottom: 24px; }

.social-links { display: flex; gap: 12px; }
.social-links a {
  width: 40px; height: 40px;
  background: rgba(255,255,255,.08);
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem;
  color: rgba(255,255,255,.7);
  transition: background var(--trans), color var(--trans), transform var(--trans);
}
.social-links a:hover {
  background: var(--laranja);
  color: var(--branco);
  transform: translateY(-3px);
}

.footer-horario h4,
.footer-nav h4 {
  color: var(--branco);
  font-size: .85rem;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-bottom: 18px;
}

.footer-horario ul li {
  display: flex;
  justify-content: space-between;
  padding: 8px 0;
  border-bottom: 1px solid rgba(255,255,255,.05);
  font-size: .92rem;
}
.footer-horario ul li:last-child { border-bottom: none; }

.footer-nav ul li { margin-bottom: 10px; }
.footer-nav ul li a {
  font-size: .93rem;
  transition: color var(--trans);
}
.footer-nav ul li a:hover { color: var(--amarelo-claro); }

.footer-bottom {
  text-align: center;
  padding: 20px;
  font-size: .85rem;
  color: rgba(255,255,255,.35);
}

/* === BACK TO TOP === */
#back-to-top {
  position: fixed;
  bottom: 30px;
  right: 30px;
  z-index: 999;
  background: var(--laranja);
  color: var(--branco);
  border: none;
  border-radius: 50%;
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1rem;
  cursor: pointer;
  box-shadow: 0 4px 20px rgba(232,97,26,.4);
  opacity: 0;
  pointer-events: none;
  transform: translateY(10px);
  transition: opacity var(--trans), transform var(--trans);
}
#back-to-top.visible {
  opacity: 1;
  pointer-events: all;
  transform: translateY(0);
}
#back-to-top:hover { background: var(--laranja-hover); transform: translateY(-3px); }

/* === ANIMAÇÕES (SCROLL) === */
.fade-in {
  opacity: 0;
  transform: translateY(24px);
  animation: fadeInUp .8s ease forwards;
}
.fade-in:nth-child(1) { animation-delay: .1s; }
.fade-in:nth-child(2) { animation-delay: .25s; }
.fade-in:nth-child(3) { animation-delay: .4s; }
.fade-in:nth-child(4) { animation-delay: .55s; }

@keyframes fadeInUp {
  to { opacity: 1; transform: translateY(0); }
}

.reveal {
  opacity: 0;
  transform: translateY(36px);
  transition: opacity .7s ease, transform .7s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* === RESPONSIVO === */
@media (max-width: 1024px) {
  .destaques-grid    { grid-template-columns: repeat(2, 1fr); }
  .servicos-grid     { grid-template-columns: repeat(2, 1fr); }
  .aces-grid         { grid-template-columns: repeat(2, 1fr); }
  .footer-inner      { grid-template-columns: 1fr 1fr; }
  .footer-brand      { grid-column: 1 / -1; }
}

@media (max-width: 768px) {
  .section { padding: 64px 0; }

  /* Header mobile */
  .hamburger { display: flex; }
  #nav {
    position: fixed;
    top: 72px; left: 0; right: 0;
    background: rgba(26,18,8,.98);
    backdrop-filter: blur(14px);
    padding: 24px 20px;
    transform: translateY(-110%);
    opacity: 0;
    transition: transform .35s ease, opacity .35s ease;
  }
  #nav.open { transform: translateY(0); opacity: 1; }
  .nav-list { flex-direction: column; gap: 6px; }
  .nav-link { display: block; padding: 12px 20px; font-size: 1.1rem; }

  /* Hero */
  .hero-badge { bottom: 20px; right: 20px; width: 76px; height: 76px; }

  /* Sobre */
  .sobre-grid { grid-template-columns: 1fr; gap: 36px; }
  .sobre-img img { height: 280px; }

  /* Destaques */
  .destaques-grid { grid-template-columns: 1fr; }

  /* Serviços */
  .servicos-grid        { grid-template-columns: 1fr; }
  .aces-grid            { grid-template-columns: 1fr 1fr; }
  .ambiente-pagamento   { grid-template-columns: 1fr; }

  /* Contato */
  .contato-grid { grid-template-columns: 1fr; }
  .mapa         { height: 280px; }

  /* Footer */
  .footer-inner { grid-template-columns: 1fr; gap: 36px; }
  .footer-brand { grid-column: auto; }
}

@media (max-width: 480px) {
  .hero-btns     { flex-direction: column; align-items: center; }
  .aces-grid     { grid-template-columns: 1fr; }
  .hero-badge    { display: none; }
}
  </style>
</head>
<body>

  <!-- ===== HEADER ===== -->
  <header id="header">
    <div class="container header-inner">
      <a href="#inicio" class="logo">
        <span class="logo-icon">🍺</span>
        <span class="logo-text">Bar Bolas</span>
      </a>
      <nav id="nav">
        <ul class="nav-list">
          <li><a href="#inicio" class="nav-link">Início</a></li>
          <li><a href="#sobre" class="nav-link">Sobre</a></li>
          <li><a href="#servicos" class="nav-link">Serviços</a></li>
          <li><a href="#depoimentos" class="nav-link">Avaliações</a></li>
          <li><a href="#contato" class="nav-link">Contato</a></li>
        </ul>
      </nav>
      <button class="hamburger" id="hamburger" aria-label="Abrir menu">
        <span></span><span></span><span></span>
      </button>
    </div>
  </header>

  <!-- ===== HERO ===== -->
  <section id="inicio" class="hero">
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <p class="hero-eyebrow fade-in">Bem-vindo ao</p>
      <h1 class="hero-title fade-in">Bar Bolas</h1>
      <p class="hero-subtitle fade-in">O ponto certo do seu happy hour 🍻</p>
      <div class="hero-btns fade-in">
        <a href="#contato" class="btn btn-primary">Como Chegar</a>
        <a href="#servicos" class="btn btn-outline">Nossos Serviços</a>
      </div>
    </div>
    <div class="hero-badge">
      <span>Desde</span>
      <strong>2010</strong>
    </div>
  </section>

  <!-- ===== SOBRE ===== -->
  <section id="sobre" class="sobre section">
    <div class="container">
      <div class="sobre-grid">
        <div class="sobre-text reveal">
          <span class="section-tag">Nossa história</span>
          <h2 class="section-title">Bar Bolas:<br/>um lugar pra chamar de seu</h2>
          <p>O Bar Bolas nasceu do amor por boa comida, cerveja gelada e companhia agradável. Aqui você encontra os melhores <strong>petiscos e pratos da culinária brasileira</strong>, preparados com ingredientes frescos e muito carinho.</p>
          <p>Nosso ambiente é <strong>casual e aconchegante</strong>, com mesas na calçada para aquelas noites gostosas e um salão que abraça todo mundo – grupos de amigos, turistas curiosos e universitários que querem relaxar depois de um dia puxado.</p>
          <div class="sobre-tags">
            <span><i class="fa-solid fa-users"></i> Grupos</span>
            <span><i class="fa-solid fa-graduation-cap"></i> Universitários</span>
            <span><i class="fa-solid fa-earth-americas"></i> Turistas</span>
            <span><i class="fa-solid fa-baby"></i> Famílias</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== DESTAQUES ===== -->
  <section class="destaques section">
    <div class="container">
      <span class="section-tag center">Por que nos escolher</span>
      <h2 class="section-title center reveal">O que faz o Bar Bolas<br/>diferente de todos os outros</h2>
      <div class="destaques-grid">
        <div class="destaque-card reveal">
          <div class="destaque-icon"><i class="fa-solid fa-music"></i></div>
          <h3>Música ao vivo</h3>
          <p>Toda sexta e sábado com artistas locais incríveis. Do samba ao rock, sempre tem uma boa trilha.</p>
        </div>
        <div class="destaque-card reveal">
          <div class="destaque-icon"><i class="fa-solid fa-tv"></i></div>
          <h3>Transmissão de esportes</h3>
          <p>Telões de ponta para você não perder nenhum lance. Futebol, UFC, vôlei – tudo aqui!</p>
        </div>
        <div class="destaque-card reveal">
          <div class="destaque-icon"><i class="fa-solid fa-building"></i></div>
          <h3>Mesas na cobertura</h3>
          <p>Vista panorâmica e brisa fresca. O lugar perfeito para um fim de tarde especial.</p>
        </div>
        <div class="destaque-card reveal">
          <div class="destaque-icon"><i class="fa-solid fa-beer-mug-empty"></i></div>
          <h3>Ótima seleção de cervejas</h3>
          <p>Mais de 40 rótulos nacionais e importados, sempre geladas do jeito que você merece.</p>
        </div>
        <div class="destaque-card reveal">
          <div class="destaque-icon"><i class="fa-solid fa-martini-glass-citrus"></i></div>
          <h3>Coquetéis especiais</h3>
          <p>Drinks autorais criados pelos nossos bartenders. Da caipirinha clássica ao coquetel da casa.</p>
        </div>
        <div class="destaque-card reveal">
          <div class="destaque-icon"><i class="fa-solid fa-utensils"></i></div>
          <h3>Petiscos irresistíveis</h3>
          <p>Do bolinho de bacalhau ao dadinho de tapioca, os petiscos do Bar Bolas são lenda na cidade.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== DEPOIMENTOS ===== -->
  <section id="depoimentos" class="depoimentos section">
    <div class="container">
      <span class="section-tag center">Depoimentos</span>
      <h2 class="section-title center reveal">O que nossos clientes dizem</h2>
      <div class="depoimentos-grid">
        <div class="depoimento-card reveal">
          <div class="depoimento-header">
            <div class="depoimento-avatar">JS</div>
            <div class="depoimento-info">
              <h4>João Silva</h4>
              <div class="stars">
                <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
              </div>
            </div>
          </div>
          <p>"Melhor happy hour de Mongaguá! A cerveja está sempre trincando e os petiscos são maravilhosos. O bolinho de bacalhau é imperdível."</p>
        </div>
        <div class="depoimento-card reveal">
          <div class="depoimento-header">
            <div class="depoimento-avatar">MA</div>
            <div class="depoimento-info">
              <h4>Maria de Andrade</h4>
              <div class="stars">
                <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star-half-stroke"></i>
              </div>
            </div>
          </div>
          <p>"Ambiente super agradável e música de qualidade. Excelente lugar para ir com os amigos. O atendimento é nota dez!"</p>
        </div>
        <div class="depoimento-card reveal">
          <div class="depoimento-header">
            <div class="depoimento-avatar">RC</div>
            <div class="depoimento-info">
              <h4>Ricardo Costa</h4>
              <div class="stars">
                <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
              </div>
            </div>
          </div>
          <p>"Sou cliente fiel desde 2015. É o lugar perfeito para relaxar depois do trabalho. Preço justo e qualidade impecável em tudo."</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== SERVIÇOS ===== -->
  <section id="servicos" class="servicos section">
    <div class="container">
      <span class="section-tag center">Comodidade pra você</span>
      <h2 class="section-title center reveal">Nossos serviços</h2>
      <div class="servicos-grid">
        <div class="servico-card reveal">
          <i class="fa-solid fa-chair"></i>
          <h3>Mesas externas</h3>
          <p>Aproveite a brisa e o movimento da rua nas nossas mesas na calçada.</p>
        </div>
        <div class="servico-card reveal">
          <i class="fa-solid fa-motorcycle"></i>
          <h3>Delivery</h3>
          <p>Entregamos no seu endereço com rapidez. Peça pelo WhatsApp ou apps.</p>
        </div>
        <div class="servico-card reveal">
          <i class="fa-solid fa-hand-sparkles"></i>
          <h3>Entrega sem contato</h3>
          <p>Opção de entrega sem contato disponível. Segurança em primeiro lugar.</p>
        </div>
        <div class="servico-card reveal">
          <i class="fa-solid fa-bag-shopping"></i>
          <h3>Para viagem</h3>
          <p>Embalagem especial para você curtir a comida do Bar Bolas em qualquer lugar.</p>
        </div>
        <div class="servico-card reveal">
          <i class="fa-solid fa-store"></i>
          <h3>Consumo no local</h3>
          <p>Mesa reservada... brincadeira! Chegou, senta. É assim que gostamos.</p>
        </div>
        <div class="servico-card sem-reserva reveal">
          <i class="fa-solid fa-calendar-xmark"></i>
          <h3>Sem reservas</h3>
          <p>Não aceitamos reservas. Chega, a gente dá um jeito. Quase sempre tem mesa!</p>
        </div>
      </div>

      <!-- Acessibilidade -->
      <div class="acessibilidade reveal">
        <h3><i class="fa-solid fa-wheelchair"></i> Acessibilidade</h3>
        <div class="aces-grid">
          <span><i class="fa-solid fa-check"></i> Entrada acessível</span>
          <span><i class="fa-solid fa-check"></i> Banheiro acessível</span>
          <span><i class="fa-solid fa-check"></i> Assentos acessíveis</span>
          <span><i class="fa-solid fa-check"></i> Estacionamento acessível</span>
        </div>
      </div>

      <!-- Ambiente -->
      <div class="ambiente-pagamento reveal">
        <div class="ambiente-box">
          <h3><i class="fa-solid fa-couch"></i> Ambiente</h3>
          <div class="tags-row">
            <span>Aconchegante</span>
            <span>Casual</span>
            <span>Tranquilo</span>
            <span>Moderno</span>
            <span>Bom para crianças</span>
          </div>
        </div>
        <div class="pagamento-box">
          <h3><i class="fa-solid fa-credit-card"></i> Pagamentos</h3>
          <div class="tags-row">
            <span><i class="fa-brands fa-cc-visa"></i> Crédito/Débito</span>
            <span><i class="fa-solid fa-nfc-symbol"></i> NFC/Aproximação</span>
            <span>Alelo</span>
            <span>Pluxee</span>
            <span>PIX</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== CONTATO ===== -->
  <section id="contato" class="contato section">
    <div class="container">
      <span class="section-tag center">Venha nos visitar</span>
      <h2 class="section-title center reveal">Onde estamos</h2>
      <div class="contato-grid">
        <div class="contato-info reveal">
          <div class="info-card">
            <i class="fa-solid fa-location-dot"></i>
            <div>
              <h4>Endereço</h4>
              <p>Av. Nossa Sra. de Fátima, 532 – Balneário Agenor de Campos<br/>Mongaguá – SP, 11730-000</p>
              <small><i class="fa-solid fa-triangle-exclamation"></i> Estacionamento com vagas limitadas</small>
            </div>
          </div>
          <div class="info-card">
            <i class="fa-solid fa-phone"></i>
            <div>
              <h4>Telefone</h4>
              <p>(19) 3456-7890</p>
            </div>
          </div>

          <div class="info-card">
            <i class="fa-solid fa-clock"></i>
            <div>
              <h4>Horários</h4>
              <table class="horario-table">
                <tr><td>Seg – Sex</td><td>07h – 00h</td></tr>
                <tr><td>Sábado</td><td>08h – 02h</td></tr>
                <tr><td>Domingo</td><td>10h – 22h</td></tr>
              </table>
            </div>
          </div>
        </div>
        <div class="mapa reveal">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3606.8!2d-46.6908359!3d-24.1274043!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce283d9a29b92d%3A0xf482d68217dc67b8!2sBar+Bolas!5e0!3m2!1spt-BR!2sbr!4v1700000000001"
            width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"
            referrerpolicy="no-referrer-when-downgrade" title="Localização do Bar do Bolas">
          </iframe>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== FOOTER ===== -->
  <footer class="footer">
    <div class="container footer-inner">
      <div class="footer-brand">
        <span class="logo-text">🍺 Bar Bolas</span>
        <p>O ponto certo do seu happy hour.</p>
        <div class="social-links">
          <a href="#" aria-label="Instagram"><i class="fa-brands fa-instagram"></i></a>
          <a href="#" aria-label="Facebook"><i class="fa-brands fa-facebook"></i></a>
          <a href="#" aria-label="TikTok"><i class="fa-brands fa-tiktok"></i></a>
          <a href="#" aria-label="WhatsApp"><i class="fa-brands fa-whatsapp"></i></a>
        </div>
      </div>
      <div class="footer-horario">
        <h4>Horário de funcionamento</h4>
        <ul>
          <li><span>Segunda a Sexta</span><span>07h – 00h</span></li>
          <li><span>Sábado</span><span>08h – 02h</span></li>
          <li><span>Domingo</span><span>10h – 22h</span></li>
          <li><span>Feriados</span><span>10h – 22h</span></li>
        </ul>
      </div>
      <div class="footer-nav">
        <h4>Navegação</h4>
        <ul>
          <li><a href="#inicio">Início</a></li>
          <li><a href="#sobre">Sobre</a></li>
          <li><a href="#depoimentos">Avaliações</a></li>
          <li><a href="#servicos">Serviços</a></li>
          <li><a href="#contato">Contato</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2024 Bar Bolas. Todos os direitos reservados. | Feito com 🍺 e muito carinho.</p>
    </div>
  </footer>

  <!-- Botão voltar ao topo -->
  <button id="back-to-top" aria-label="Voltar ao topo">
    <i class="fa-solid fa-chevron-up"></i>
  </button>

  <script>
/* ========================================
   BAR BOLAS – script.js
======================================== */

'use strict';

/* ===== 1. MENU HAMBÚRGUER ===== */
(function () {
  const hamburger = document.getElementById('hamburger');
  const nav       = document.getElementById('nav');
  const navLinks  = document.querySelectorAll('.nav-link');

  if (!hamburger || !nav) return;

  function toggleMenu(open) {
    hamburger.classList.toggle('open', open);
    nav.classList.toggle('open', open);
    hamburger.setAttribute('aria-expanded', open);
    document.body.style.overflow = open ? 'hidden' : '';
  }

  hamburger.addEventListener('click', () => {
    const isOpen = nav.classList.contains('open');
    toggleMenu(!isOpen);
  });

  navLinks.forEach(link => {
    link.addEventListener('click', () => toggleMenu(false));
  });

  document.addEventListener('click', (e) => {
    if (!nav.contains(e.target) && !hamburger.contains(e.target)) {
      toggleMenu(false);
    }
  });
})();


/* ===== 2. HEADER COM SCROLL ===== */
(function () {
  const header = document.getElementById('header');
  if (!header) return;

  function updateHeader() {
    if (window.scrollY > 60) {
      header.classList.add('scrolled');
    } else {
      header.classList.remove('scrolled');
    }
  }

  window.addEventListener('scroll', updateHeader, { passive: true });
  updateHeader();
})();


/* ===== 3. BOTÃO "VOLTAR AO TOPO" ===== */
(function () {
  const btn = document.getElementById('back-to-top');
  if (!btn) return;

  window.addEventListener('scroll', () => {
    if (window.scrollY > 400) {
      btn.classList.add('visible');
    } else {
      btn.classList.remove('visible');
    }
  }, { passive: true });

  btn.addEventListener('click', () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  });
})();


/* ===== 4. ANIMAÇÕES AO ROLAR (REVEAL) ===== */
(function () {
  const elements = document.querySelectorAll('.reveal');
  if (!elements.length) return;

  function applyDelays() {
    const grids = document.querySelectorAll(
      '.destaques-grid, .servicos-grid, .contato-grid, .depoimentos-grid'
    );
    grids.forEach(grid => {
      const items = grid.querySelectorAll('.reveal');
      items.forEach((item, i) => {
        item.style.transitionDelay = (i * 0.08) + 's';
      });
    });
  }
  applyDelays();

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    },
    { threshold: 0.12 }
  );

  elements.forEach(el => observer.observe(el));
})();


/* ===== 5. SCROLL SUAVE PARA LINKS ÂNCORA ===== */
(function () {
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
      const targetSelector = this.getAttribute('href');
      if (targetSelector === '#') return;

      const target = document.querySelector(targetSelector);
      if (!target) return;

      e.preventDefault();
      const headerH = document.getElementById('header')?.offsetHeight || 72;
      const top = target.getBoundingClientRect().top + window.scrollY - headerH;

      window.scrollTo({ top, behavior: 'smooth' });
    });
  });
})();


/* ===== 6. LINK ATIVO NO MENU CONFORME SEÇÃO VISÍVEL ===== */
(function () {
  const sections  = document.querySelectorAll('section[id]');
  const navLinks  = document.querySelectorAll('.nav-link');
  if (!sections.length || !navLinks.length) return;

  function setActive() {
    const scrollY  = window.scrollY;
    const headerH  = document.getElementById('header')?.offsetHeight || 72;

    let currentId = '';
    sections.forEach(section => {
      const top = section.offsetTop - headerH - 40;
      if (scrollY >= top) currentId = section.id;
    });

    navLinks.forEach(link => {
      link.classList.remove('active');
      if (link.getAttribute('href') === '#' + currentId) {
        link.classList.add('active');
      }
    });
  }

  window.addEventListener('scroll', setActive, { passive: true });
  setActive();
})();


/* ===== 7. EFEITO PARALLAX SUAVE NO HERO ===== */
(function () {
  const hero = document.querySelector('.hero');
  if (!hero) return;

  if (window.matchMedia('(max-width: 768px)').matches) return;

  window.addEventListener('scroll', () => {
    const scrollY = window.scrollY;
    hero.style.backgroundPositionY = (scrollY * 0.4) + 'px';
  }, { passive: true });
})();


/* ===== 8. INICIALIZAÇÃO ===== */
document.addEventListener('DOMContentLoaded', () => {
  console.log('%c🍺 Bar do Bolas', 'font-size:2rem; color:#E8611A; font-weight:bold');
  console.log('%cSite carregado com sucesso! Bom proveito 🎉', 'color:#F5A623');
});
  </script>
</body>
</html>
