
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NexaAI — Agents IA & Formations</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --noir: #0a0a0f;
    --blanc: #f4f2ed;
    --accent: #b8f458;
    --accent2: #58e4f4;
    --gris1: #1a1a24;
    --gris2: #2a2a38;
    --gris3: #8888a0;
    --radius: 16px;
  }
  html { scroll-behavior: smooth; }
  body {
    background: var(--noir);
    color: var(--blanc);
    font-family: 'DM Sans', sans-serif;
    font-size: 16px;
    line-height: 1.65;
    overflow-x: hidden;
  }
  h1,h2,h3,h4 { font-family: 'Syne', sans-serif; }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.2rem 4rem;
    background: rgba(10,10,15,0.88);
    backdrop-filter: blur(16px);
    border-bottom: 0.5px solid rgba(255,255,255,0.08);
  }
  .logo { font-family:'Syne',sans-serif; font-size:1.4rem; font-weight:800; letter-spacing:-0.02em; color:var(--blanc); text-decoration:none; }
  .logo span { color:var(--accent); }
  .nav-links { display:flex; gap:2.5rem; list-style:none; }
  .nav-links a { color:var(--gris3); font-size:0.9rem; font-weight:500; text-decoration:none; transition:color .2s; }
  .nav-links a:hover { color:var(--blanc); }
  .nav-cta { background:var(--accent); color:var(--noir); font-family:'Syne',sans-serif; font-weight:700; font-size:0.85rem; padding:0.6rem 1.4rem; border-radius:100px; border:none; cursor:pointer; text-decoration:none; transition:opacity .2s; }
  .nav-cta:hover { opacity:.85; }

  /* ── HERO ── */
  .hero { min-height:100vh; display:flex; flex-direction:column; align-items:center; justify-content:center; text-align:center; padding:8rem 2rem 4rem; position:relative; overflow:hidden; }
  .hero-bg { position:absolute; inset:0; z-index:0; background:radial-gradient(ellipse 80% 60% at 50% 0%, rgba(184,244,88,.08) 0%, transparent 70%), radial-gradient(ellipse 60% 50% at 80% 80%, rgba(88,228,244,.06) 0%, transparent 60%); }
  .hero-grid { position:absolute; inset:0; z-index:0; opacity:.03; background-image:linear-gradient(rgba(255,255,255,.5) 1px,transparent 1px),linear-gradient(90deg,rgba(255,255,255,.5) 1px,transparent 1px); background-size:60px 60px; }
  .hero-badge { display:inline-flex; align-items:center; gap:8px; background:rgba(184,244,88,.1); border:0.5px solid rgba(184,244,88,.3); color:var(--accent); font-size:.8rem; font-weight:500; padding:.4rem 1rem; border-radius:100px; margin-bottom:2rem; position:relative; z-index:1; animation:fadeUp .6s ease both; }
  .dot { width:6px; height:6px; border-radius:50%; background:var(--accent); animation:pulse 2s infinite; }
  @keyframes pulse{0%,100%{opacity:1}50%{opacity:.4}}
  @keyframes fadeUp{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
  .hero h1 { font-size:clamp(3rem,7vw,6rem); font-weight:800; line-height:1.0; letter-spacing:-.03em; color:var(--blanc); position:relative; z-index:1; animation:fadeUp .7s .1s ease both; }
  .hero h1 em { font-style:normal; color:var(--accent); }
  .hero-sub { font-size:clamp(1rem,2vw,1.2rem); color:var(--gris3); max-width:580px; margin:1.5rem auto 2.5rem; position:relative; z-index:1; animation:fadeUp .7s .2s ease both; font-weight:300; }
  .hero-btns { display:flex; gap:1rem; flex-wrap:wrap; align-items:center; justify-content:center; position:relative; z-index:1; animation:fadeUp .7s .3s ease both; }
  .btn-primary { background:var(--accent); color:var(--noir); font-family:'Syne',sans-serif; font-weight:700; font-size:.95rem; padding:.85rem 2rem; border-radius:100px; border:none; cursor:pointer; text-decoration:none; transition:transform .2s,opacity .2s; display:inline-block; }
  .btn-primary:hover { transform:translateY(-2px); opacity:.9; }
  .btn-ghost { background:transparent; color:var(--blanc); font-family:'Syne',sans-serif; font-weight:600; font-size:.95rem; padding:.85rem 2rem; border-radius:100px; border:0.5px solid rgba(255,255,255,.2); cursor:pointer; text-decoration:none; transition:border-color .2s,transform .2s; display:inline-block; }
  .btn-ghost:hover { border-color:var(--blanc); transform:translateY(-2px); }

  /* ── SECTION COMMONS ── */
  section { padding:6rem 4rem; }
  .section-tag { font-size:.75rem; font-weight:600; letter-spacing:.12em; text-transform:uppercase; color:var(--accent); margin-bottom:1rem; display:block; }
  .section-h2 { font-size:clamp(2rem,4vw,3rem); font-weight:800; line-height:1.1; letter-spacing:-.02em; max-width:600px; }
  .section-h2 em { font-style:normal; color:var(--accent2); }

  /* ── AGENTS ── */
  #agents { background:var(--noir); }
  .agents-layout { display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:start; margin-top:3.5rem; }
  .agents-intro { color:var(--gris3); font-size:1.05rem; line-height:1.75; font-weight:300; margin-top:1rem; }
  .agent-cards { display:flex; flex-direction:column; gap:1rem; }
  .agent-card { background:var(--gris1); border:0.5px solid rgba(255,255,255,.07); border-radius:var(--radius); padding:1.5rem; transition:border-color .3s,transform .2s; }
  .agent-card:hover { border-color:rgba(184,244,88,.3); transform:translateX(4px); }
  .agent-card-top { display:flex; align-items:center; gap:1rem; margin-bottom:.7rem; }
  .agent-icon { width:44px; height:44px; border-radius:10px; display:flex; align-items:center; justify-content:center; font-size:1.3rem; flex-shrink:0; }
  .icon-green { background:rgba(184,244,88,.12); }
  .icon-blue  { background:rgba(88,228,244,.12); }
  .icon-pink  { background:rgba(240,110,180,.12); }
  .icon-orange{ background:rgba(255,170,80,.12); }
  .agent-card h3 { font-size:1rem; font-weight:700; color:var(--blanc); }
  .agent-card p  { font-size:.88rem; color:var(--gris3); line-height:1.6; }
  .tag { display:inline-block; font-size:.72rem; font-weight:600; padding:.2rem .6rem; border-radius:100px; margin-top:.6rem; }
  .tag-green { background:rgba(184,244,88,.12); color:var(--accent); }
  .tag-blue  { background:rgba(88,228,244,.12);  color:var(--accent2); }

  /* ── FORMATIONS ── */
  #formations { background:var(--gris1); }
  .formations-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:1.5rem; margin-top:3rem; }
  .formation-card { background:var(--noir); border:0.5px solid rgba(255,255,255,.07); border-radius:var(--radius); padding:2rem; transition:transform .25s; position:relative; overflow:hidden; }
  .formation-card::before { content:''; position:absolute; top:0; left:0; right:0; height:2px; background:var(--accent); opacity:0; transition:opacity .3s; }
  .formation-card:hover { transform:translateY(-6px); }
  .formation-card:hover::before { opacity:1; }
  .formation-card.featured::before { opacity:1; background:var(--accent2); }
  .formation-card.featured { border-color:rgba(88,228,244,.2); }
  .feat-badge { display:inline-block; background:rgba(88,228,244,.12); color:var(--accent2); font-size:.72rem; font-weight:700; letter-spacing:.06em; text-transform:uppercase; padding:.25rem .7rem; border-radius:100px; margin-bottom:1rem; }
  .level-pill { display:inline-block; font-size:.72rem; font-weight:600; padding:.2rem .7rem; border-radius:100px; margin-bottom:1rem; }
  .level-debut  { background:rgba(184,244,88,.1);  color:var(--accent); }
  .level-inter  { background:rgba(255,170,80,.1);   color:#ffaa50; }
  .level-expert { background:rgba(240,110,180,.1);  color:#f06eb4; }
  .formation-card h3 { font-size:1.1rem; font-weight:700; color:var(--blanc); margin-bottom:.6rem; }
  .formation-card p  { font-size:.88rem; color:var(--gris3); line-height:1.6; margin-bottom:1.2rem; }
  .formation-meta { display:flex; gap:1rem; flex-wrap:wrap; }
  .meta-item { display:flex; align-items:center; gap:5px; font-size:.8rem; color:var(--gris3); }
  .formation-footer { margin-top:1.5rem; padding-top:1.2rem; border-top:0.5px solid rgba(255,255,255,.07); display:flex; align-items:center; justify-content:space-between; }
  .price { font-family:'Syne',sans-serif; font-size:1.3rem; font-weight:800; color:var(--blanc); }
  .btn-small { background:var(--accent); color:var(--noir); font-family:'Syne',sans-serif; font-weight:700; font-size:.8rem; padding:.5rem 1.1rem; border-radius:100px; border:none; cursor:pointer; transition:opacity .2s; text-decoration:none; display:inline-block; }
  .btn-small:hover { opacity:.85; }

  /* ── PROCESS ── */
  #process { background:var(--noir); }
  .process-steps { display:grid; grid-template-columns:repeat(4,1fr); gap:1.5rem; margin-top:3rem; }
  .process-step { padding:1.8rem; border:0.5px solid rgba(255,255,255,.07); border-radius:var(--radius); transition:border-color .3s; }
  .process-step:hover { border-color:rgba(184,244,88,.25); }
  .step-num { font-family:'Syne',sans-serif; font-size:2.5rem; font-weight:800; color:rgba(184,244,88,.15); line-height:1; margin-bottom:1rem; }
  .process-step h3 { font-size:1rem; font-weight:700; color:var(--blanc); margin-bottom:.5rem; }
  .process-step p  { font-size:.88rem; color:var(--gris3); line-height:1.6; }

  /* ── FAQ ── */
  #faq { background:var(--gris1); }
  .faq-grid { display:grid; grid-template-columns:1fr 1fr; gap:1rem; margin-top:3rem; max-width:900px; }
  .faq-item { background:var(--noir); border:0.5px solid rgba(255,255,255,.07); border-radius:var(--radius); overflow:hidden; }
  .faq-question { display:flex; align-items:center; justify-content:space-between; padding:1.3rem 1.5rem; cursor:pointer; font-family:'Syne',sans-serif; font-weight:600; font-size:.95rem; color:var(--blanc); gap:1rem; user-select:none; transition:background .2s; }
  .faq-question:hover { background:rgba(255,255,255,.03); }
  .faq-chevron { font-size:1.1rem; color:var(--accent); transition:transform .3s; flex-shrink:0; }
  .faq-item.open .faq-chevron { transform:rotate(45deg); }
  .faq-answer { max-height:0; overflow:hidden; transition:max-height .35s ease, padding .3s ease; }
  .faq-item.open .faq-answer { max-height:300px; }
  .faq-answer-inner { padding:0 1.5rem 1.3rem; font-size:.88rem; color:var(--gris3); line-height:1.7; }

  /* ── CONTACT ── */
  #contact { background:var(--noir); }
  .contact-layout { display:grid; grid-template-columns:1fr 1.4fr; gap:5rem; align-items:start; margin-top:3.5rem; }
  .contact-info h3 { font-size:1.4rem; font-weight:700; margin-bottom:1rem; }
  .contact-info p  { color:var(--gris3); font-size:.95rem; line-height:1.75; font-weight:300; margin-bottom:2rem; }
  .contact-detail { display:flex; align-items:center; gap:.75rem; margin-bottom:1rem; font-size:.9rem; color:var(--gris3); }
  .contact-icon { width:36px; height:36px; background:rgba(184,244,88,.1); border-radius:8px; display:flex; align-items:center; justify-content:center; font-size:1rem; flex-shrink:0; }
  .contact-detail a { color:var(--blanc); text-decoration:none; }
  .contact-detail a:hover { color:var(--accent); }

  /* Formulaire */
  .contact-form { background:var(--gris1); border:0.5px solid rgba(255,255,255,.07); border-radius:var(--radius); padding:2.5rem; }
  .form-row { display:grid; grid-template-columns:1fr 1fr; gap:1rem; margin-bottom:1rem; }
  .form-group { display:flex; flex-direction:column; gap:.4rem; margin-bottom:1rem; }
  .form-group label { font-size:.8rem; font-weight:600; color:var(--gris3); text-transform:uppercase; letter-spacing:.06em; }
  .form-group input,
  .form-group select,
  .form-group textarea {
    background:var(--noir); border:0.5px solid rgba(255,255,255,.12);
    border-radius:10px; padding:.75rem 1rem;
    color:var(--blanc); font-family:'DM Sans',sans-serif; font-size:.9rem;
    outline:none; transition:border-color .2s;
  }
  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus { border-color:var(--accent); }
  .form-group input::placeholder,
  .form-group textarea::placeholder { color:rgba(136,136,160,.5); }
  .form-group select { appearance:none; cursor:pointer; }
  .form-group textarea { resize:vertical; min-height:120px; }
  .form-submit { width:100%; background:var(--accent); color:var(--noir); font-family:'Syne',sans-serif; font-weight:700; font-size:1rem; padding:1rem; border-radius:100px; border:none; cursor:pointer; transition:opacity .2s,transform .2s; margin-top:.5rem; }
  .form-submit:hover { opacity:.88; transform:translateY(-1px); }
  .form-note { font-size:.75rem; color:var(--gris3); text-align:center; margin-top:.75rem; }
  .success-msg { display:none; text-align:center; padding:2rem; }
  .success-msg.visible { display:block; }
  .success-icon { font-size:3rem; margin-bottom:1rem; }
  .success-msg h3 { font-size:1.3rem; font-weight:700; color:var(--accent); margin-bottom:.5rem; }
  .success-msg p  { color:var(--gris3); font-size:.9rem; }

  /* ── CTA FINAL ── */
  #cta-final { background:var(--gris1); text-align:center; padding:7rem 4rem; position:relative; overflow:hidden; }
  #cta-final::before { content:''; position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); width:600px; height:300px; border-radius:50%; background:radial-gradient(ellipse,rgba(184,244,88,.07) 0%,transparent 70%); pointer-events:none; }
  #cta-final h2 { font-size:clamp(2rem,5vw,3.5rem); font-weight:800; letter-spacing:-.03em; max-width:700px; margin:0 auto 1.5rem; position:relative; z-index:1; }
  #cta-final p  { color:var(--gris3); max-width:500px; margin:0 auto 2.5rem; font-size:1.05rem; font-weight:300; position:relative; z-index:1; }
  .cta-btns { display:flex; gap:1rem; justify-content:center; flex-wrap:wrap; position:relative; z-index:1; }

  /* ── FOOTER ── */
  footer { background:var(--noir); border-top:0.5px solid rgba(255,255,255,.07); padding:2.5rem 4rem; display:flex; align-items:center; justify-content:space-between; flex-wrap:wrap; gap:1rem; }
  .footer-links { display:flex; gap:2rem; }
  .footer-links a { color:var(--gris3); font-size:.85rem; text-decoration:none; }
  .footer-links a:hover { color:var(--blanc); }
  .footer-copy { font-size:.8rem; color:var(--gris3); }

  /* ── RESPONSIVE ── */
  @media(max-width:900px){
    nav { padding:1rem 1.5rem; }
    .nav-links { display:none; }
    section { padding:4rem 1.5rem; }
    .agents-layout { grid-template-columns:1fr; gap:2.5rem; }
    .formations-grid { grid-template-columns:1fr; }
    .process-steps { grid-template-columns:1fr 1fr; }
    .faq-grid { grid-template-columns:1fr; }
    .contact-layout { grid-template-columns:1fr; gap:2rem; }
    .form-row { grid-template-columns:1fr; }
    footer { flex-direction:column; align-items:flex-start; padding:2rem 1.5rem; }
  }
  @media(max-width:600px){
    .process-steps { grid-template-columns:1fr; }
  }
</style>
</head>
<body>

<!-- ═══════════════════════════ NAV ═══════════════════════════ -->
<nav>
  <a href="#" class="logo">Nexa<span>AI</span></a>
  <ul class="nav-links">
    <li><a href="#agents">Agents IA</a></li>
    <li><a href="#formations">Formations</a></li>
    <li><a href="#process">Méthode</a></li>
    <li><a href="#faq">FAQ</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Prendre contact →</a>
</nav>

<!-- ═══════════════════════════ HERO ═══════════════════════════ -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-badge"><div class="dot"></div> Spécialiste en IA générative &amp; automatisation</div>
  <h1>
    Automatisez votre<br>
    <em>futur avec l'IA</em>
  </h1>
  <p class="hero-sub">Je crée des agents IA sur mesure et forme vos équipes pour que la transformation digitale devienne votre avantage concurrentiel.</p>
  <div class="hero-btns">
    <a href="#agents" class="btn-primary">Découvrir mes services</a>
    <a href="#contact" class="btn-ghost">Me contacter</a>
  </div>
</section>

<!-- ═══════════════════════════ AGENTS ═══════════════════════════ -->
<section id="agents">
  <span class="section-tag">Agents IA sur mesure</span>
  <h2 class="section-h2">Des IA qui <em>travaillent</em> pour vous, 24h/24</h2>
  <div class="agents-layout">
    <div>
      <p class="agents-intro">Je conçois et déploie des agents intelligents adaptés à vos processus métier. De la prospection commerciale à l'analyse de données, mes agents automatisent les tâches répétitives et libèrent votre temps pour ce qui a vraiment de la valeur.</p>
      <p class="agents-intro" style="margin-top:1rem;">Chaque agent est conçu sur mesure, documenté et accompagné d'une formation pour votre équipe.</p>
      <div style="margin-top:2rem;">
        <a href="#contact" class="btn-primary">Discuter de votre projet →</a>
      </div>
    </div>
    <div class="agent-cards">
      <div class="agent-card">
        <div class="agent-card-top">
          <div class="agent-icon icon-green">🤖</div>
          <h3>Agent Prospection &amp; CRM</h3>
        </div>
        <p>Qualifie vos leads, rédige des emails personnalisés et met à jour votre CRM automatiquement.</p>
        <span class="tag tag-green">Automatisation commerciale</span>
      </div>
      <div class="agent-card">
        <div class="agent-card-top">
          <div class="agent-icon icon-blue">📊</div>
          <h3>Agent Analyse &amp; Reporting</h3>
        </div>
        <p>Collecte, analyse et synthétise vos données en rapports clairs et recommandations actionnables.</p>
        <span class="tag tag-blue">Data &amp; Business Intelligence</span>
      </div>
      <div class="agent-card">
        <div class="agent-card-top">
          <div class="agent-icon icon-pink">💬</div>
          <h3>Agent Support Client</h3>
        </div>
        <p>Répond aux questions courantes, escalade intelligemment et réduit le temps de traitement.</p>
        <span class="tag tag-green">Relation client</span>
      </div>
      <div class="agent-card">
        <div class="agent-card-top">
          <div class="agent-icon icon-orange">✍️</div>
          <h3>Agent Création de Contenu</h3>
        </div>
        <p>Génère articles, posts, newsletters et scripts vidéo alignés sur votre voix de marque.</p>
        <span class="tag tag-blue">Marketing &amp; Contenu</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════════════════════ FORMATIONS ═══════════════════════════ -->
<section id="formations">
  <span class="section-tag">Formations IA</span>
  <h2 class="section-h2">Montez en compétence, <em>concrètement</em></h2>
  <div style="color:var(--gris3);font-weight:300;margin-top:.75rem;max-width:600px;">Des formations pratiques, orientées résultats, adaptées à votre niveau et à votre secteur d'activité.</div>
  <div class="formations-grid">
    <div class="formation-card">
      <span class="level-pill level-debut">Débutant</span>
      <h3>IA pour les non-techniciens</h3>
      <p>Comprendre l'IA, les LLM et utiliser les outils du quotidien (ChatGPT, Claude, Copilot) pour gagner du temps dès demain.</p>
      <div class="formation-meta">
        <div class="meta-item">⏱ 1 jour</div>
        <div class="meta-item">👥 Présentiel</div>
        <div class="meta-item">📍 Paris &amp; distanciel</div>
      </div>
      <div class="formation-footer">
        <span class="price">Sur devis</span>
        <a href="#contact" class="btn-small">Renseignements</a>
      </div>
    </div>
    <div class="formation-card featured">
      <span class="feat-badge">⭐ Populaire</span>
      <h3>Prompt Engineering &amp; Agents IA</h3>
      <p>Maîtriser l'art du prompt, créer des workflows automatisés et déployer vos premiers agents avec n8n et Make.</p>
      <div class="formation-meta">
        <div class="meta-item">⏱ 3 jours</div>
        <div class="meta-item">🖥 Hybride</div>
        <div class="meta-item">🏅 Certifiant</div>
      </div>
      <div class="formation-footer">
        <span class="price">Sur devis</span>
        <a href="#contact" class="btn-small">Renseignements</a>
      </div>
    </div>
    <div class="formation-card">
      <span class="level-pill level-expert">Expert</span>
      <h3>Développer avec les API IA</h3>
      <p>Intégrer OpenAI, Anthropic et Mistral dans vos applications, construire des RAG et des pipelines LLM.</p>
      <div class="formation-meta">
        <div class="meta-item">⏱ 5 jours</div>
        <div class="meta-item">💻 Distanciel</div>
        <div class="meta-item">🏅 Certifiant</div>
      </div>
      <div class="formation-footer">
        <span class="price">Sur devis</span>
        <a href="#contact" class="btn-small">Renseignements</a>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════════════════════ PROCESS ═══════════════════════════ -->
<section id="process">
  <span class="section-tag">Ma méthode</span>
  <h2 class="section-h2">De l'idée au déploiement <em>en 4 étapes</em></h2>
  <div class="process-steps">
    <div class="process-step">
      <div class="step-num">01</div>
      <h3>Audit &amp; Cadrage</h3>
      <p>On identifie ensemble les processus à automatiser et les gains potentiels pour votre activité.</p>
    </div>
    <div class="process-step">
      <div class="step-num">02</div>
      <h3>Conception</h3>
      <p>Prototypage de l'agent IA, choix des outils et validation de l'architecture technique.</p>
    </div>
    <div class="process-step">
      <div class="step-num">03</div>
      <h3>Développement</h3>
      <p>Développement itératif avec tests continus et ajustements selon vos retours terrain.</p>
    </div>
    <div class="process-step">
      <div class="step-num">04</div>
      <h3>Déploiement &amp; Suivi</h3>
      <p>Mise en production, documentation complète et formation de vos équipes pour une adoption réussie.</p>
    </div>
  </div>
</section>

<!-- ═══════════════════════════ FAQ ═══════════════════════════ -->
<section id="faq">
  <span class="section-tag">Questions fréquentes</span>
  <h2 class="section-h2">Tout ce que vous <em>voulez savoir</em></h2>
  <div class="faq-grid">

    <div class="faq-item">
      <div class="faq-question" onclick="toggleFaq(this)">
        Faut-il être technique pour bénéficier de vos services ?
        <span class="faq-chevron">+</span>
      </div>
      <div class="faq-answer">
        <div class="faq-answer-inner">Non, absolument pas. Je m'adapte à votre niveau de maturité digitale. Mon rôle est de rendre l'IA accessible, que vous soyez une TPE, un indépendant ou une grande entreprise. L'audit initial permet de cadrer précisément vos besoins.</div>
      </div>
    </div>

    <div class="faq-item">
      <div class="faq-question" onclick="toggleFaq(this)">
        Combien de temps faut-il pour créer un agent IA ?
        <span class="faq-chevron">+</span>
      </div>
      <div class="faq-answer">
        <div class="faq-answer-inner">Cela dépend de la complexité du projet. Un agent simple (automatisation d'emails, FAQ bot) peut être opérationnel en 2 à 4 semaines. Un projet plus complexe avec intégrations multiples demande 1 à 3 mois. Je vous donne une estimation précise après l'audit gratuit.</div>
      </div>
    </div>

    <div class="faq-item">
      <div class="faq-question" onclick="toggleFaq(this)">
        Mes données sont-elles en sécurité ?
        <span class="faq-chevron">+</span>
      </div>
      <div class="faq-answer">
        <div class="faq-answer-inner">La sécurité et la confidentialité sont au cœur de chaque projet. Je propose des architectures on-premise ou cloud privé selon vos contraintes. Un accord de confidentialité (NDA) est systématiquement proposé avant tout échange de données sensibles.</div>
      </div>
    </div>

    <div class="faq-item">
      <div class="faq-question" onclick="toggleFaq(this)">
        Les formations sont-elles finançables (OPCO, CPF) ?
        <span class="faq-chevron">+</span>
      </div>
      <div class="faq-answer">
        <div class="faq-answer-inner">Je travaille à l'obtention de certifications Qualiopi pour ouvrir les formations au financement OPCO et CPF. En attendant, certaines formations peuvent être prises en charge par votre OPCO au titre du plan de développement des compétences. Contactez-moi pour plus d'informations.</div>
      </div>
    </div>

    <div class="faq-item">
      <div class="faq-question" onclick="toggleFaq(this)">
        Quelle est la différence entre un chatbot et un agent IA ?
        <span class="faq-chevron">+</span>
      </div>
      <div class="faq-answer">
        <div class="faq-answer-inner">Un chatbot répond à des questions selon des règles prédéfinies. Un agent IA est capable de raisonner, planifier et exécuter des tâches complexes : chercher des informations, interagir avec vos outils (CRM, email, base de données), prendre des décisions et s'adapter au contexte.</div>
      </div>
    </div>

    <div class="faq-item">
      <div class="faq-question" onclick="toggleFaq(this)">
        Proposez-vous un suivi après la livraison ?
        <span class="faq-chevron">+</span>
      </div>
      <div class="faq-answer">
        <div class="faq-answer-inner">Oui, je propose une période de garantie et des contrats de maintenance mensuels. Les modèles d'IA évoluent rapidement, il est donc important de maintenir et d'améliorer les agents dans le temps. Je propose des forfaits d'accompagnement adaptés à vos besoins.</div>
      </div>
    </div>

  </div>
</section>

<!-- ═══════════════════════════ CONTACT ═══════════════════════════ -->
<section id="contact">
  <span class="section-tag">Contact</span>
  <h2 class="section-h2">Parlons de votre <em>projet</em></h2>
  <div class="contact-layout">
    <div class="contact-info">
      <h3>Un audit gratuit de 30 minutes</h3>
      <p>Vous avez un projet d'automatisation ou souhaitez former votre équipe ? Remplissez le formulaire et je vous recontacte sous 24h pour un premier échange sans engagement.</p>
      <div class="contact-detail">
        <div class="contact-icon">📧</div>
        <a href="mailto:contact@votresite.fr">contact@votresite.fr</a>
      </div>
      <div class="contact-detail">
        <div class="contact-icon">📍</div>
        <span>Paris, France — interventions toute la France</span>
      </div>
      <div class="contact-detail">
        <div class="contact-icon">🕐</div>
        <span>Réponse sous 24h ouvrées</span>
      </div>
    </div>

    <div class="contact-form" id="formWrapper">
      <form id="contactForm" onsubmit="handleSubmit(event)">
        <div class="form-row">
          <div class="form-group">
            <label for="prenom">Prénom *</label>
            <input type="text" id="prenom" name="prenom" placeholder="Marie" required>
          </div>
          <div class="form-group">
            <label for="nom">Nom *</label>
            <input type="text" id="nom" name="nom" placeholder="Dupont" required>
          </div>
        </div>
        <div class="form-group">
          <label for="email">Email *</label>
          <input type="email" id="email" name="email" placeholder="marie.dupont@entreprise.fr" required>
        </div>
        <div class="form-group">
          <label for="entreprise">Entreprise</label>
          <input type="text" id="entreprise" name="entreprise" placeholder="Nom de votre entreprise">
        </div>
        <div class="form-group">
          <label for="sujet">Ce qui vous intéresse *</label>
          <select id="sujet" name="sujet" required>
            <option value="" disabled selected>Choisissez une option</option>
            <option value="agent">Création d'un agent IA sur mesure</option>
            <option value="formation-debutant">Formation — Débutant</option>
            <option value="formation-inter">Formation — Prompt Engineering &amp; Agents</option>
            <option value="formation-expert">Formation — Développeur API IA</option>
            <option value="audit">Audit gratuit de 30 minutes</option>
            <option value="autre">Autre</option>
          </select>
        </div>
        <div class="form-group">
          <label for="message">Décrivez votre projet</label>
          <textarea id="message" name="message" placeholder="Parlez-moi de votre activité, de vos besoins, de ce que vous aimeriez automatiser ou apprendre…"></textarea>
        </div>
        <button type="submit" class="form-submit">Envoyer ma demande →</button>
        <p class="form-note">Vos données sont confidentielles et ne seront jamais partagées.</p>
      </form>
      <div class="success-msg" id="successMsg">
        <div class="success-icon">✅</div>
        <h3>Message envoyé !</h3>
        <p>Merci pour votre message. Je vous recontacte sous 24h ouvrées pour organiser notre premier échange.</p>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════════════════════ CTA FINAL ═══════════════════════════ -->
<section id="cta-final">
  <h2>Prêt à passer à l'IA&nbsp;?</h2>
  <p>Échangeons sur vos projets. Un audit gratuit de 30 minutes pour identifier vos premières opportunités d'automatisation.</p>
  <div class="cta-btns">
    <a href="#contact" class="btn-primary">Réserver un audit gratuit →</a>
    <a href="#formations" class="btn-ghost">Explorer les formations</a>
  </div>
</section>

<!-- ═══════════════════════════ FOOTER ═══════════════════════════ -->
<footer>
  <a href="#" class="logo">Nexa<span>AI</span></a>
  <div class="footer-links">
    <a href="#agents">Agents IA</a>
    <a href="#formations">Formations</a>
    <a href="#faq">FAQ</a>
    <a href="#contact">Contact</a>
    <a href="#">Mentions légales</a>
  </div>
  <div class="footer-copy">© 2025 NexaAI — Tous droits réservés</div>
</footer>

<script>
  function toggleFaq(el) {
    var item = el.parentElement;
    var isOpen = item.classList.contains('open');
    document.querySelectorAll('.faq-item.open').forEach(function(i){ i.classList.remove('open'); });
    if (!isOpen) item.classList.add('open');
  }

  function handleSubmit(e) {
    e.preventDefault();
    var form = document.getElementById('contactForm');
    var success = document.getElementById('successMsg');
    form.style.display = 'none';
    success.classList.add('visible');
    // Pour connecter à un vrai service d'email, voir les instructions dans le README
  }
</script>
</body>
</html>
