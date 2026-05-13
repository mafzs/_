<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bar Bolas — Mongaguá, SP</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --gold: #C9A84C;
    --gold-light: #E8C96B;
    --gold-dark: #9B7A2E;
    --cream: #F5EFE0;
    --dark: #1A1208;
    --dark2: #2C2010;
    --dark3: #3D3020;
    --mid: #6B5635;
    --text-light: #D4C4A0;
    --text-muted: #8B7355;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--dark);
    color: var(--cream);
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 1.2rem 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: background 0.4s;
  }
  nav.scrolled {
    background: rgba(26, 18, 8, 0.96);
    border-bottom: 1px solid rgba(201, 168, 76, 0.2);
    backdrop-filter: blur(12px);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--gold);
    letter-spacing: 0.05em;
    text-decoration: none;
  }
  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }
  .nav-links a {
    color: var(--text-light);
    text-decoration: none;
    font-size: 0.85rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    font-weight: 400;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--gold); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: relative;
    padding: 2rem;
    background:
      radial-gradient(ellipse at 50% 60%, rgba(201,168,76,0.08) 0%, transparent 60%),
      linear-gradient(180deg, #1A1208 0%, #2C1A05 50%, #1A1208 100%);
    overflow: hidden;
  }
  .hero-bg-pattern {
    position: absolute;
    inset: 0;
    opacity: 0.04;
    background-image: repeating-linear-gradient(
      45deg,
      var(--gold) 0px, var(--gold) 1px,
      transparent 1px, transparent 40px
    ),
    repeating-linear-gradient(
      -45deg,
      var(--gold) 0px, var(--gold) 1px,
      transparent 1px, transparent 40px
    );
  }
  .hero-line {
    position: absolute;
    width: 1px;
    height: 120px;
    background: linear-gradient(to bottom, transparent, var(--gold), transparent);
    top: 50%;
    transform: translateY(-50%);
  }
  .hero-line-left { left: 6%; }
  .hero-line-right { right: 6%; }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.7rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    border: 1px solid rgba(201,168,76,0.35);
    padding: 0.5rem 1.4rem;
    border-radius: 2px;
    margin-bottom: 2.5rem;
    animation: fadeIn 1s ease forwards;
  }
  .hero-badge::before, .hero-badge::after {
    content: '';
    width: 20px;
    height: 1px;
    background: var(--gold);
    opacity: 0.6;
  }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(4rem, 10vw, 8rem);
    font-weight: 900;
    line-height: 0.95;
    letter-spacing: -0.01em;
    margin-bottom: 0.5rem;
    animation: slideUp 1s ease 0.2s both;
  }
  .hero h1 .italic {
    font-style: italic;
    color: var(--gold);
    display: block;
  }
  .hero-subtitle {
    font-size: 0.8rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-top: 1.5rem;
    margin-bottom: 3rem;
    animation: slideUp 1s ease 0.4s both;
  }
  .hero-cta {
    display: inline-flex;
    align-items: center;
    gap: 0.8rem;
    background: var(--gold);
    color: var(--dark);
    padding: 1rem 2.5rem;
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    text-decoration: none;
    transition: all 0.3s;
    animation: slideUp 1s ease 0.6s both;
  }
  .hero-cta:hover {
    background: var(--gold-light);
    transform: translateY(-2px);
  }
  .hero-scroll {
    position: absolute;
    bottom: 2.5rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    color: var(--text-muted);
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    animation: pulse 2s ease infinite;
  }
  .hero-scroll span {
    width: 1px;
    height: 50px;
    background: linear-gradient(to bottom, var(--gold), transparent);
  }

  /* DIVIDER */
  .divider {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin: 0 auto;
    max-width: 300px;
    padding: 4rem 0;
  }
  .divider::before, .divider::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, transparent, var(--gold-dark));
  }
  .divider::after {
    background: linear-gradient(to left, transparent, var(--gold-dark));
  }
  .divider-diamond {
    width: 8px;
    height: 8px;
    background: var(--gold);
    transform: rotate(45deg);
  }

  /* SECTIONS */
  section {
    padding: 6rem 2rem;
  }
  .container {
    max-width: 1100px;
    margin: 0 auto;
  }
  .section-label {
    font-size: 0.7rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.2rem, 5vw, 3.5rem);
    font-weight: 700;
    line-height: 1.1;
    margin-bottom: 1.5rem;
  }
  .section-title em {
    font-style: italic;
    color: var(--gold);
  }

  /* SOBRE */
  .sobre-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: center;
  }
  .sobre-text p {
    color: var(--text-light);
    line-height: 1.9;
    font-size: 1rem;
    font-weight: 300;
    margin-bottom: 1.2rem;
  }
  .sobre-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    margin-top: 3rem;
  }
  .stat {
    border-top: 1px solid rgba(201,168,76,0.25);
    padding-top: 1.2rem;
  }
  .stat-number {
    font-family: 'Playfair Display', serif;
    font-size: 2.8rem;
    font-weight: 900;
    color: var(--gold);
    line-height: 1;
    margin-bottom: 0.3rem;
  }
  .stat-label {
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--text-muted);
  }
  .sobre-visual {
    position: relative;
  }
  .sobre-card {
    background: var(--dark2);
    border: 1px solid rgba(201,168,76,0.15);
    padding: 3rem;
    position: relative;
  }
  .sobre-card::before {
    content: '';
    position: absolute;
    top: -1px; left: 2rem;
    width: 4rem;
    height: 3px;
    background: var(--gold);
  }
  .sobre-card-quote {
    font-family: 'Playfair Display', serif;
    font-size: 1.15rem;
    font-style: italic;
    color: var(--cream);
    line-height: 1.8;
    margin-bottom: 2rem;
  }
  .sobre-card-author {
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
  }
  .rating-row {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    margin-top: 1.5rem;
  }
  .stars {
    color: var(--gold);
    font-size: 1.1rem;
    letter-spacing: 0.1em;
  }
  .rating-text {
    font-size: 0.8rem;
    color: var(--text-muted);
  }

  /* AMBIENTE */
  .ambiente {
    background: var(--dark2);
    border-top: 1px solid rgba(201,168,76,0.08);
    border-bottom: 1px solid rgba(201,168,76,0.08);
  }
  .ambiente-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    margin-top: 4rem;
  }
  .ambiente-item {
    background: var(--dark3);
    padding: 2.5rem 2rem;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
  }
  .ambiente-item:hover { background: rgba(201,168,76,0.06); }
  .ambiente-item::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--gold);
    transform: scaleX(0);
    transition: transform 0.3s;
    transform-origin: left;
  }
  .ambiente-item:hover::after { transform: scaleX(1); }
  .ambiente-icon {
    font-size: 2rem;
    margin-bottom: 1.2rem;
    display: block;
    color: var(--gold);
  }
  .ambiente-item h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.15rem;
    font-weight: 700;
    margin-bottom: 0.8rem;
  }
  .ambiente-item p {
    font-size: 0.88rem;
    color: var(--text-light);
    line-height: 1.7;
    font-weight: 300;
  }

  /* LOCALIZAÇÃO */
  .localizacao-grid {
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: 5rem;
    align-items: start;
  }
  .info-block {
    margin-bottom: 2.5rem;
  }
  .info-block-label {
    font-size: 0.68rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.6rem;
  }
  .info-block-value {
    font-size: 1rem;
    color: var(--cream);
    line-height: 1.6;
    font-weight: 300;
  }
  .horarios-grid {
    display: grid;
    gap: 0.5rem;
  }
  .horario-row {
    display: flex;
    justify-content: space-between;
    padding: 0.7rem 0;
    border-bottom: 1px solid rgba(201,168,76,0.08);
    font-size: 0.88rem;
  }
  .horario-day { color: var(--text-muted); }
  .horario-time { color: var(--cream); font-weight: 400; }
  .map-embed {
    border: 1px solid rgba(201,168,76,0.15);
    overflow: hidden;
    height: 380px;
  }
  .map-embed iframe {
    width: 100%;
    height: 100%;
    border: 0;
    filter: grayscale(0.3) sepia(0.15);
  }

  /* FOOTER */
  footer {
    background: #0E0A04;
    padding: 3rem 2rem;
    text-align: center;
    border-top: 1px solid rgba(201,168,76,0.12);
  }
  .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem;
    font-weight: 900;
    color: var(--gold);
    margin-bottom: 1rem;
  }
  .footer-sub {
    font-size: 0.75rem;
    color: var(--text-muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 2rem;
  }
  .footer-copy {
    font-size: 0.75rem;
    color: var(--mid);
  }
  .insta-link {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    color: var(--gold);
    text-decoration: none;
    font-size: 0.82rem;
    letter-spacing: 0.1em;
    border: 1px solid rgba(201,168,76,0.3);
    padding: 0.6rem 1.5rem;
    margin-bottom: 2.5rem;
    transition: all 0.2s;
  }
  .insta-link:hover {
    background: rgba(201,168,76,0.08);
    border-color: var(--gold);
  }

  /* ANIMATIONS */
  @keyframes fadeIn {
    from { opacity: 0; } to { opacity: 1; }
  }
  @keyframes slideUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulse {
    0%, 100% { opacity: 0.5; } 50% { opacity: 1; }
  }

  .reveal {
    opacity: 0;
    transform: translateY(25px);
    transition: opacity 0.8s ease, transform 0.8s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .sobre-grid,
    .localizacao-grid { grid-template-columns: 1fr; gap: 3rem; }
    .ambiente-grid { grid-template-columns: 1fr; gap: 2px; }
    section { padding: 4rem 1.5rem; }
    .hero-line { display: none; }
  }
</style>
</head>
<body>

<nav id="navbar">
  <a href="#" class="nav-logo">Bar Bolas</a>
  <ul class="nav-links">
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#ambiente">Ambiente</a></li>
    <li><a href="#localizacao">Localização</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg-pattern"></div>
  <div class="hero-line hero-line-left"></div>
  <div class="hero-line hero-line-right"></div>

  <div>
    <div class="hero-badge">Mongaguá — São Paulo</div>
    <h1>
      Bar
      <span class="italic">Bolas</span>
    </h1>
    <p class="hero-subtitle">O melhor bar da cidade · Avaliado 4,5 ★ no TripAdvisor</p>
    <a href="#sobre" class="hero-cta">Conheça o bar</a>
  </div>

  <div class="hero-scroll">
    <span></span>
    scroll
  </div>
</section>

<!-- SOBRE -->
<section id="sobre">
  <div class="container">
    <div class="sobre-grid">
      <div class="sobre-text reveal">
        <p class="section-label">Sobre nós</p>
        <h2 class="section-title">Um clássico em <em>Mongaguá</em></h2>
        <p>O Bar Bolas é o point favorito dos moradores e visitantes de Mongaguá. Com um ambiente descontraído e acolhedor, o bar se tornou referência na cidade como o lugar perfeito para reunir amigos, família e celebrar bons momentos.</p>
        <p>Localizado no coração da cidade, oferecemos um espaço único onde a tradição do bar brasileiro se encontra com o calor humano da costa paulista. Cerveja bem gelada, boa conversa e um atendimento que faz você querer voltar sempre.</p>

        <div class="sobre-stats">
          <div class="stat">
            <div class="stat-number">4,5</div>
            <div class="stat-label">Avaliação TripAdvisor</div>
          </div>
          <div class="stat">
            <div class="stat-number">#1</div>
            <div class="stat-label">Bar em Mongaguá</div>
          </div>
          <div class="stat">
            <div class="stat-number">24+</div>
            <div class="stat-label">Avaliações positivas</div>
          </div>
          <div class="stat">
            <div class="stat-number">100%</div>
            <div class="stat-label">Feito com amor</div>
          </div>
        </div>
      </div>

      <div class="sobre-visual reveal">
        <div class="sobre-card">
          <p class="sobre-card-quote">"Um lugar incrível para curtir com amigos e família. Ótimo ambiente, atendimento carinhoso e a melhor cerveja da região."</p>
          <div class="sobre-card-author">Cliente fiel — TripAdvisor</div>
          <div class="rating-row">
            <span class="stars">★★★★★</span>
            <span class="rating-text">Avaliação máxima</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- AMBIENTE -->
<section id="ambiente" class="ambiente">
  <div class="container">
    <div class="reveal">
      <p class="section-label">Experiência</p>
      <h2 class="section-title">Um bar feito para <em>momentos</em></h2>
    </div>

    <div class="ambiente-grid reveal">
      <div class="ambiente-item">
        <span class="ambiente-icon">🍺</span>
        <h3>Bebidas geladas</h3>
        <p>Cerveja sempre no ponto certo de temperatura. Drinks, petiscos e tudo que você precisa para um final de tarde perfeito.</p>
      </div>
      <div class="ambiente-item">
        <span class="ambiente-icon">🤝</span>
        <h3>Atendimento caloroso</h3>
        <p>Uma equipe que trata você como amigo de longa data. O Bar Bolas é conhecido pela simpatia e atenção de quem cuida do lugar.</p>
      </div>
      <div class="ambiente-item">
        <span class="ambiente-icon">🌊</span>
        <h3>Perto da praia</h3>
        <p>Estrategicamente localizado em Mongaguá, perfeito para quem vem curtir o litoral e quer um barzinho de verdade.</p>
      </div>
      <div class="ambiente-item">
        <span class="ambiente-icon">👨‍👩‍👧</span>
        <h3>Para todos</h3>
        <p>Ótimo para casais, famílias e grupos de amigos. Um ambiente acolhedor que recebe todo mundo com o mesmo sorriso.</p>
      </div>
      <div class="ambiente-item">
        <span class="ambiente-icon">🎶</span>
        <h3>Boa energia</h3>
        <p>Aquela vibração autêntica de bar brasileiro. Música, risadas e boas histórias fazem parte da atmosfera do lugar.</p>
      </div>
      <div class="ambiente-item">
        <span class="ambiente-icon">⭐</span>
        <h3>#1 em Mongaguá</h3>
        <p>Eleito o melhor bar e pub da cidade no TripAdvisor, com dezenas de avaliações positivas de clientes apaixonados.</p>
      </div>
    </div>
  </div>
</section>

<!-- LOCALIZAÇÃO -->
<section id="localizacao">
  <div class="container">
    <div class="localizacao-grid">
      <div>
        <div class="reveal">
          <p class="section-label">Onde estamos</p>
          <h2 class="section-title">Venha nos <em>visitar</em></h2>
        </div>

        <div class="info-block reveal">
          <p class="info-block-label">Endereço</p>
          <p class="info-block-value">Mongaguá, São Paulo<br>Litoral Paulista</p>
        </div>

        <div class="info-block reveal">
          <p class="info-block-label">Funcionamento</p>
          <div class="horarios-grid">
            <div class="horario-row">
              <span class="horario-day">Segunda a Quinta</span>
              <span class="horario-time">11h às 23h</span>
            </div>
            <div class="horario-row">
              <span class="horario-day">Sexta-feira</span>
              <span class="horario-time">11h às 00h</span>
            </div>
            <div class="horario-row">
              <span class="horario-day">Sábado</span>
              <span class="horario-time">11h às 00h</span>
            </div>
            <div class="horario-row">
              <span class="horario-day">Domingo</span>
              <span class="horario-time">11h às 22h</span>
            </div>
          </div>
        </div>

        <div class="info-block reveal">
          <p class="info-block-label">Redes sociais</p>
          <a href="https://www.instagram.com" target="_blank" class="insta-link">📸 @barbolas</a>
        </div>
      </div>

      <div class="reveal">
        <div class="map-embed">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3656.123!2d-46.6908359!3d-24.1274043!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce283d9a29b92d%3A0xf482d68217dc67b8!2sBar%20Bolas!5e0!3m2!1spt-BR!2sbr!4v1"
            allowfullscreen
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade">
          </iframe>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Bar Bolas</div>
  <p class="footer-sub">Mongaguá · São Paulo · Litoral Paulista</p>
  <br>
  <p class="footer-copy">© 2025 Bar Bolas — Todos os direitos reservados</p>
</footer>

<script>
  const nav = document.getElementById('navbar');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('scrolled', window.scrollY > 60);
  });

  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));
</script>

</body>
</html>
