# Delavier-maxime
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Maxime Delavier — Portfolio BUT GEA</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=Lato:wght@300;400;700&family=Montserrat:wght@400;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --navy: #0f1e3c;
      --navy-light: #1a2f57;
      --accent: #c8a96e;
      --text: #1a1a2e;
      --text-muted: #5a6180;
      --bg: #fafaf8;
      --bg-card: #ffffff;
      --border: rgba(15, 30, 60, 0.1);
      --serif: 'Playfair Display', Georgia, serif;
      --sans: 'Lato', system-ui, sans-serif;
      --label-font: 'Montserrat', system-ui, sans-serif;
    }

    html { scroll-behavior: smooth; }
    body { font-family: var(--sans); background: var(--bg); color: var(--text); line-height: 1.7; font-weight: 300; }

    /* NAV */
    nav { position: sticky; top: 0; z-index: 100; display: flex; justify-content: space-between; align-items: center; padding: 1.1rem 3rem; background: rgba(250,250,248,0.92); backdrop-filter: blur(12px); border-bottom: 1px solid var(--border); }
    .nav-logo { font-family: var(--serif); font-size: 1.15rem; color: var(--navy); }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a { font-size: 0.82rem; font-weight: 400; color: var(--text-muted); text-decoration: none; letter-spacing: 0.05em; text-transform: uppercase; transition: color 0.2s; font-family: var(--label-font); }
    .nav-links a:hover { color: var(--navy); }

    /* HERO */
    .hero { min-height: 88vh; display: flex; flex-direction: column; justify-content: center; padding: 6rem 3rem 4rem; position: relative; overflow: hidden; }
    .hero::before { content: ''; position: absolute; top: -100px; right: -100px; width: 500px; height: 500px; border-radius: 50%; background: radial-gradient(circle, rgba(200,169,110,0.12) 0%, transparent 70%); pointer-events: none; }
    .hero-eyebrow { display: inline-flex; align-items: center; gap: 8px; font-size: 0.75rem; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; color: var(--accent); margin-bottom: 1.5rem; opacity: 0; animation: fadeUp 0.6s 0.1s forwards; font-family: var(--label-font); }
    .hero-eyebrow::before { content: ''; display: block; width: 28px; height: 1px; background: var(--accent); }
    .hero h1 { font-family: var(--serif); font-size: clamp(2.8rem, 7vw, 5.5rem); color: var(--navy); line-height: 1.1; max-width: 700px; opacity: 0; animation: fadeUp 0.7s 0.2s forwards; }
    .hero h1 em { font-style: normal; color: var(--accent); }
    .hero-desc { margin-top: 1.5rem; font-size: 1rem; color: var(--text-muted); max-width: 480px; line-height: 1.8; opacity: 0; animation: fadeUp 0.7s 0.35s forwards; }
    .hero-cta { margin-top: 2.5rem; display: flex; gap: 12px; flex-wrap: wrap; opacity: 0; animation: fadeUp 0.7s 0.5s forwards; }

    .btn { display: inline-block; padding: 0.75rem 1.6rem; border-radius: 4px; font-family: var(--sans); font-size: 0.85rem; font-weight: 500; cursor: pointer; text-decoration: none; transition: all 0.2s; letter-spacing: 0.02em; }
    .btn-dark { background: var(--navy); color: #fff; border: 1px solid var(--navy); }
    .btn-dark:hover { background: var(--navy-light); }
    .btn-outline { background: transparent; color: var(--navy); border: 1px solid var(--navy); }
    .btn-outline:hover { background: var(--navy); color: #fff; }
    .btn-accent { background: var(--accent); color: #fff; border: 1px solid var(--accent); }
    .btn-accent:hover { background: #b8934e; border-color: #b8934e; }

    /* SECTIONS */
    section { padding: 5rem 3rem; border-top: 1px solid var(--border); }
    .section-label { font-family: var(--label-font); font-size: 0.72rem; font-weight: 600; letter-spacing: 0.14em; text-transform: uppercase; color: var(--accent); margin-bottom: 0.75rem; display: flex; align-items: center; gap: 10px; }
    .section-label::after { content: ''; flex: 1; max-width: 40px; height: 1px; background: var(--accent); }
    .section-title { font-family: var(--serif); font-size: clamp(1.8rem, 4vw, 2.8rem); color: var(--navy); line-height: 1.15; max-width: 500px; margin-bottom: 3rem; }

    /* À PROPOS */
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start; }
    .about-text p { color: var(--text-muted); margin-bottom: 1rem; font-size: 0.95rem; }
    .about-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .stat-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 8px; padding: 1.5rem; }
    .stat-card .num { font-family: var(--serif); font-size: 2rem; color: var(--navy); line-height: 1; margin-bottom: 4px; }
    .stat-card .lbl { font-size: 0.78rem; color: var(--text-muted); font-weight: 400; }

    /* ERASMUS BADGE */
    .erasmus-badge { display: inline-flex; align-items: center; gap: 10px; background: linear-gradient(135deg, rgba(200,169,110,0.12), rgba(15,30,60,0.06)); border: 1px solid var(--accent); border-radius: 10px; padding: 1rem 1.5rem; margin-top: 2rem; max-width: 420px; }
    .erasmus-badge .flag { font-size: 1.8rem; }
    .erasmus-badge .info { display: flex; flex-direction: column; }
    .erasmus-badge .info strong { font-size: 0.9rem; color: var(--navy); font-weight: 700; }
    .erasmus-badge .info span { font-size: 0.8rem; color: var(--text-muted); }

    /* CV SECTION */
    .cv-block { background: var(--navy); border-radius: 12px; padding: 2.5rem; display: flex; align-items: center; justify-content: space-between; gap: 2rem; flex-wrap: wrap; }
    .cv-block .cv-text h3 { font-family: var(--serif); font-size: 1.5rem; color: #fff; margin-bottom: 0.5rem; }
    .cv-block .cv-text p { font-size: 0.9rem; color: rgba(255,255,255,0.65); max-width: 380px; line-height: 1.7; }
    .cv-block .cv-actions { display: flex; flex-direction: column; gap: 10px; align-items: flex-start; }
    .cv-upload-label { display: inline-flex; align-items: center; gap: 8px; background: rgba(255,255,255,0.12); color: #fff; border: 1px solid rgba(255,255,255,0.25); padding: 0.65rem 1.2rem; border-radius: 4px; font-size: 0.83rem; font-family: var(--sans); cursor: pointer; transition: background 0.2s; }
    .cv-upload-label:hover { background: rgba(255,255,255,0.2); }
    #cv-file-input { display: none; }
    #cv-view-btn { display: none; }
    .cv-status { font-size: 0.78rem; color: rgba(255,255,255,0.5); }

    /* COMPÉTENCES — style original */
    .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; }
    .skill-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 8px; padding: 1.5rem; transition: border-color 0.2s, transform 0.2s; }
    .skill-card:hover { border-color: var(--accent); transform: translateY(-2px); }
    .skill-icon { width: 36px; height: 36px; border-radius: 8px; background: rgba(200,169,110,0.12); display: flex; align-items: center; justify-content: center; margin-bottom: 1rem; font-size: 1.1rem; }
    .skill-card h3 { font-size: 0.95rem; font-weight: 500; color: var(--navy); margin-bottom: 6px; }
    .skill-card p { font-size: 0.82rem; color: var(--text-muted); line-height: 1.6; }

    /* PROJETS — cartes cliquables */
    .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1.25rem; }
    .project-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 8px; padding: 2rem; position: relative; overflow: hidden; transition: border-color 0.2s, box-shadow 0.2s; cursor: pointer; }
    .project-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px; background: var(--accent); opacity: 0; transition: opacity 0.2s; }
    .project-card:hover { border-color: var(--accent); box-shadow: 0 6px 20px rgba(15,30,60,0.08); }
    .project-card:hover::before { opacity: 1; }
    .project-card .click-hint { font-size: 0.7rem; color: var(--text-muted); font-family: var(--label-font); letter-spacing: 0.04em; margin-bottom: 0.75rem; display: block; }
    .project-badge { display: inline-block; font-size: 0.7rem; font-weight: 600; letter-spacing: 0.06em; text-transform: uppercase; padding: 3px 10px; border-radius: 20px; margin-bottom: 1rem; font-family: var(--label-font); }
    .badge-gema { background: #e8f0fe; color: #1a3a8f; }
    .badge-mgt { background: #e6f4ea; color: #1e6b3a; }
    .badge-gest { background: #fef3e2; color: #9a5c00; }
    .project-card h3 { font-size: 1rem; font-weight: 600; color: var(--navy); margin-bottom: 8px; font-family: var(--serif); }
    .project-card p { font-size: 0.85rem; color: var(--text-muted); line-height: 1.65; }
    .project-has-content { border-left: 3px solid var(--accent) !important; }

    /* CONTACT */
    .contact-wrapper { max-width: 560px; }
    .contact-wrapper > p { color: var(--text-muted); margin-bottom: 2rem; font-size: 0.95rem; }
    .contact-list { list-style: none; display: flex; flex-direction: column; gap: 0.75rem; }
    .contact-list li { display: flex; align-items: center; gap: 12px; font-size: 0.9rem; color: var(--text-muted); }
    .contact-list .icon { width: 36px; height: 36px; border-radius: 8px; background: rgba(200,169,110,0.12); display: flex; align-items: center; justify-content: center; flex-shrink: 0; font-size: 1rem; }

    /* FOOTER */
    footer { border-top: 1px solid var(--border); padding: 2rem 3rem; display: flex; justify-content: space-between; align-items: center; font-size: 0.78rem; color: var(--text-muted); }
    footer .logo { font-family: var(--serif); color: var(--navy); font-size: 0.95rem; }

    /* MODAL PROJET */
    .modal-overlay { display: none; position: fixed; inset: 0; background: rgba(10,20,40,0.5); z-index: 1000; align-items: center; justify-content: center; padding: 1rem; backdrop-filter: blur(4px); }
    .modal-overlay.open { display: flex; }
    .modal { background: var(--bg-card); border-radius: 12px; width: 100%; max-width: 600px; max-height: 90vh; overflow-y: auto; padding: 2rem; position: relative; animation: modalIn 0.25s ease; }
    @keyframes modalIn { from { opacity: 0; transform: translateY(16px) scale(0.98); } to { opacity: 1; transform: none; } }
    .modal-close { position: absolute; top: 1rem; right: 1rem; background: none; border: none; font-size: 1.3rem; cursor: pointer; color: var(--text-muted); }
    .modal-close:hover { color: var(--navy); }
    .modal h2 { font-family: var(--serif); font-size: 1.4rem; color: var(--navy); margin-bottom: 1.5rem; }
    .modal-field-label { font-family: var(--label-font); font-size: 0.72rem; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; color: var(--navy); margin-bottom: 0.5rem; margin-top: 1.2rem; display: block; }
    .modal input[type="text"], .modal textarea, .modal select { width: 100%; border: 1px solid var(--border); border-radius: 6px; padding: 0.7rem; font-family: var(--sans); font-size: 0.875rem; color: var(--text); background: var(--bg); transition: border-color 0.2s; }
    .modal input[type="text"]:focus, .modal textarea:focus { outline: none; border-color: var(--navy); }
    .modal textarea { min-height: 90px; resize: vertical; }
    .modal select { cursor: pointer; }

    /* ZONE UPLOAD IMAGES */
    .upload-zone { border: 2px dashed var(--border); border-radius: 8px; padding: 1.5rem; text-align: center; cursor: pointer; transition: border-color 0.2s, background 0.2s; margin-top: 0.5rem; }
    .upload-zone:hover { border-color: var(--accent); background: rgba(200,169,110,0.04); }
    .upload-zone p { font-size: 0.82rem; color: var(--text-muted); margin-top: 6px; }
    .upload-zone .upload-icon { font-size: 1.8rem; }
    #modal-file-input { display: none; }
    .attachments-list { margin-top: 0.75rem; display: flex; flex-direction: column; gap: 0.5rem; }
    .attachment-item { display: flex; align-items: center; justify-content: space-between; background: rgba(15,30,60,0.04); border-radius: 6px; padding: 0.5rem 0.75rem; font-size: 0.82rem; color: var(--navy); }
    .attachment-item button { background: none; border: none; cursor: pointer; color: var(--text-muted); font-size: 1rem; }
    .attachment-item button:hover { color: #c0392b; }
    .img-preview-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(80px, 1fr)); gap: 8px; margin-top: 0.75rem; }
    .img-preview-item { position: relative; }
    .img-preview-item img { width: 100%; height: 80px; object-fit: cover; border-radius: 6px; border: 1px solid var(--border); }
    .img-preview-item .remove-img { position: absolute; top: -6px; right: -6px; background: #c0392b; color: #fff; border: none; border-radius: 50%; width: 20px; height: 20px; font-size: 0.7rem; cursor: pointer; display: flex; align-items: center; justify-content: center; }

    .modal-actions { display: flex; gap: 10px; margin-top: 1.5rem; }
    .btn-save { background: var(--navy); color: #fff; border: none; padding: 0.65rem 1.4rem; border-radius: 4px; font-family: var(--label-font); font-size: 0.82rem; font-weight: 600; cursor: pointer; letter-spacing: 0.04em; }
    .btn-save:hover { background: var(--navy-light); }
    .btn-cancel { background: transparent; color: var(--text-muted); border: 1px solid var(--border); padding: 0.65rem 1.2rem; border-radius: 4px; font-family: var(--sans); font-size: 0.85rem; cursor: pointer; }

    /* SAVED CONTENT AFFICHÉ SUR LA CARTE */
    .project-saved-preview { margin-top: 0.75rem; font-size: 0.78rem; color: var(--text-muted); display: flex; align-items: center; gap: 6px; }
    .project-saved-preview .dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent); flex-shrink: 0; }

    @keyframes fadeUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }

    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { gap: 1rem; }
      .hero { padding: 4rem 1.5rem 3rem; }
      section { padding: 3.5rem 1.5rem; }
      .about-grid { grid-template-columns: 1fr; gap: 2rem; }
      .cv-block { flex-direction: column; }
      footer { flex-direction: column; gap: 0.5rem; text-align: center; padding: 1.5rem; }
    }
  </style>
