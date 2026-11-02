<!DOCTYPE html>
<html lang="pt-BR" data-theme="dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta
    name="description"
    content="Portfólio de José: desenvolvimento de interfaces e experiências digitais."
  >
  <meta name="theme-color" content="#101211">
  <title>José — Portfólio</title>

  <style>
    :root {
      color-scheme: dark;
      --bg: #101211;
      --surface: #191d19;
      --surface-alt: #232a23;
      --text: #f4f7f0;
      --muted: #a9b5a5;
      --border: #354033;
      --accent: #c3f47a;
      --accent-ink: #101211;
      --radius: 24px;
    }

    [data-theme="light"] {
      color-scheme: light;
      --bg: #f5f7f1;
      --surface: #ffffff;
      --surface-alt: #e9eee2;
      --text: #182015;
      --muted: #586550;
      --border: #d3dccb;
    }

    * { box-sizing: border-box; }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 100px;
    }

    body {
      margin: 0;
      background: var(--bg);
      color: var(--text);
      font-family: Inter, system-ui, -apple-system, "Segoe UI", sans-serif;
      line-height: 1.6;
    }

    body.modal-open { overflow: hidden; }
    button, input, textarea, select { font: inherit; }
    button, a { -webkit-tap-highlight-color: transparent; }
    button { cursor: pointer; }
    a { color: inherit; text-decoration: none; }
    h1, h2, h3, p { margin: 0; }
    h1, h2, h3 { line-height: 1.12; }
    [hidden] { display: none !important; }

    :focus-visible {
      outline: 3px solid var(--text);
      outline-offset: 4px;
    }

    ::selection {
      background: var(--accent);
      color: var(--accent-ink);
    }

    .container {
      width: min(1120px, calc(100% - 40px));
      margin-inline: auto;
    }

    .section { padding-block: 80px; }

    .eyebrow {
      margin-bottom: 18px;
      color: var(--muted);
      font-size: .75rem;
      font-weight: 700;
      letter-spacing: .15em;
      text-transform: uppercase;
    }

    .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      min-height: 46px;
      padding: 11px 20px;
      border: 1px solid transparent;
      border-radius: 100px;
      background: var(--accent);
      color: var(--accent-ink);
      font-weight: 700;
      font-size: .88rem;
      transition: transform .2s;
    }

    .button:hover { transform: translateY(-2px); }

    .button.secondary {
      border-color: var(--border);
      background: var(--surface);
      color: var(--text);
    }

    .button.small { min-height: 40px; padding: 8px 15px; font-size: .8rem; }

    .skip-link {
      position: fixed;
      top: -100px;
      left: 16px;
      z-index: 100;
      padding: 10px 20px;
      background: var(--accent);
      color: var(--accent-ink);
      border-radius: 10px;
    }

    .skip-link:focus { top: 10px; }

    /* Cabeçalho */
    .header {
      position: sticky;
      top: 0;
      z-index: 20;
      background: var(--bg);
      border-bottom: 1px solid var(--border);
    }

    .header-inner {
      display: flex;
      align-items: center;
      gap: 24px;
      min-height: 80px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 7px;
      min-width: 0;
      font-size: 1.3rem;
      font-weight: 850;
      letter-spacing: -.05em;
    }

    .logo span:first-child {
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
      max-width: 230px;
    }

    .logo-dot {
      width: 8px;
      height: 8px;
      flex-shrink: 0;
      border-radius: 50%;
      background: var(--accent);
    }

    .nav {
      display: flex;
      gap: 25px;
      margin-left: auto;
      color: var(--muted);
      font-size: .87rem;
    }

    .nav a:hover { color: var(--text); }

    .header-actions { display: flex; align-items: center; gap: 8px; }

    .icon-button {
      display: grid;
      place-items: center;
      width: 42px;
      height: 42px;
      padding: 0;
      border: 1px solid var(--border);
      border-radius: 50%;
      background: var(--surface);
      color: var(--text);
      font-size: 1.15rem;
    }

    #menu-button { display: none; }

    /* Apresentação */
    .hero {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      align-items: center;
      gap: 60px;
      padding-block: 90px 70px;
    }

    .status {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      margin-bottom: 26px;
      padding: 6px 12px;
      border: 1px solid var(--border);
      border-radius: 100px;
      color: var(--muted);
      font-size: .75rem;
    }

    .status::before {
      content: "";
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #7dbf56;
    }

    h1 {
      font-size: clamp(2.8rem, 5.8vw, 4.7rem);
      letter-spacing: -.065em;
      overflow-wrap: anywhere;
    }

    .hero-role {
      display: block;
      margin-top: 10px;
      color: var(--muted);
      font-size: .65em;
      line-height: 1.15;
    }

    .hero-description {
      max-width: 510px;
      margin-top: 24px;
      color: var(--muted);
      white-space: pre-line;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 28px;
    }

    .location { margin-top: 25px; color: var(--muted); font-size: .8rem; }

    .hero-art {
      position: relative;
      display: grid;
      place-items: center;
      min-height: 400px;
      overflow: hidden;
      border: 1px solid var(--border);
      border-radius: 30px;
      background:
        radial-gradient(ellipse at top right, #8dbf4926, transparent 65%),
        var(--surface);
    }

    .art-circle {
      position: absolute;
      width: 290px;
      height: 290px;
      border: 1px dashed var(--border);
      border-radius: 50%;
    }

    .code-window {
      position: relative;
      width: 86%;
      padding: 22px;
      border: 1px solid #3b4934;
      border-radius: 18px;
      background: #141b13;
      color: #edf5e8;
      box-shadow: 0 25px 50px #0004;
      transform: rotate(-5deg);
    }

    .window-top {
      display: flex;
      gap: 6px;
      padding-bottom: 17px;
      border-bottom: 1px solid #34402e;
    }

    .window-top i {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #91a881;
    }

    .window-top span { margin-left: auto; color: #b1c1a7; font-size: .65rem; }

    .code-window pre {
      margin: 22px 0 0;
      white-space: pre-wrap;
      overflow-wrap: anywhere;
      font: .82rem/1.9 ui-monospace, Consolas, monospace;
    }

    .purple { color: #d1b3ff; }
    .green { color: #c3f47a; }

    .art-label {
      position: absolute;
      right: 18px;
      bottom: 28px;
      padding: 12px 16px;
      border-radius: 12px;
      background: var(--accent);
      color: var(--accent-ink);
      font-size: .8rem;
      font-weight: 750;
      transform: rotate(5deg);
    }

    .tech-strip {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      align-items: center;
      gap: 15px 30px;
      padding-block: 24px;
      border-block: 1px solid var(--border);
      font-size: .85rem;
    }

    .tech-label { color: var(--muted); }

    /* Projetos */
    .section-heading {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 25px;
      margin-bottom: 30px;
    }

    h2 { font-size: clamp(2rem, 4vw, 3rem); letter-spacing: -.05em; }

    .filters { display: flex; flex-wrap: wrap; gap: 7px; }

    .filter {
      min-height: 42px;
      padding: 8px 16px;
      border: 1px solid var(--border);
      border-radius: 100px;
      background: transparent;
      color: var(--muted);
      font-size: .8rem;
    }

    .filter[aria-pressed="true"] {
      background: var(--text);
      color: var(--bg);
      border-color: var(--text);
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 24px;
    }

    .project {
      min-width: 0;
      padding: 10px;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      background: var(--surface);
      transition: transform .2s;
    }

    .project:hover { transform: translateY(-4px); }

    .project-preview {
      display: grid;
      place-items: center;
      height: 225px;
      overflow: hidden;
      border-radius: 16px;
      background: #d9e8ca;
      color: #293d20;
    }

    .project:nth-child(2) .project-preview { background: #dbd0ed; color: #4f386a; }
    .project:nth-child(3) .project-preview { background: #efdbc8; color: #76513a; }
    .project:nth-child(4) .project-preview { background: #cbdfea; color: #315569; }

    .preview-window {
      width: 76%;
      padding: 22px;
      border: 1px solid #ffffff80;
      border-radius: 14px;
      background: #ffffffb8;
      box-shadow: 0 20px 30px #0001;
      transform: rotate(-5deg);
    }

    .preview-dots { margin-bottom: 20px; font-size: .6rem; letter-spacing: 4px; }
    .preview-icon { font-size: 2.7rem; line-height: 1; }
    .preview-line { width: 70%; height: 7px; margin-top: 17px; border-radius: 5px; background: currentColor; opacity: .22; }
    .preview-line.short { width: 45%; margin-top: 9px; }

    .project-info { padding: 20px 12px 14px; }
    .project-info h3 { font-size: 1.2rem; overflow-wrap: anywhere; }
    .project-description { margin-top: 10px; color: var(--muted); font-size: .88rem; white-space: pre-line; overflow-wrap: anywhere; }
    .tags { display: flex; flex-wrap: wrap; gap: 7px; margin-top: 15px; }
    .tags span { padding: 3px 9px; border: 1px solid var(--border); border-radius: 6px; color: var(--muted); font-size: .68rem; }
    .project-link { display: inline-block; margin-top: 18px; font-size: .85rem; font-weight: 700; }
    .project-link:hover { text-decoration: underline; }
    .project-status { margin-top: 20px; color: var(--muted); font-size: .78rem; }

    /* Sobre e contato */
    .about {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 65px;
      border-top: 1px solid var(--border);
    }

    .about-text {
      margin-top: 24px;
      color: var(--muted);
      white-space: pre-line;
      overflow-wrap: anywhere;
    }

    .services { display: grid; gap: 14px; }

    .service {
      padding: 24px;
      border: 1px solid var(--border);
      border-radius: 18px;
      background: var(--surface);
    }

    .service h3 { font-size: 1rem; margin-bottom: 8px; }
    .service p { font-size: .86rem; color: var(--muted); }

    .contact { padding-top: 0; }

    .contact-panel {
      padding: 65px 25px;
      border-radius: 30px;
      background: var(--accent);
      color: var(--accent-ink);
      text-align: center;
    }

    .contact-panel h2 { max-width: 700px; margin-inline: auto; }
    .contact-panel p { margin-top: 20px; }
    .contact-panel .button { margin-top: 28px; background: var(--accent-ink); color: var(--accent); }

    .contact-email {
      display: block;
      width: fit-content;
      max-width: 100%;
      margin: 20px auto 0;
      overflow-wrap: anywhere;
      text-decoration: underline;
      text-underline-offset: 4px;
      font-size: .88rem;
    }

    .footer-inner {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 18px;
      padding-block: 26px;
      border-top: 1px solid var(--border);
      color: var(--muted);
      font-size: .8rem;
    }

    /* Editor */
    .editor {
      width: min(820px, calc(100% - 24px));
      max-height: 90dvh;
      padding: 0;
      border: 1px solid var(--border);
      border-radius: 22px;
      background: var(--bg);
      color: var(--text);
      box-shadow: 0 25px 100px #0006;
    }

    .editor::backdrop {
      background: #0009;
      backdrop-filter: blur(5px);
    }

    .editor-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      padding: 22px;
      border-bottom: 1px solid var(--border);
    }

    .editor-header h2 { font-size: 1.5rem; }

    .editor-body { padding: 24px; }

    .editor-note {
      margin-bottom: 25px;
      padding: 15px;
      border: 1px solid var(--border);
      border-radius: 12px;
      background: var(--surface);
      color: var(--muted);
      font-size: .85rem;
    }

    fieldset {
      min-width: 0;
      margin: 0 0 25px;
      padding: 20px;
      border: 1px solid var(--border);
      border-radius: 16px;
    }

    legend { padding-inline: 8px; font-weight: 700; }

    .form-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 16px;
    }

    .field { display: grid; gap: 7px; min-width: 0; }
    .field.full { grid-column: 1 / -1; }
    .field label { font-size: .84rem; font-weight: 650; }

    .field input,
    .field textarea,
    .field select {
      width: 100%;
      min-width: 0;
      padding: 11px 12px;
      border: 1px solid var(--border);
      border-radius: 9px;
      background: var(--surface);
      color: var(--text);
    }

    .field textarea { resize: vertical; min-height: 105px; }
    .field input[type="color"] { height: 47px; padding: 5px; cursor: pointer; }

    .editor-project {
      margin-top: 16px;
      padding-top: 20px;
      border-top: 1px solid var(--border);
    }

    .editor-project h3 { margin-bottom: 15px; font-size: 1rem; }

    .editor-footer {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      padding-top: 4px;
    }

    .editor-feedback { min-height: 26px; margin-top: 16px; color: var(--muted); font-size: .85rem; }

    .toast {
      position: fixed;
      bottom: 22px;
      left: 50%;
      z-index: 40;
      width: max-content;
      max-width: calc(100% - 32px);
      padding: 12px 20px;
      border: 1px solid var(--border);
      border-radius: 12px;
      background: var(--surface);
      color: var(--text);
      box-shadow: 0 10px 35px #0004;
      transform: translateX(-50%);
      font-size: .85rem;
      text-align: center;
    }

    @media (max-width: 900px) {
      .hero { gap: 30px; }
      .hero-art { min-height: 360px; }
      .code-window { padding: 16px; }
      .code-window pre { font-size: .72rem; }
      .section-heading { flex-direction: column; align-items: start; }
      .nav { gap: 16px; }
      .header-inner { gap: 15px; }
      .about { gap: 35px; }
    }

    @media (max-width: 700px) {
      .container { width: calc(100% - 32px); }
      .section { padding-block: 55px; }
      .header-inner { flex-wrap: wrap; min-height: 72px; gap: 0; }
      .header-actions { margin-left: auto; }
      .logo span:first-child { max-width: 130px; }
      #menu-button { display: grid; }

      .nav {
        display: none;
        order: 3;
        flex-direction: column;
        gap: 0;
        width: 100%;
        margin: 0;
        padding-block: 10px;
      }

      .nav.open { display: flex; }
      .nav a { padding: 11px; }

      .hero { grid-template-columns: 1fr; padding-block: 50px; gap: 35px; }
      .hero h1 { font-size: clamp(2.7rem, 12vw, 4rem); }
      .hero-art { min-height: 330px; }
      .code-window { max-width: 350px; padding: 20px; }
      .code-window pre { font-size: .8rem; }
      .projects-grid, .about { grid-template-columns: 1fr; }
      .tech-label { width: 100%; text-align: center; }
      .contact { padding-top: 0; }
      .contact-panel { padding: 45px 20px; }
      .footer-inner { justify-content: center; text-align: center; }
      .form-grid { grid-template-columns: 1fr; }
      .editor-body { padding: 16px; }
      fieldset { padding: 15px; }
      .editor-footer .button { flex: 1 1 100%; }
    }

    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after { transition: none !important; animation: none !important; }
    }
  </style>
</head>

<body id="inicio">
  <a class="skip-link" href="#conteudo">Pular para o conteúdo</a>

  <header class="header">
    <div class="container header-inner">
      <a class="logo" href="#inicio" aria-label="Voltar ao início">
        <span id="logo-name">José</span>
        <span class="logo-dot" aria-hidden="true"></span>
      </a>

      <nav id="navigation" class="nav" aria-label="Navegação principal">
        <a href="#projetos">Projetos</a>
        <a href="#sobre">Sobre mim</a>
        <a href="#contato">Contato ↗</a>
      </nav>

      <div class="header-actions">
        <button type="button" id="open-editor" class="button small">✎ Editar</button>
        <button type="button" id="theme-button" class="icon-button" aria-label="Ativar tema claro">☀</button>
        <button
          type="button"
          id="menu-button"
          class="icon-button"
          aria-label="Abrir menu"
          aria-expanded="false"
          aria-controls="navigation"
        >☰</button>
      </div>
    </div>
  </header>

  <main id="conteudo">
    <section class="container hero" aria-labelledby="hero-title">
      <div>
        <span class="status" id="availability">Disponível para novos projetos</span>

        <h1 id="hero-title">
          Olá, eu sou <span id="hero-name">José</span>.
          <span class="hero-role" id="hero-role">Desenvolvedor front-end.</span>
        </h1>

        <p class="hero-description" id="hero-description"></p>

        <div class="hero-actions">
          <a class="button" href="#projetos">Explorar projetos ↗</a>
          <a class="button secondary" href="#contato">Entre em contato</a>
        </div>

        <p class="location" id="location"></p>
      </div>

      <div class="hero-art" aria-hidden="true">
        <div class="art-circle"></div>
        <div class="code-window">
          <div class="window-top">
            <i></i><i></i><i></i>
            <span>portfolio.js</span>
          </div>
          <pre><code><span class="purple">const</span> developer = {
  name: <span class="green" id="code-name">"José"</span>,
  passion: [
    <span class="green">"design"</span>,
    <span class="green">"código"</span>
  ],
  readyToCreate: <span class="purple">true</span>
};

developer.<span class="green">build</span>();</code></pre>
        </div>
        <span class="art-label">✦ Ideias que ganham vida.</span>
      </div>
    </section>

    <div class="container tech-strip" id="technologies" aria-label="Tecnologias"></div>

    <section class="container section" id="projetos" aria-labelledby="projects-title">
      <div class="section-heading">
        <div>
          <p class="eyebrow">Do conceito à experiência</p>
          <h2 id="projects-title">Projetos em destaque.</h2>
        </div>

        <div class="filters" role="group" aria-label="Filtrar projetos">
          <button type="button" class="filter" data-filter="all" aria-pressed="true">Todos</button>
          <button type="button" class="filter" data-filter="web" aria-pressed="false">Websites</button>
          <button type="button" class="filter" data-filter="app" aria-pressed="false">Aplicações</button>
        </div>
      </div>

      <div class="projects-grid" id="projects-grid"></div>
      <p class="project-status" id="project-status" role="status" aria-live="polite"></p>
    </section>

    <section class="container section about" id="sobre" aria-labelledby="about-title">
      <div>
        <p class="eyebrow">Um pouco sobre mim</p>
        <h2 id="about-title">Tecnologia com um olhar humano.</h2>
        <p class="about-text" id="about-text"></p>
      </div>

      <div class="services">
        <article class="service">
          <h3>01 / Desenvolvimento front-end</h3>
          <p>Interfaces responsivas e acessíveis, construídas com atenção a cada detalhe.</p>
        </article>
        <article class="service">
          <h3>02 / Design de interfaces</h3>
          <p>Experiências intuitivas que conectam identidade visual e funcionalidade.</p>
        </article>
        <article class="service">
          <h3>03 / Performance e evolução</h3>
          <p>Melhorias contínuas para produtos digitais rápidos e bem organizados.</p>
        </article>
      </div>
    </section>

    <section class="container section contact" id="contato" aria-labelledby="contact-title">
      <div class="contact-panel">
        <h2 id="contact-title">Vamos construir algo que faça a diferença?</h2>
        <p>Conte sua ideia. Vamos encontrar a melhor forma de colocá-la no mundo.</p>
        <a class="button" id="contact-button" href="mailto:junhoruan93@gmail.com">Vamos conversar ↗</a>
        <a class="contact-email" id="contact-email" href="mailto:junhoruan93@gmail.com">junhoruan93@gmail.com</a>
      </div>
    </section>
  </main>

  <footer class="container">
    <div class="footer-inner">
      <p>© <span id="year"></span> <span id="footer-name">José</span>. Feito com cuidado e código.</p>
      <a href="#inicio">Voltar ao topo ↑</a>
    </div>
  </footer>

  <!-- Editor integrado -->
  <dialog class="editor" id="editor" aria-labelledby="editor-title" aria-describedby="editor-description">
    <div class="editor-header">
      <h2 id="editor-title">Personalize seu portfólio</h2>
      <button type="button" class="icon-button" id="close-editor" aria-label="Fechar editor">×</button>
    </div>

    <form id="editor-form" class="editor-body">
      <p class="editor-note" id="editor-description">
        Edite os campos e clique em “Salvar alterações”.
        As mudanças ficam neste navegador. Para publicar, baixe o HTML atualizado.
        Este painel não possui autenticação.
      </p>

      <fieldset>
        <legend>Informações principais</legend>

        <div class="form-grid">
          <div class="field">
            <label for="edit-name">Seu nome</label>
            <input id="edit-name" name="name" required maxlength="60">
          </div>

          <div class="field">
            <label for="edit-role">Profissão / título</label>
            <input id="edit-role" name="role" required maxlength="100">
          </div>

          <div class="field">
            <label for="edit-email">E-mail</label>
            <input id="edit-email" name="email" type="email" required maxlength="150">
          </div>

          <div class="field">
            <label for="edit-location">Localização</label>
            <input id="edit-location" name="location" required maxlength="120">
          </div>

          <div class="field full">
            <label for="edit-availability">Mensagem de disponibilidade</label>
            <input id="edit-availability" name="availability" required maxlength="100">
          </div>

          <div class="field full">
            <label for="edit-description">Apresentação</label>
            <textarea id="edit-description" name="description" required maxlength="700"></textarea>
          </div>

          <div class="field full">
            <label for="edit-technologies">Tecnologias — separadas por vírgulas</label>
            <input id="edit-technologies" name="technologies" required maxlength="250">
          </div>

          <div class="field full">
            <label for="edit-about">Sobre mim</label>
            <textarea id="edit-about" name="about" required maxlength="2000" rows="6"></textarea>
          </div>

          <div class="field">
            <label for="edit-accent">Cor de destaque</label>
            <input id="edit-accent" name="accent" type="color">
          </div>
        </div>
      </fieldset>

      <fieldset>
        <legend>Seus projetos</legend>
        <p class="project-status">
          Substitua os exemplos pelos seus trabalhos. Os links são opcionais.
        </p>
        <div id="project-fields"></div>
      </fieldset>

      <div class="editor-footer">
        <button class="button" type="submit">Salvar alterações</button>
        <button class="button secondary" type="button" id="download-html">Baixar HTML atualizado</button>
        <button class="button secondary" type="button" id="reset-data">Restaurar versão do arquivo</button>
      </div>

      <p class="editor-feedback" id="editor-feedback" role="status" aria-live="polite"></p>
    </form>
  </dialog>

  <div class="toast" id="toast" role="status" aria-live="polite" hidden></div>

  <!-- Dados incorporados. O download do HTML atualiza este bloco. -->
  <script id="portfolio-data" type="application/json">
  {
    "name": "José",
    "role": "Desenvolvedor front-end.",
    "email": "junhoruan93@gmail.com",
    "location": "Brasil · Disponível para projetos remotos",
    "availability": "Disponível para novos projetos",
    "description": "Transformo ideias em interfaces modernas, acessíveis e cheias de personalidade. Gosto de unir design e código para criar experiências digitais que fazem sentido.",
    "technologies": "HTML, CSS, JavaScript, TypeScript, React, Figma",
    "about": "Acredito que um bom produto digital começa entendendo as pessoas. Por isso, combino desenvolvimento, design e atenção aos detalhes para criar experiências intuitivas.\n\nGosto de interfaces simples, código bem organizado e projetos que resolvem problemas reais. Estou sempre aprendendo e buscando novos desafios.",
    "accent": "#c3f47a",
    "projects": [
      {
        "title": "Finflow Dashboard",
        "description": "Projeto conceitual de um painel financeiro com visualização clara de receitas e despesas.",
        "category": "app",
        "tags": "React, TypeScript, Dashboard",
        "url": ""
      },
      {
        "title": "Forma Studio",
        "description": "Projeto conceitual de um site criativo para um estúdio de design e identidade visual.",
        "category": "web",
        "tags": "HTML, CSS, JavaScript",
        "url": ""
      },
      {
        "title": "Terra Concept",
        "description": "Projeto conceitual de uma loja virtual minimalista para produtos artesanais.",
        "category": "web",
        "tags": "React, UI Design, E-commerce",
        "url": ""
      },
      {
        "title": "Orbit Workspace",
        "description": "Projeto conceitual de uma aplicação para organizar tarefas e manter o foco.",
        "category": "app",
        "tags": "TypeScript, React, Produtividade",
        "url": ""
      }
    ]
  }
  </script>

  <script>
    (() => {
      "use strict";

      const $ = id => document.getElementById(id);
      const clone = value => JSON.parse(JSON.stringify(value));

      const fileData = JSON.parse($("portfolio-data").textContent);

      // Cada versão exportada recebe sua própria chave, evitando que dados
      // de uma versão anterior sobrescrevam a personalização do novo arquivo.
      const revision = document.documentElement.dataset.revision || "original";
      const STORAGE_KEY = "jose-portfolio-v2-" + revision;
      const THEME_KEY = "jose-portfolio-theme";

      const editor = $("editor");
      const form = $("editor-form");
      const baseFields = [
        "name", "role", "email", "location", "availability",
        "description", "technologies", "about", "accent"
      ];

      let data = clone(fileData);
      let activeFilter = "all";
      let toastTimer;

      function validData(value) {
        return value &&
          baseFields.every(key => typeof value[key] === "string") &&
          /^#[0-9a-f]{6}$/i.test(value.accent) &&
          Array.isArray(value.projects) &&
          value.projects.length === fileData.projects.length &&
          value.projects.every(project =>
            project &&
            ["title", "description", "category", "tags", "url"]
              .every(key => typeof project[key] === "string") &&
            ["web", "app"].includes(project.category)
          );
      }

      try {
        const saved = JSON.parse(localStorage.getItem(STORAGE_KEY));
        if (validData(saved)) data = saved;
      } catch {
        // Se o armazenamento estiver indisponível, usa os dados do arquivo.
      }

      function createElement(tag, className, text) {
        const element = document.createElement(tag);
        if (className) element.className = className;
        if (text !== undefined) element.textContent = text;
        return element;
      }

      function splitList(text) {
        return text.split(",").map(item => item.trim()).filter(Boolean);
      }

      function safeURL(value) {
        if (!value.trim()) return "";
        try {
          const url = new URL(value);
          return ["http:", "https:"].includes(url.protocol) ? url.href : "";
        } catch {
          return "";
        }
      }

      // Seleciona texto preto ou branco para contrastar com a cor escolhida.
      function accentInk(hex) {
        const channels = hex.slice(1).match(/.{2}/g).map(part => {
          const value = parseInt(part, 16) / 255;
          return value <= .04045
            ? value / 12.92
            : Math.pow((value + .055) / 1.055, 2.4);
        });
        const luminance =
          .2126 * channels[0] + .7152 * channels[1] + .0722 * channels[2];

        return luminance > .179 ? "#000000" : "#ffffff";
      }

      function renderProjects() {
        const grid = $("projects-grid");
        grid.replaceChildren();

        const symbols = ["◈", "✳", "◒", "▦"];
        let visible = 0;

        data.projects.forEach((project, index) => {
          const article = createElement("article", "project");

          article.hidden =
            activeFilter !== "all" && project.category !== activeFilter;

          if (!article.hidden) visible++;

          const preview = createElement("div", "project-preview");
          preview.setAttribute("aria-hidden", "true");

          const previewWindow = createElement("div", "preview-window");
          previewWindow.append(
            createElement("div", "preview-dots", "● ● ●"),
            createElement("div", "preview-icon", symbols[index % symbols.length]),
            createElement("div", "preview-line"),
            createElement("div", "preview-line short")
          );

          preview.append(previewWindow);

          const info = createElement("div", "project-info");
          info.append(
            createElement("h3", "", project.title),
            createElement("p", "project-description", project.description)
          );

          const tags = createElement("div", "tags");
          splitList(project.tags).forEach(tag => {
            tags.append(createElement("span", "", tag));
          });
          info.append(tags);

          const url = safeURL(project.url);

          if (url) {
            const link = createElement("a", "project-link", "Ver projeto ↗");
            link.href = url;
            link.target = "_blank";
            link.rel = "noopener noreferrer";
            link.setAttribute("aria-label", `Ver ${project.title} em nova aba`);
            info.append(link);
          }

          article.append(preview, info);
          grid.append(article);
        });

        $("project-status").textContent =
          `${visible} ${visible === 1 ? "projeto exibido" : "projetos exibidos"}.`;
      }

      function render() {
        document.title = `${data.name} — ${data.role}`;
        document.querySelector('meta[name="description"]')
          .setAttribute("content", `Portfólio de ${data.name}. ${data.description}`);

        document.documentElement.style.setProperty("--accent", data.accent);
        document.documentElement.style.setProperty("--accent-ink", accentInk(data.accent));

        $("logo-name").textContent = data.name;
        $("hero-name").textContent = data.name;
        $("hero-role").textContent = data.role;
        $("hero-description").textContent = data.description;
        $("availability").textContent = data.availability;
        $("location").textContent = data.location;
        $("about-text").textContent = data.about;
        $("footer-name").textContent = data.name;
        $("code-name").textContent = JSON.stringify(data.name);
        $("year").textContent = new Date().getFullYear();

        const mailto = "mailto:" + encodeURIComponent(data.email);
        $("contact-button").href = mailto + "?subject=Vamos%20criar%20um%20projeto";
        $("contact-email").href = mailto;
        $("contact-email").textContent = data.email;

        const technologies = $("technologies");
        technologies.replaceChildren(
          createElement("span", "tech-label", "Minha caixa de ferramentas")
        );

        splitList(data.technologies).forEach(technology => {
          technologies.append(createElement("strong", "", technology));
        });

        renderProjects();
      }

      function notify(message) {
        clearTimeout(toastTimer);
        $("toast").textContent = message;
        $("toast").hidden = false;
        toastTimer = setTimeout(() => {
          $("toast").hidden = true;
        }, 4500);
      }

      // Editor: campos de projeto são montados sem inserir HTML do usuário.
      function addProjectField(container, index, key, labelText, value, type) {
        const wrapper = createElement("div", "field");
        if (key === "description" || key === "url") wrapper.classList.add("full");

        const id = `project-${index}-${key}`;
        const label = createElement("label", "", labelText);
        label.htmlFor = id;

        let input;

        if (key === "description") {
          input = document.createElement("textarea");
          input.maxLength = 500;
        } else if (key === "category") {
          input = document.createElement("select");

          [
            ["web", "Website"],
            ["app", "Aplicação"]
          ].forEach(([optionValue, text]) => {
            const option = createElement("option", "", text);
            option.value = optionValue;
            input.append(option);
          });
        } else {
          input = document.createElement("input");
          input.type = type || "text";
          input.maxLength = key === "url" ? 1000 : 160;
          if (key === "url") input.placeholder = "https://seu-projeto.com";
        }

        input.id = id;
        input.name = id;
        input.required = key !== "url";
        input.value = value;

        input.addEventListener("input", () => input.setCustomValidity(""));

        wrapper.append(label, input);
        container.append(wrapper);
      }

      function populateEditor() {
        baseFields.forEach(key => {
          form.elements.namedItem(key).value = data[key];
        });

        $("project-fields").replaceChildren();

        data.projects.forEach((project, index) => {
          const block = createElement("div", "editor-project");
          block.append(createElement("h3", "", `Projeto ${index + 1}`));

          const grid = createElement("div", "form-grid");

          addProjectField(grid, index, "title", "Título", project.title);
          addProjectField(grid, index, "category", "Categoria", project.category);
          addProjectField(grid, index, "description", "Descrição", project.description);
          addProjectField(grid, index, "tags", "Tecnologias — separadas por vírgulas", project.tags);
          addProjectField(grid, index, "url", "Link do projeto (opcional)", project.url, "url");

          block.append(grid);
          $("project-fields").append(block);
        });

        $("editor-feedback").textContent = "";
      }

      function readForm() {
        // Impede campos obrigatórios compostos apenas por espaços.
        form.querySelectorAll("input[required], textarea[required]").forEach(input => {
          input.setCustomValidity(
            input.value.trim() ? "" : "Preencha este campo."
          );
        });

        data.projects.forEach((_, index) => {
          const input = $(`project-${index}-url`);
          input.setCustomValidity(
            input.value.trim() && !safeURL(input.value)
              ? "Use um endereço completo começando com https:// ou http://."
              : ""
          );
        });

        if (!form.reportValidity()) return null;

        const next = {};
        baseFields.forEach(key => {
          next[key] = form.elements.namedItem(key).value.trim();
        });

        next.projects = data.projects.map((_, index) => {
          const project = {};
          ["title", "description", "category", "tags", "url"].forEach(key => {
            project[key] = $(`project-${index}-${key}`).value.trim();
          });
          return project;
        });

        return next;
      }

      function saveData(next) {
        data = next;
        render();

        try {
          localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
          return true;
        } catch {
          return false;
        }
      }

      $("open-editor").addEventListener("click", () => {
        populateEditor();
        editor.showModal();
        document.body.classList.add("modal-open");
      });

      $("close-editor").addEventListener("click", () => editor.close());

      editor.addEventListener("close", () => {
        document.body.classList.remove("modal-open");
      });

      form.addEventListener("input", event => {
        if (typeof event.target.setCustomValidity === "function") {
          event.target.setCustomValidity("");
        }
      });

      form.addEventListener("submit", event => {
        event.preventDefault();
        const next = readForm();
        if (!next) return;

        const persisted = saveData(next);
        editor.close();

        notify(persisted
          ? "Alterações salvas neste navegador!"
          : "Alterações aplicadas. Baixe o HTML: o navegador não permitiu salvar localmente."
        );
      });

      $("reset-data").addEventListener("click", () => {
        const confirmed = confirm(
          "Restaurar os dados incorporados neste arquivo? As alterações locais serão substituídas."
        );
        if (!confirmed) return;

        const persisted = saveData(clone(fileData));
        populateEditor();

        $("editor-feedback").textContent = persisted
          ? "Versão original deste arquivo restaurada e salva."
          : "Versão restaurada nesta sessão. O armazenamento local está indisponível.";
      });

      // Exporta uma cópia completa e funcional, com os dados já incorporados.
      $("download-html").addEventListener("click", () => {
        const next = readForm();
        if (!next) return;

        saveData(next);

        const copy = document.documentElement.cloneNode(true);
        copy.dataset.revision =
          Date.now().toString(36) + Math.random().toString(36).slice(2, 8);

        copy.querySelector("body").classList.remove("modal-open");
        copy.querySelector("#editor").removeAttribute("open");
        copy.querySelector("#toast").hidden = true;
        copy.querySelector("#editor-feedback").textContent = "";
        copy.querySelector("#navigation").classList.remove("open");
        copy.querySelector("#menu-button").setAttribute("aria-expanded", "false");
        copy.querySelector("#menu-button").setAttribute("aria-label", "Abrir menu");

        // Exporta a lista completa, independentemente do filtro em uso.
        copy.querySelectorAll(".project").forEach(project => {
          project.hidden = false;
        });

        copy.querySelectorAll("[data-filter]").forEach(button => {
          button.setAttribute("aria-pressed", String(button.dataset.filter === "all"));
        });

        // Escape de "<" impede que textos encerrem o bloco de dados JSON.
        copy.querySelector("#portfolio-data").textContent =
          JSON.stringify(data, null, 2)
            .replace(/</g, "\\u003c")
            .replace(/\u2028/g, "\\u2028")
            .replace(/\u2029/g, "\\u2029");

        const html = "<!DOCTYPE html>\n" + copy.outerHTML;
        const blob = new Blob([html], { type: "text/html;charset=utf-8" });
        const objectURL = URL.createObjectURL(blob);
        const link = document.createElement("a");

        link.href = objectURL;
        link.download = "index.html";
        document.body.append(link);
        link.click();
        link.remove();

        setTimeout(() => URL.revokeObjectURL(objectURL), 10000);

        $("editor-feedback").textContent =
          "Download solicitado! Use o arquivo baixado para substituir a versão publicada.";
      });

      // Filtros
      document.querySelectorAll("[data-filter]").forEach(button => {
        button.addEventListener("click", () => {
          activeFilter = button.dataset.filter;

          document.querySelectorAll("[data-filter]").forEach(item => {
            item.setAttribute("aria-pressed", String(item === button));
          });

          renderProjects();
        });
      });

      // Menu mobile
      function setMenu(open) {
        $("navigation").classList.toggle("open", open);
        $("menu-button").setAttribute("aria-expanded", String(open));
        $("menu-button").setAttribute("aria-label", open ? "Fechar menu" : "Abrir menu");
      }

      $("menu-button").addEventListener("click", () => {
        setMenu($("menu-button").getAttribute("aria-expanded") !== "true");
      });

      $("navigation").querySelectorAll("a").forEach(link => {
        link.addEventListener("click", () => setMenu(false));
      });

      document.addEventListener("keydown", event => {
        if (
          event.key === "Escape" &&
          !editor.open &&
          $("menu-button").getAttribute("aria-expanded") === "true"
        ) {
          setMenu(false);
          $("menu-button").focus();
        }
      });

      window.addEventListener("resize", () => {
        if (window.innerWidth > 700) setMenu(false);
      });

      // Tema
      function setTheme(theme) {
        const dark = theme === "dark";
        document.documentElement.dataset.theme = theme;
        $("theme-button").textContent = dark ? "☀" : "☾";
        $("theme-button").setAttribute(
          "aria-label",
          dark ? "Ativar tema claro" : "Ativar tema escuro"
        );

        document.querySelector('meta[name="theme-color"]')
          .setAttribute("content", dark ? "#101211" : "#f5f7f1");
      }

      let initialTheme = document.documentElement.dataset.theme;

      try {
        const storedTheme = localStorage.getItem(THEME_KEY);
        if (["dark", "light"].includes(storedTheme)) initialTheme = storedTheme;
      } catch {}

      setTheme(initialTheme);

      $("theme-button").addEventListener("click", () => {
        const theme =
          document.documentElement.dataset.theme === "dark" ? "light" : "dark";

        setTheme(theme);

        try {
          localStorage.setItem(THEME_KEY, theme);
        } catch {}
      });

      render();
    })();
  </script>
</body>
</html>
