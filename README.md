<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bar Bolas — Mongaguá</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400;1,600&family=Tenor+Sans&family=Jost:wght@200;300;400&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --ink:#0D0B08;--ink2:#1C1910;--ink3:#2A2620;
  --amber:#B8893A;--amber-l:#D4A855;--amber-d:#8A6420;
  --sand:#EDE4D0;--sand-l:#F7F2E8;--sand-d:#C8B99A;
  --fog:#6B6050;--white:#FDFAF4;
}
html{scroll-behavior:smooth}
body{background:var(--ink);color:var(--sand);font-family:'Jost',sans-serif;font-weight:300;cursor:none;overflow-x:hidden}
body::before{content:'';position:fixed;inset:0;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");opacity:.025;pointer-events:none;z-index:1000}
#cursor{position:fixed;width:8px;height:8px;background:var(--amber);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:width .3s,height .3s}
#cursor-ring{position:fixed;width:36px;height:36px;border:1px solid rgba(184,137,58,.35);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:width .3s,height .3s,border-color .3s}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:500;padding:2rem 4rem;display:flex;align-items:center;justify-content:space-between;transition:padding .5s,background .5s}
nav.compact{padding:1.2rem 4rem;background:rgba(13,11,8,.9);backdrop-filter:blur(20px);border-bottom:1px solid rgba(184,137,58,.1)}
.nav-logo{font-family:'Cormorant Garamond',serif;font-size:1.5rem;font-weight:600;color:var(--amber-l);letter-spacing:.06em;text-decoration:none}
.nav-menu{display:flex;gap:3rem;list-style:none}
.nav-menu a{font-family:'Tenor Sans',sans-serif;font-size:.65rem;letter-spacing:.22em;text-transform:uppercase;color:var(--sand-d);text-decoration:none;transition:color .25s;position:relative}
.nav-menu a::after{content:'';position:absolute;bottom:-3px;left:0;width:0;height:1px;background:var(--amber);transition:width .3s}
.nav-menu a:hover{color:var(--amber-l)}
.nav-menu a:hover::after{width:100%}
.nav-cta{font-family:'Tenor Sans',sans-serif;font-size:.65rem;letter-spacing:.2em;text-transform:uppercase;color:var(--ink);background:var(--amber);padding:.65rem 1.8rem;text-decoration:none;transition:background .25s}
.nav-cta:hover{background:var(--amber-l)}

/* HERO */
.hero{min-height:100vh;position:relative;overflow:hidden;display:grid;grid-template-columns:1fr 1fr;background:var(--ink)}
.hero-left{display:flex;flex-direction:column;justify-content:flex-end;padding:10rem 0 6rem 4rem;position:relative;z-index:2}
.hero-eyebrow{font-family:'Tenor Sans',sans-serif;font-size:.62rem;letter-spacing:.35em;text-transform:uppercase;color:var(--amber);margin-bottom:2.5rem;display:flex;align-items:center;gap:1rem}
.hero-eyebrow::before{content:'';width:40px;height:1px;background:var(--amber);opacity:.7}
.hero-h1{font-family:'Cormorant Garamond',serif;font-size:clamp(5rem,8.5vw,8.5rem);font-weight:300;line-height:.92;letter-spacing:-.02em;color:var(--white)}
.hero-h1 .line{display:block;overflow:hidden}
.hero-h1 .line span{display:block;animation:lineUp 1.2s cubic-bezier(.16,1,.3,1) both}
.hero-h1 .line:nth-child(1) span{animation-delay:.1s}
.hero-h1 .line:nth-child(2) span{animation-delay:.28s}
.hero-h1 .gold{color:var(--amber-l);font-style:italic}
.hero-desc{margin-top:2.5rem;max-width:360px;font-size:.92rem;line-height:1.9;color:var(--fog);animation:fadeUp 1s ease .8s both}
.hero-actions{margin-top:3rem;display:flex;align-items:center;gap:2.5rem;animation:fadeUp 1s ease 1s both}
.btn-primary{background:var(--amber);color:var(--ink);font-family:'Tenor Sans',sans-serif;font-size:.68rem;letter-spacing:.2em;text-transform:uppercase;padding:.95rem 2.5rem;text-decoration:none;display:inline-flex;align-items:center;gap:.9rem;position:relative;overflow:hidden;transition:transform .3s}
.btn-primary::after{content:'';position:absolute;inset:0;background:var(--amber-l);transform:translateX(-101%);transition:transform .45s cubic-bezier(.23,1,.32,1)}
.btn-primary:hover::after{transform:translateX(0)}
.btn-primary span,.btn-primary svg{position:relative;z-index:1}
.btn-primary svg{transition:transform .3s}
.btn-primary:hover svg{transform:translateX(4px)}
.btn-ghost{font-family:'Tenor Sans',sans-serif;font-size:.68rem;letter-spacing:.2em;text-transform:uppercase;color:var(--sand-d);text-decoration:none;display:inline-flex;align-items:center;gap:.7rem;transition:color .25s}
.btn-ghost:hover{color:var(--amber-l)}
.hero-right{position:relative;overflow:hidden;background:linear-gradient(135deg,#1A1206 0%,#2E1E08 60%,#1C1408 100%)}
.geo-wrap{position:absolute;inset:0;display:flex;align-items:center;justify-content:center}
.geo-ring{position:absolute;border-radius:50%;border:1px solid rgba(184,137,58,.1)}
.geo-ring:nth-child(1){width:500px;height:500px;animation:slowSpin 40s linear infinite}
.geo-ring:nth-child(2){width:340px;height:340px;animation:slowSpin 28s linear infinite reverse;border-color:rgba(184,137,58,.18)}
.geo-ring:nth-child(3){width:180px;height:180px;animation:slowSpin 18s linear infinite;border-color:rgba(184,137,58,.3)}
.hero-overlay{position:absolute;inset:0;background:linear-gradient(to right,var(--ink) 0%,transparent 100%);z-index:1}
.hero-badge{position:absolute;bottom:3.5rem;right:3.5rem;z-index:3;width:120px;height:120px;border-radius:50%;background:var(--amber);display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;animation:rotateBadge 22s linear infinite}
.badge-inner{display:flex;flex-direction:column;align-items:center;animation:rotateBadge 22s linear infinite reverse}
.badge-n{font-family:'Cormorant Garamond',serif;font-size:1.9rem;font-weight:600;color:var(--ink);line-height:1}
.badge-n sup{font-size:.9rem}
.badge-l{font-family:'Tenor Sans',sans-serif;font-size:.48rem;letter-spacing:.15em;text-transform:uppercase;color:var(--ink);opacity:.75;margin-top:.25rem;line-height:1.4}
.hero-scroll{position:absolute;bottom:3rem;left:4rem;z-index:5;display:flex;flex-direction:column;align-items:center;gap:.8rem}
.scroll-line{width:1px;height:55px;background:linear-gradient(to bottom,var(--amber),transparent);animation:scrollP 2.5s ease infinite}
.scroll-txt{font-family:'Tenor Sans',sans-serif;font-size:.55rem;letter-spacing:.28em;text-transform:uppercase;color:var(--fog);writing-mode:vertical-rl}

/* TICKER */
.ticker{overflow:hidden;border-top:1px solid rgba(184,137,58,.13);border-bottom:1px solid rgba(184,137,58,.13);background:var(--ink2);padding:.85rem 0}
.ticker-track{display:flex;white-space:nowrap;animation:tickerAnim 28s linear infinite}
.ticker-item{display:inline-flex;align-items:center;gap:1.5rem;padding:0 3rem;font-family:'Tenor Sans',sans-serif;font-size:.62rem;letter-spacing:.22em;text-transform:uppercase;color:var(--fog)}
.tick-dot{width:4px;height:4px;background:var(--amber);border-radius:50%;flex-shrink:0}

/* SOBRE */
.sobre{padding:10rem 4rem;display:grid;grid-template-columns:1fr 2fr;gap:8rem;align-items:start;position:relative}
.sobre::before{content:'';position:absolute;top:0;left:4rem;right:4rem;height:1px;background:linear-gradient(to right,var(--amber-d),transparent)}
.sobre-num{font-family:'Cormorant Garamond',serif;font-size:8rem;font-weight:300;color:rgba(184,137,58,.09);line-height:1;position:sticky;top:8rem}
.stag{font-family:'Tenor Sans',sans-serif;font-size:.62rem;letter-spacing:.32em;text-transform:uppercase;color:var(--amber);margin-bottom:1.8rem;display:flex;align-items:center;gap:1.2rem}
.stag::before{content:'';width:28px;height:1px;background:var(--amber)}
.sobre-title{font-family:'Cormorant Garamond',serif;font-size:clamp(2.6rem,4vw,4.2rem);font-weight:300;line-height:1.05;color:var(--white);margin-bottom:2.5rem}
.sobre-title em{font-style:italic;color:var(--amber-l)}
.sobre-body p{font-size:.96rem;line-height:2;color:var(--fog);font-weight:300;margin-bottom:1.4rem}
.metrics{display:grid;grid-template-columns:repeat(3,1fr);gap:0;margin-top:5rem;border:1px solid rgba(184,137,58,.13)}
.metric{padding:2.5rem 2rem;border-right:1px solid rgba(184,137,58,.13);transition:background .3s}
.metric:last-child{border-right:none}
.metric:hover{background:rgba(184,137,58,.04)}
.metric-val{font-family:'Cormorant Garamond',serif;font-size:3rem;font-weight:300;color:var(--amber-l);line-height:1;margin-bottom:.6rem}
.metric-val sup{font-size:1.1rem}
.metric-lbl{font-family:'Tenor Sans',sans-serif;font-size:.62rem;letter-spacing:.14em;text-transform:uppercase;color:var(--fog)}

/* CARDS */
.cards-section{background:var(--ink2);padding:8rem 4rem}
.cards-head{display:flex;align-items:flex-end;justify-content:space-between;margin-bottom:5rem;padding-bottom:2rem;border-bottom:1px solid rgba(184,137,58,.1)}
.cards-title{font-family:'Cormorant Garamond',serif;font-size:clamp(2.4rem,3.8vw,3.8rem);font-weight:300;color:var(--white);line-height:1.05}
.cards-title em{font-style:italic;color:var(--amber-l)}
.cards-sub{font-size:.82rem;color:var(--fog);max-width:200px;line-height:1.7;text-align:right}
.cgrid{display:grid;grid-template-columns:repeat(3,1fr);gap:2px}
.ccard{background:var(--ink3);padding:3rem 2.5rem;position:relative;overflow:hidden;transition:background .4s;border:1px solid rgba(184,137,58,.05)}
.ccard::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:var(--amber);transform:scaleX(0);transform-origin:left;transition:transform .5s cubic-bezier(.23,1,.32,1)}
.ccard:hover{background:rgba(42,38,32,.95)}
.ccard:hover::after{transform:scaleX(1)}
.ccard-idx{position:absolute;top:2rem;right:2rem;font-family:'Cormorant Garamond',serif;font-size:2.8rem;font-weight:300;color:rgba(184,137,58,.09);line-height:1}
.ccard-icon{font-size:2rem;margin-bottom:1.8rem;display:block;transition:transform .3s}
.ccard:hover .ccard-icon{transform:scale(1.08)}
.ccard h3{font-family:'Cormorant Garamond',serif;font-size:1.45rem;font-weight:600;color:var(--sand);margin-bottom:.9rem;line-height:1.2}
.ccard p{font-size:.86rem;line-height:1.88;color:var(--fog);font-weight:300}

/* REVIEW */
.review{padding:9rem 4rem;position:relative;overflow:hidden;text-align:center}
.review::before{content:'\201C';position:absolute;top:-4rem;left:1rem;font-family:'Cormorant Garamond',serif;font-size:28rem;font-weight:600;color:rgba(184,137,58,.035);line-height:1;pointer-events:none}
.review-inner{max-width:820px;margin:0 auto;position:relative;z-index:1}
.review-stars{display:flex;justify-content:center;gap:.35rem;margin-bottom:2.5rem}
.review-stars span{color:var(--amber);font-size:1.1rem}
.review-quote{font-family:'Cormorant Garamond',serif;font-size:clamp(1.55rem,3.2vw,2.5rem);font-weight:300;font-style:italic;color:var(--white);line-height:1.5;margin-bottom:3rem}
.review-byline{}
.review-name{font-family:'Tenor Sans',sans-serif;font-size:.65rem;letter-spacing:.25em;text-transform:uppercase;color:var(--amber);margin-bottom:.4rem}
.review-source{font-size:.78rem;color:var(--fog)}
.review-sep{display:flex;align-items:center;gap:2rem;justify-content:center;margin:5rem 0}
.sep-line{flex:1;max-width:100px;height:1px;background:rgba(184,137,58,.18)}
.sep-diamond{width:7px;height:7px;background:var(--amber);transform:rotate(45deg)}
.review-nums{display:flex;justify-content:center;gap:5rem;flex-wrap:wrap}
.rn-val{font-family:'Cormorant Garamond',serif;font-size:2.4rem;font-weight:300;color:var(--amber-l);line-height:1;margin-bottom:.4rem}
.rn-lbl{font-family:'Tenor Sans',sans-serif;font-size:.58rem;letter-spacing:.2em;text-transform:uppercase;color:var(--fog)}

/* LOCAL */
.local{padding:8rem 4rem;background:var(--ink2);position:relative}
.local::before{content:'';position:absolute;top:0;left:4rem;right:4rem;height:1px;background:linear-gradient(to right,var(--amber-d),transparent)}
.local-grid{display:grid;grid-template-columns:1fr 1.5fr;gap:7rem;align-items:start}
.local-title{font-family:'Cormorant Garamond',serif;font-size:clamp(2.4rem,3.8vw,3.8rem);font-weight:300;color:var(--white);line-height:1.05;margin-bottom:3.5rem}
.local-title em{font-style:italic;color:var(--amber-l)}
.irow{display:flex;gap:1.5rem;padding:1.6rem 0;border-bottom:1px solid rgba(184,137,58,.09)}
.irow-icon{width:34px;height:34px;flex-shrink:0;border:1px solid rgba(184,137,58,.22);display:flex;align-items:center;justify-content:center;margin-top:2px}
.irow-icon svg{width:15px;height:15px;stroke:var(--amber);fill:none;stroke-width:1.5}
.irow-lbl{font-family:'Tenor Sans',sans-serif;font-size:.6rem;letter-spacing:.22em;text-transform:uppercase;color:var(--amber);margin-bottom:.5rem}
.irow-val{font-size:.9rem;line-height:1.7;color:var(--sand-d);font-weight:300}
.hor-table{width:100%}
.hor-table tr{border-bottom:1px solid rgba(184,137,58,.07)}
.hor-table td{padding:.85rem 0;font-size:.86rem;font-weight:300}
.hor-table td:first-child{color:var(--fog)}
.hor-table td:last-child{color:var(--sand);text-align:right}
.map-wrap{border:1px solid rgba(184,137,58,.14);overflow:hidden;height:460px;position:relative}
.map-wrap::before{content:'LOCALIZAÇÃO';position:absolute;top:1rem;left:50%;transform:translateX(-50%);font-family:'Tenor Sans',sans-serif;font-size:.52rem;letter-spacing:.3em;color:var(--amber);z-index:2;background:var(--ink2);padding:.3rem .8rem}
.map-wrap iframe{width:100%;height:100%;border:0;filter:saturate(.45) contrast(1.1) brightness(.75) sepia(.25);display:block}

/* FOOTER */
footer{background:var(--ink);border-top:1px solid rgba(184,137,58,.1);padding:5rem 4rem 3rem}
.footer-top{display:grid;grid-template-columns:1.6fr 1fr 1fr;gap:5rem;padding-bottom:4rem;border-bottom:1px solid rgba(184,137,58,.08);margin-bottom:3rem}
.f-logo{font-family:'Cormorant Garamond',serif;font-size:2.4rem;font-weight:600;color:var(--amber-l);line-height:1;margin-bottom:.4rem}
.f-sub{font-family:'Tenor Sans',sans-serif;font-size:.58rem;letter-spacing:.28em;text-transform:uppercase;color:var(--fog);margin-bottom:1.5rem}
.f-desc{font-size:.86rem;line-height:1.85;color:var(--fog);font-weight:300;max-width:270px}
.f-col-title{font-family:'Tenor Sans',sans-serif;font-size:.6rem;letter-spacing:.22em;text-transform:uppercase;color:var(--amber);margin-bottom:1.6rem}
.f-links{display:flex;flex-direction:column;gap:.85rem}
.f-links a{font-size:.86rem;color:var(--fog);text-decoration:none;transition:color .25s;font-weight:300}
.f-links a:hover{color:var(--amber-l)}
.footer-bottom{display:flex;justify-content:space-between;align-items:center}
.f-copy{font-size:.73rem;color:var(--fog)}
.f-trip{font-size:.73rem;color:var(--fog);display:flex;gap:.5rem;align-items:center}
.f-trip strong{color:var(--amber)}

/* ANIMATIONS */
@keyframes lineUp{from{transform:translateY(110%)}to{transform:translateY(0)}}
@keyframes fadeUp{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
@keyframes scrollP{0%,100%{opacity:.3}50%{opacity:1}}
@keyframes slowSpin{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
@keyframes rotateBadge{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
@keyframes tickerAnim{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.reveal{opacity:0;transform:translateY(28px);transition:opacity .9s cubic-bezier(.16,1,.3,1),transform .9s cubic-bezier(.16,1,.3,1)}
.reveal.in{opacity:1;transform:none}
.d1{transition-delay:.1s}.d2{transition-delay:.2s}.d3{transition-delay:.3s}.d4{transition-delay:.4s}

@media(max-width:900px){
  nav{padding:1.5rem 1.5rem}nav.compact{padding:1rem 1.5rem}
  .nav-menu,.nav-cta{display:none}
  .hero{grid-template-columns:1fr}.hero-right{display:none}
  .hero-left{padding:8rem 1.5rem 5rem}
  .sobre,.cards-section,.review,.local{padding:5rem 1.5rem}
  .sobre{grid-template-columns:1fr;gap:3rem}.sobre-num{display:none}
  .metrics{grid-template-columns:1fr 1fr}.metrics .metric:nth-child(2){border-right:none}.metrics .metric:nth-child(3){border-top:1px solid rgba(184,137,58,.13);grid-column:1/-1}
  .cards-head{flex-direction:column;align-items:flex-start;gap:1.5rem}.cards-sub{text-align:left}
  .cgrid{grid-template-columns:1fr}
  .local-grid{grid-template-columns:1fr;gap:4rem}
  .footer-top{grid-template-columns:1fr;gap:3rem}
  footer{padding:4rem 1.5rem 2.5rem}
  .footer-bottom{flex-direction:column;gap:1rem;text-align:center}
}
</style>
</head>
<body>
<div id="cursor"></div>
<div id="cursor-ring"></div>

<nav id="nav">
  <a href="#" class="nav-logo">Bar Bolas</a>
  <ul class="nav-menu">
    <li><a href="#sobre">Nossa História</a></li>
    <li><a href="#cards">Experiência</a></li>
    <li><a href="#local">Visitar</a></li>
  </ul>
  <a href="#local" class="nav-cta">Como chegar</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-eyebrow">Mongaguá · Litoral Paulista · O bar da cidade</div>
    <h1 class="hero-h1">
      <span class="line"><span>Bar</span></span>
      <span class="line"><span class="gold">Bolas</span></span>
    </h1>
    <p class="hero-desc">O ponto de encontro mais querido de Mongaguá. Onde a cerveja é sempre gelada, o ambiente acolhe a todos e cada visita vira memória.</p>
    <div class="hero-actions">
      <a href="#sobre" class="btn-primary">
        <span>Conheça o bar</span>
        <svg width="15" height="15" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M5 12h14M13 6l6 6-6 6"/></svg>
      </a>
      <a href="#local" class="btn-ghost">
        <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
        Ver localização
      </a>
    </div>
  </div>
  <div class="hero-right">
    <div class="geo-wrap">
      <div class="geo-ring"></div>
      <div class="geo-ring"></div>
      <div class="geo-ring"></div>
    </div>
    <div class="hero-overlay"></div>
    <div class="hero-badge">
      <div class="badge-inner">
        <div class="badge-n">4,5<sup>★</sup></div>
        <div class="badge-l">#1 Bar<br>Mongaguá</div>
      </div>
    </div>
  </div>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <div class="scroll-txt">Scroll</div>
  </div>
</section>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-track">
    <span class="ticker-item"><span class="tick-dot"></span>Cerveja gelada</span>
    <span class="ticker-item"><span class="tick-dot"></span>Ambiente acolhedor</span>
    <span class="ticker-item"><span class="tick-dot"></span>#1 em Mongaguá</span>
    <span class="ticker-item"><span class="tick-dot"></span>4,5 estrelas TripAdvisor</span>
    <span class="ticker-item"><span class="tick-dot"></span>Litoral Paulista</span>
    <span class="ticker-item"><span class="tick-dot"></span>Tradição e sabor</span>
    <span class="ticker-item"><span class="tick-dot"></span>Petiscos irresistíveis</span>
    <span class="ticker-item"><span class="tick-dot"></span>Para toda a família</span>
    <span class="ticker-item"><span class="tick-dot"></span>Cerveja gelada</span>
    <span class="ticker-item"><span class="tick-dot"></span>Ambiente acolhedor</span>
    <span class="ticker-item"><span class="tick-dot"></span>#1 em Mongaguá</span>
    <span class="ticker-item"><span class="tick-dot"></span>4,5 estrelas TripAdvisor</span>
    <span class="ticker-item"><span class="tick-dot"></span>Litoral Paulista</span>
    <span class="ticker-item"><span class="tick-dot"></span>Tradição e sabor</span>
    <span class="ticker-item"><span class="tick-dot"></span>Petiscos irresistíveis</span>
    <span class="ticker-item"><span class="tick-dot"></span>Para toda a família</span>
  </div>
</div>

<!-- SOBRE -->
<section class="sobre" id="sobre">
  <div class="sobre-num">01</div>
  <div>
    <div class="stag reveal">Nossa identidade</div>
    <h2 class="sobre-title reveal d1">Um clássico nascido<br>à beira do <em>litoral</em></h2>
    <div class="sobre-body reveal d2">
      <p>O Bar Bolas é mais do que um ponto de encontro — é uma instituição de Mongaguá. Com ambiente descontraído e genuinamente acolhedor, tornou-se referência na cidade como o lugar perfeito para reunir amigos, família e celebrar bons momentos.</p>
      <p>Localizado no coração de Mongaguá, oferecemos um espaço único onde a tradição do bar brasileiro se encontra com o calor humano da costa paulista. Cerveja bem gelada, boa conversa e um atendimento que faz você querer voltar sempre.</p>
    </div>
    <div class="metrics reveal d3">
      <div class="metric">
        <div class="metric-val">4,5<sup>★</sup></div>
        <div class="metric-lbl">TripAdvisor</div>
      </div>
      <div class="metric">
        <div class="metric-val">#1</div>
        <div class="metric-lbl">Bar em Mongaguá</div>
      </div>
      <div class="metric">
        <div class="metric-val">24+</div>
        <div class="metric-lbl">Avaliações positivas</div>
      </div>
    </div>
  </div>
</section>

<!-- CARDS -->
<section class="cards-section" id="cards">
  <div class="cards-head reveal">
    <div>
      <div class="stag">Experiência</div>
      <h2 class="cards-title">O que torna o Bar Bolas<br><em>especial</em></h2>
    </div>
    <p class="cards-sub">Cada detalhe pensado para que você volte sempre.</p>
  </div>
  <div class="cgrid">
    <div class="ccard reveal">
      <span class="ccard-idx">01</span>
      <span class="ccard-icon">🍺</span>
      <h3>Cerveja no ponto</h3>
      <p>Sempre no grau exato de temperatura. Uma boa cerveja gelada é o começo de toda boa história que acontece aqui.</p>
    </div>
    <div class="ccard reveal d1">
      <span class="ccard-idx">02</span>
      <span class="ccard-icon">🤝</span>
      <h3>Gente que recebe bem</h3>
      <p>Um atendimento que parece hospitalidade de verdade. Todo cliente é tratado como alguém especial, sempre.</p>
    </div>
    <div class="ccard reveal d2">
      <span class="ccard-idx">03</span>
      <span class="ccard-icon">🌊</span>
      <h3>Perto da praia</h3>
      <p>Mongaguá, litoral paulista. Perfeito para quem vem curtir o mar e quer um barzinho autêntico de verdade.</p>
    </div>
    <div class="ccard reveal d3">
      <span class="ccard-idx">04</span>
      <span class="ccard-icon">👨‍👩‍👧</span>
      <h3>Para toda a família</h3>
      <p>Casais, grupos de amigos, famílias. O ambiente acolhedor abraça qualquer ocasião com o mesmo carinho.</p>
    </div>
    <div class="ccard reveal d4">
      <span class="ccard-idx">05</span>
      <span class="ccard-icon">🎵</span>
      <h3>Boa energia sempre</h3>
      <p>Aquela vibração autêntica de bar brasileiro. A combinação rara de tranquilidade e animação no lugar certo.</p>
    </div>
    <div class="ccard reveal d4">
      <span class="ccard-idx">06</span>
      <span class="ccard-icon">⭐</span>
      <h3>Referência reconhecida</h3>
      <p>O melhor bar e pub de Mongaguá segundo o TripAdvisor — eleito pelos próprios clientes que viveram a experiência.</p>
    </div>
  </div>
</section>

<!-- REVIEW -->
<section class="review">
  <div class="review-inner reveal">
    <div class="review-stars">
      <span>★</span><span>★</span><span>★</span><span>★</span><span>★</span>
    </div>
    <p class="review-quote">"Um lugar incrível para curtir com amigos e família. Ambiente maravilhoso, atendimento atencioso e exatamente o clima que você espera de um bar de litoral."</p>
    <div class="review-name">Cliente fiel</div>
    <div class="review-source">Avaliação verificada · TripAdvisor · Mongaguá</div>
    <div class="review-sep">
      <div class="sep-line"></div>
      <div class="sep-diamond"></div>
      <div class="sep-line"></div>
    </div>
    <div class="review-nums">
      <div>
        <div class="rn-val">4,5★</div>
        <div class="rn-lbl">TripAdvisor</div>
      </div>
      <div>
        <div class="rn-val">#1</div>
        <div class="rn-lbl">Bares — Mongaguá</div>
      </div>
      <div>
        <div class="rn-val">24+</div>
        <div class="rn-lbl">Avaliações positivas</div>
      </div>
    </div>
  </div>
</section>

<!-- LOCAL -->
<section class="local" id="local">
  <div class="local-grid">
    <div>
      <div class="stag reveal">Visitar</div>
      <h2 class="local-title reveal d1">Venha tomar<br>uma <em>conosco</em></h2>
      <div class="irow reveal d2">
        <div class="irow-icon">
          <svg viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
        </div>
        <div>
          <div class="irow-lbl">Endereço</div>
          <div class="irow-val">Mongaguá, São Paulo<br>Litoral Paulista</div>
        </div>
      </div>
      <div class="irow reveal d3">
        <div class="irow-icon">
          <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
        </div>
        <div>
          <div class="irow-lbl">Horários</div>
          <div class="irow-val">
            <table class="hor-table">
              <tr><td>Segunda a Quinta</td><td>11h – 23h</td></tr>
              <tr><td>Sexta-feira</td><td>11h – 00h</td></tr>
              <tr><td>Sábado</td><td>11h – 00h</td></tr>
              <tr><td>Domingo</td><td>11h – 22h</td></tr>
            </table>
          </div>
        </div>
      </div>
      <div class="irow reveal d4">
        <div class="irow-icon">
          <svg viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
        </div>
        <div>
          <div class="irow-lbl">Avaliações</div>
          <div class="irow-val">
            <a href="https://www.tripadvisor.com/Restaurant_Review-g1749025-d5673261-Reviews-Bar_Bolas-Mongagua_State_of_Sao_Paulo.html" target="_blank" rel="noopener" style="color:var(--amber);text-decoration:none;display:inline-flex;align-items:center;gap:.5rem;font-size:.88rem">
              Ver no TripAdvisor
              <svg width="11" height="11" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15,3 21,3 21,9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="map-wrap reveal d2">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3656.8!2d-46.6908359!3d-24.1274043!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce283d9a29b92d%3A0xf482d68217dc67b8!2sBar%20Bolas!5e0!3m2!1spt-BR!2sbr!4v1" allowfullscreen loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div>
      <div class="f-logo">Bar Bolas</div>
      <div class="f-sub">Mongaguá · São Paulo</div>
      <p class="f-desc">O bar mais querido do litoral paulista. Venha fazer parte da nossa história e criar memórias que ficam.</p>
    </div>
    <div>
      <div class="f-col-title">Navegação</div>
      <div class="f-links">
        <a href="#sobre">Nossa História</a>
        <a href="#cards">Experiência</a>
        <a href="#local">Localização</a>
        <a href="#local">Horários</a>
      </div>
    </div>
    <div>
      <div class="f-col-title">Reconhecimentos</div>
      <div class="f-links">
        <a href="https://www.tripadvisor.com/Restaurant_Review-g1749025-d5673261-Reviews-Bar_Bolas-Mongagua_State_of_Sao_Paulo.html" target="_blank" rel="noopener">#1 Bar em Mongaguá</a>
        <a href="https://www.tripadvisor.com/Restaurant_Review-g1749025-d5673261-Reviews-Bar_Bolas-Mongagua_State_of_Sao_Paulo.html" target="_blank" rel="noopener">4,5 ★ no TripAdvisor</a>
        <a href="https://www.tripadvisor.com/Restaurant_Review-g1749025-d5673261-Reviews-Bar_Bolas-Mongagua_State_of_Sao_Paulo.html" target="_blank" rel="noopener">24+ avaliações</a>
      </div>
    </div>
  </div>
  <div class="footer-bottom">
    <p class="f-copy">© 2025 Bar Bolas · Mongaguá, São Paulo · Todos os direitos reservados</p>
    <div class="f-trip"><strong>4,5 ★</strong> no TripAdvisor</div>
  </div>
</footer>

<script>
const cursor=document.getElementById('cursor');
const ring=document.getElementById('cursor-ring');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{
  mx=e.clientX;my=e.clientY;
  cursor.style.left=mx+'px';cursor.style.top=my+'px';
});
(function tick(){
  rx+=(mx-rx)*.12;ry+=(my-ry)*.12;
  ring.style.left=rx+'px';ring.style.top=ry+'px';
  requestAnimationFrame(tick);
})();
document.querySelectorAll('a,button').forEach(el=>{
  el.addEventListener('mouseenter',()=>{
    cursor.style.width='3px';cursor.style.height='3px';
    ring.style.width='52px';ring.style.height='52px';
    ring.style.borderColor='rgba(184,137,58,.7)';
  });
  el.addEventListener('mouseleave',()=>{
    cursor.style.width='8px';cursor.style.height='8px';
    ring.style.width='36px';ring.style.height='36px';
    ring.style.borderColor='rgba(184,137,58,.35)';
  });
});
const nav=document.getElementById('nav');
window.addEventListener('scroll',()=>nav.classList.toggle('compact',scrollY>80));
const revs=document.querySelectorAll('.reveal');
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('in');obs.unobserve(e.target)}});
},{threshold:.1});
revs.forEach(el=>obs.observe(el));
</script>
</body>
</html>