</head>
<body>

  <nav>
    <span class="nav-logo">Maxime Delavier</span>
    <ul class="nav-links">
      <li><a href="#apropos">À propos</a></li>
      <li><a href="#competences">Compétences</a></li>
      <li><a href="#projets">Projets</a></li>
      <li><a href="#cv">Mon CV</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero" id="accueil">
    <span class="hero-eyebrow">BUT GEA · GEMA · 1ère année · 2025–2026</span>
    <h1>Maxime<br><em>Delavier</em></h1>
    <p class="hero-desc">
      Étudiant en BUT Gestion des Entreprises et des Administrations, parcours GEMA — Gestion Entrepreneuriale et Managériale. Motivé, rigoureux et impliqué dans chacun de mes projets.
    </p>
    <div class="hero-cta">
      <a href="#projets" class="btn btn-dark">Voir mes projets</a>
      <a href="#cv" class="btn btn-accent">Mon CV</a>
      <a href="#contact" class="btn btn-outline">Me contacter</a>
    </div>
  </section>

  <!-- À PROPOS -->
  <section id="apropos">
    <p class="section-label">À propos</p>
    <h2 class="section-title">Qui suis-je ?</h2>
    <div class="about-grid">
      <div class="about-text">
        <p>
          Je suis actuellement en première année de BUT Gestion des Entreprises et des Administrations, dans le parcours GEMA — Gestion Entrepreneuriale et Managériale. Curieux et impliqué, je m'intéresse à la gestion d'entreprise, au management et à la stratégie organisationnelle.
        </p>
        <p>
          Mon objectif est de mettre en pratique les compétences acquises en cours à travers des projets concrets, des études de cas et des expériences professionnelles.
        </p>
        <div class="erasmus-badge">
          <span class="flag">🍁</span>
          <div class="info">
            <strong>Erasmus+ — Canada</strong>
            <span>Semestre à l'international prévu dans le cadre du BUT GEA. Une expérience enrichissante pour développer mes compétences interculturelles et managériales.</span>
          </div>
        </div>
      </div>
      <div class="about-stats">
        <div class="stat-card">
          <div class="num">1ère</div>
          <div class="lbl">Année de BUT GEA</div>
        </div>
        <div class="stat-card">
          <div class="num">GEMA</div>
          <div class="lbl">Parcours suivi</div>
        </div>
        <div class="stat-card">
          <div class="num">🍁</div>
          <div class="lbl">Erasmus Canada</div>
        </div>
        <div class="stat-card">
          <div class="num">ENT</div>
          <div class="lbl">Entrepreneuriat</div>
        </div>
      </div>
    </div>
  </section>

  <!-- COMPÉTENCES -->
  <section id="competences">
    <p class="section-label">Compétences</p>
    <h2 class="section-title">Ce que je maîtrise</h2>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-icon">🤝</div>
        <h3>Management</h3>
        <p>Organisation d'équipe, leadership, conduite de projet collectif.</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🚀</div>
        <h3>Entrepreneuriat</h3>
        <p>Création de valeur, analyse d'opportunités, esprit d'initiative.</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">📊</div>
        <h3>Gestion administrative</h3>
        <p>Tableaux de bord, gestion documentaire, outils bureautiques (Excel, Word).</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🎯</div>
        <h3>Stratégie d'entreprise</h3>
        <p>Analyse SWOT, diagnostic interne/externe, prise de décision.</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">📝</div>
        <h3>Rédaction professionnelle</h3>
        <p>Comptes-rendus, rapports, notes de synthèse, supports de présentation.</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">📢</div>
        <h3>Communication</h3>
        <p>Communication interne et externe, présentation orale, travail en groupe.</p>
      </div>
    </div>
  </section>

  <!-- PROJETS -->
  <section id="projets">
    <p class="section-label">Projets</p>
    <h2 class="section-title">Mes travaux & réalisations</h2>
    <p style="font-size:0.85rem; color:var(--text-muted); margin-top:-2rem; margin-bottom:2rem;">Cliquez sur une carte pour y ajouter vos travaux, images ou pièces jointes.</p>
    <div class="projects-grid" id="projects-grid">

      <div class="project-card" onclick="openModal(0)" data-index="0">
        <span class="project-badge badge-gema">GEMA</span>
        <h3 id="proj-title-0">Projet 1 — À compléter</h3>
        <p id="proj-desc-0">Cliquez pour décrire ce projet, ajouter des images ou des pièces jointes.</p>
        <div class="project-saved-preview" id="proj-preview-0" style="display:none;"><div class="dot"></div><span></span></div>
      </div>

      <div class="project-card" onclick="openModal(1)" data-index="1">
        <span class="project-badge badge-mgt">Management</span>
        <h3 id="proj-title-1">Projet 2 — À compléter</h3>
        <p id="proj-desc-1">Cliquez pour décrire ce projet, ajouter des images ou des pièces jointes.</p>
        <div class="project-saved-preview" id="proj-preview-1" style="display:none;"><div class="dot"></div><span></span></div>
      </div>

      <div class="project-card" onclick="openModal(2)" data-index="2">
        <span class="project-badge badge-gest">Gestion</span>
        <h3 id="proj-title-2">Projet 3 — À compléter</h3>
        <p id="proj-desc-2">Cliquez pour décrire ce projet, ajouter des images ou des pièces jointes.</p>
        <div class="project-saved-preview" id="proj-preview-2" style="display:none;"><div class="dot"></div><span></span></div>
      </div>

      <div class="project-card" onclick="openModal(3)" data-index="3">
        <span class="project-badge badge-gema">GEMA</span>
        <h3 id="proj-title-3">Projet 4 — À compléter</h3>
        <p id="proj-desc-3">Cliquez pour décrire ce projet, ajouter des images ou des pièces jointes.</p>
        <div class="project-saved-preview" id="proj-preview-3" style="display:none;"><div class="dot"></div><span></span></div>
      </div>

    </div>
  </section>

  <!-- CV -->
  <section id="cv">
    <p class="section-label">Curriculum Vitae</p>
    <h2 class="section-title">Mon CV</h2>
    <div class="cv-block">
      <div class="cv-text">
        <h3>Maxime Delavier</h3>
        <p>Dépose ton CV au format PDF pour le rendre consultable directement depuis ton portfolio. Il sera visible pour toute personne qui visite ta page.</p>
      </div>
      <div class="cv-actions">
        <label class="cv-upload-label" for="cv-file-input">
          📎 &nbsp;Importer mon CV (PDF)
        </label>
        <input type="file" id="cv-file-input" accept=".pdf" onchange="handleCvUpload(event)" />
        <a id="cv-view-btn" class="btn btn-accent" target="_blank">📄 Consulter mon CV</a>
        <span class="cv-status" id="cv-status">Aucun CV importé pour l'instant.</span>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <p class="section-label">Contact</p>
    <h2 class="section-title">Travaillons ensemble</h2>
    <div class="contact-wrapper">
      <p>
        Disponible pour un stage ou toute opportunité professionnelle en lien avec la gestion d'entreprise et le management. N'hésitez pas à me contacter.
      </p>
      <ul class="contact-list">
        <li><div class="icon">✉️</div><span>maximedelavier43@gmail.com</span></li>
        <li><div class="icon">📞</div><span>07 66 88 61 70</span></li>
        <li><div class="icon">📍</div><span>Somain, France</span></li>
        <li><div class="icon">🎓</div><span>BUT GEA GEMA — Promotion 2025/2028</span></li>
        <li><div class="icon">🍁</div><span>Erasmus+ Canada — semestre à l'international</span></li>
      </ul>
    </div>
  </section>

  <footer>
    <span class="logo">Maxime Delavier</span>
    <span>Portfolio BUT GEA · 2026</span>
  </footer>

  <!-- MODAL PROJET -->
  <div class="modal-overlay" id="modal-overlay" onclick="closeModalOutside(event)">
    <div class="modal" id="modal">
      <button class="modal-close" onclick="closeModal()">✕</button>
      <h2 id="modal-heading">Modifier le projet</h2>

      <label class="modal-field-label">Catégorie</label>
      <select id="modal-badge">
        <option value="gema">GEMA</option>
        <option value="mgt">Management</option>
        <option value="gest">Gestion</option>
      </select>

      <label class="modal-field-label">Titre du projet</label>
      <input type="text" id="modal-title-input" placeholder="Ex : Étude de cas stratégique, Dossier de management..." />

      <label class="modal-field-label">Description / traces écrites</label>
      <textarea id="modal-desc-input" placeholder="Décris ici ton projet, ce que tu as appris, les méthodes utilisées, les résultats obtenus..."></textarea>

      <label class="modal-field-label">Images (captures, photos, illustrations)</label>
      <div class="upload-zone" onclick="document.getElementById('modal-img-input').click()">
        <div class="upload-icon">🖼️</div>
        <p>Cliquez pour ajouter des images</p>
      </div>
      <input type="file" id="modal-img-input" accept="image/*" multiple onchange="handleImages(event)" style="display:none;" />
      <div class="img-preview-grid" id="img-preview-grid"></div>

      <label class="modal-field-label">Pièces jointes (PDF, Word, etc.)</label>
      <div class="upload-zone" onclick="document.getElementById('modal-file-input').click()">
        <div class="upload-icon">📎</div>
        <p>Cliquez pour ajouter des fichiers</p>
      </div>
      <input type="file" id="modal-file-input" multiple onchange="handleFiles(event)" style="display:none;" />
      <div class="attachments-list" id="attachments-list"></div>

      <div class="modal-actions">
        <button class="btn-save" onclick="saveProject()">💾 Enregistrer</button>
        <button class="btn-cancel" onclick="closeModal()">Annuler</button>
      </div>
    </div>
  </div>

  <script>
    // ── DONNÉES ──────────────────────────────────────────────────────────
    let currentIndex = null;
    let tempImages = [];   // { name, dataUrl }
    let tempFiles  = [];   // { name, dataUrl, type }

    // Chargement depuis localStorage
    let projects = JSON.parse(localStorage.getItem('portfolio_projects') || 'null') || [
      { badge:'gema', title:'Projet 1 — À compléter', desc:'', images:[], files:[] },
      { badge:'mgt',  title:'Projet 2 — À compléter', desc:'', images:[], files:[] },
      { badge:'gest', title:'Projet 3 — À compléter', desc:'', images:[], files:[] },
      { badge:'gema', title:'Projet 4 — À compléter', desc:'', images:[], files:[] },
    ];

    const badgeLabels = { gema:'GEMA', mgt:'Management', gest:'Gestion' };

    // ── RENDU CARTES ─────────────────────────────────────────────────────
    function renderCards() {
      projects.forEach((p, i) => {
        // titre
        document.getElementById('proj-title-' + i).textContent = p.title;
        // description
        document.getElementById('proj-desc-' + i).textContent = p.desc || 'Cliquez pour décrire ce projet, ajouter des images ou des pièces jointes.';
        // badge
        const card = document.querySelector('[data-index="' + i + '"]');
        const badge = card.querySelector('.project-badge');
        badge.className = 'project-badge badge-' + p.badge;
        badge.textContent = badgeLabels[p.badge];
        // bordure si contenu
        const hasContent = p.desc || p.images.length || p.files.length;
        card.classList.toggle('project-has-content', !!hasContent);
        // aperçu
        const preview = document.getElementById('proj-preview-' + i);
        if (hasContent) {
          const parts = [];
          if (p.images.length) parts.push(p.images.length + ' image(s)');
          if (p.files.length)  parts.push(p.files.length + ' fichier(s)');
          preview.querySelector('span').textContent = parts.join(' · ') || 'Description ajoutée';
          preview.style.display = 'flex';
        } else {
          preview.style.display = 'none';
        }
      });
    }

    // ── MODAL ────────────────────────────────────────────────────────────
    function openModal(i) {
      currentIndex = i;
      const p = projects[i];
      document.getElementById('modal-heading').textContent = 'Modifier — ' + p.title;
      document.getElementById('modal-badge').value = p.badge;
      document.getElementById('modal-title-input').value = p.title.replace(' — À compléter','');
      document.getElementById('modal-desc-input').value  = p.desc;

      tempImages = p.images ? JSON.parse(JSON.stringify(p.images)) : [];
      tempFiles  = p.files  ? JSON.parse(JSON.stringify(p.files))  : [];

      renderImgPreview();
      renderFileList();

      document.getElementById('modal-overlay').classList.add('open');
      document.body.style.overflow = 'hidden';
    }

    function closeModal() {
      document.getElementById('modal-overlay').classList.remove('open');
      document.body.style.overflow = '';
      currentIndex = null;
      tempImages = []; tempFiles = [];
    }

    function closeModalOutside(e) {
      if (e.target === document.getElementById('modal-overlay')) closeModal();
    }

    // ── IMAGES ───────────────────────────────────────────────────────────
    function handleImages(e) {
      const files = Array.from(e.target.files);
      files.forEach(f => {
        const reader = new FileReader();
        reader.onload = ev => {
          tempImages.push({ name: f.name, dataUrl: ev.target.result });
          renderImgPreview();
        };
        reader.readAsDataURL(f);
      });
      e.target.value = '';
    }

    function renderImgPreview() {
      const grid = document.getElementById('img-preview-grid');
      grid.innerHTML = '';
      tempImages.forEach((img, idx) => {
        const div = document.createElement('div');
        div.className = 'img-preview-item';
        div.innerHTML = '<img src="' + img.dataUrl + '" alt="' + img.name + '" />'
          + '<button class="remove-img" onclick="removeImg(' + idx + ')">✕</button>';
        grid.appendChild(div);
      });
    }

    function removeImg(idx) { tempImages.splice(idx, 1); renderImgPreview(); }

    // ── FICHIERS ─────────────────────────────────────────────────────────
    function handleFiles(e) {
      const files = Array.from(e.target.files);
      files.forEach(f => {
        const reader = new FileReader();
        reader.onload = ev => {
          tempFiles.push({ name: f.name, dataUrl: ev.target.result, type: f.type });
          renderFileList();
        };
        reader.readAsDataURL(f);
      });
      e.target.value = '';
    }

    function renderFileList() {
      const list = document.getElementById('attachments-list');
      list.innerHTML = '';
      tempFiles.forEach((f, idx) => {
        const div = document.createElement('div');
        div.className = 'attachment-item';
        div.innerHTML = '<span>📄 ' + f.name + '</span>'
          + '<button onclick="removeFile(' + idx + ')" title="Supprimer">✕</button>';
        list.appendChild(div);
      });
    }

    function removeFile(idx) { tempFiles.splice(idx, 1); renderFileList(); }

    // ── SAUVEGARDE ───────────────────────────────────────────────────────
    function saveProject() {
      if (currentIndex === null) return;
      const title = document.getElementById('modal-title-input').value.trim() || ('Projet ' + (currentIndex+1));
      projects[currentIndex] = {
        badge:  document.getElementById('modal-badge').value,
        title:  title,
        desc:   document.getElementById('modal-desc-input').value.trim(),
        images: tempImages,
        files:  tempFiles,
      };
      try { localStorage.setItem('portfolio_projects', JSON.stringify(projects)); } catch(e) {}
      renderCards();
      closeModal();
    }

    // ── CV ────────────────────────────────────────────────────────────────
    function handleCvUpload(e) {
      const file = e.target.files[0];
      if (!file) return;
      const reader = new FileReader();
      reader.onload = ev => {
        try { localStorage.setItem('portfolio_cv', ev.target.result); } catch(err) {}
        showCvBtn(ev.target.result, file.name);
      };
      reader.readAsDataURL(file);
    }

    function showCvBtn(dataUrl, name) {
      const btn = document.getElementById('cv-view-btn');
      btn.href = dataUrl;
      btn.download = name || 'CV_Maxime_Delavier.pdf';
      btn.style.display = 'inline-block';
      document.getElementById('cv-status').textContent = '✅ CV importé : ' + (name || 'cv.pdf');
    }

    // ── INIT ─────────────────────────────────────────────────────────────
    window.addEventListener('DOMContentLoaded', () => {
      renderCards();
      // restaurer CV
      try {
        const cvData = localStorage.getItem('portfolio_cv');
        if (cvData) showCvBtn(cvData, 'CV_Maxime_Delavier.pdf');
      } catch(e) {}
    });

    document.addEventListener('keydown', e => { if (e.key === 'Escape') closeModal(); });
  </script>

</body>
</html>
