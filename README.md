<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Rubenilson Júnior | Portfólio TI</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, #0f172a, #111827, #1e293b);
      color: #f8fafc;
      line-height: 1.6;
    }

    .container {
      width: 90%;
      max-width: 1200px;
      margin: auto;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 1000;
      backdrop-filter: blur(12px);
      background: rgba(15, 23, 42, 0.75);
      border-bottom: 1px solid rgba(255,255,255,0.08);
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 18px 0;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 800;
      color: #38bdf8;
    }

    .nav-links {
      display: flex;
      gap: 20px;
      list-style: none;
    }

    .nav-links a {
      color: #e2e8f0;
      text-decoration: none;
      font-weight: 500;
      transition: 0.3s;
    }

    .nav-links a:hover { color: #38bdf8; }

    .menu-toggle {
      display: none;
      font-size: 2rem;
      cursor: pointer;
    }

    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 80px 0;
    }

    .hero-content {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 50px;
      align-items: center;
    }

    .badge {
      display: inline-block;
      background: rgba(56, 189, 248, 0.15);
      color: #38bdf8;
      border: 1px solid rgba(56, 189, 248, 0.35);
      padding: 8px 16px;
      border-radius: 999px;
      font-size: 0.9rem;
      margin-bottom: 20px;
    }

    .hero h1 {
      font-size: 3.3rem;
      line-height: 1.1;
      margin-bottom: 20px;
    }

    .hero h1 span { color: #38bdf8; }

    .hero p {
      font-size: 1.08rem;
      color: #cbd5e1;
      max-width: 650px;
      margin-bottom: 30px;
    }

    .buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
    }

    .btn {
      display: inline-block;
      padding: 14px 24px;
      border-radius: 14px;
      text-decoration: none;
      font-weight: 600;
      transition: 0.3s;
    }

    .btn-primary {
      background: #38bdf8;
      color: #0f172a;
    }

    .btn-primary:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 30px rgba(56, 189, 248, 0.35);
    }

    .btn-secondary {
      border: 1px solid rgba(255,255,255,0.15);
      color: #f8fafc;
      background: rgba(255,255,255,0.03);
    }

    .btn-secondary:hover {
      border-color: #38bdf8;
      color: #38bdf8;
    }

    .hero-card, .card, .project-card, .contact-card {
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 24px;
      backdrop-filter: blur(10px);
      box-shadow: 0 10px 30px rgba(0,0,0,0.25);
    }

    .hero-card {
      padding: 30px;
      animation: float 4s ease-in-out infinite;
    }

    .hero-card h3 {
      color: #38bdf8;
      margin-bottom: 12px;
      font-size: 1.4rem;
    }

    .hero-card ul {
      list-style: none;
      display: grid;
      gap: 12px;
      color: #e2e8f0;
    }

    .hero-card li::before {
      content: '✔';
      color: #38bdf8;
      margin-right: 10px;
    }

    section {
      padding: 90px 0;
    }

    .section-title {
      font-size: 2.2rem;
      margin-bottom: 15px;
      text-align: center;
    }

    .section-subtitle {
      text-align: center;
      color: #cbd5e1;
      max-width: 700px;
      margin: 0 auto 50px;
    }

    .about-grid, .skills-grid, .projects-grid, .contact-grid, .stats-grid {
      display: grid;
      gap: 25px;
    }

    .about-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .card {
      padding: 28px;
    }

    .card h3 {
      color: #38bdf8;
      margin-bottom: 12px;
    }

    .skills-grid {
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    }

    .skill-item {
      padding: 22px;
      text-align: center;
    }

    .skill-item h4 {
      margin-bottom: 8px;
      color: #38bdf8;
    }

    .projects-grid {
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    }

    .project-card {
      padding: 28px;
      transition: 0.3s;
    }

    .project-card:hover {
      transform: translateY(-8px);
      border-color: rgba(56, 189, 248, 0.35);
    }

    .project-card h3 {
      margin-bottom: 12px;
      color: #38bdf8;
    }

    .project-card p {
      color: #cbd5e1;
      margin-bottom: 18px;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-bottom: 20px;
    }

    .tag {
      background: rgba(56, 189, 248, 0.15);
      color: #7dd3fc;
      padding: 8px 12px;
      border-radius: 999px;
      font-size: 0.85rem;
    }

    .stats-grid {
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      margin-top: 50px;
    }

    .stat-box {
      text-align: center;
      padding: 28px;
    }

    .stat-box h3 {
      font-size: 2rem;
      color: #38bdf8;
    }

    .contact-grid {
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }

    .contact-card {
      padding: 28px;
      text-align: center;
    }

    .contact-card h3 {
      color: #38bdf8;
      margin-bottom: 10px;
    }

    .contact-card a {
      color: #f8fafc;
      text-decoration: none;
      word-break: break-word;
    }

    .contact-card a:hover { color: #38bdf8; }

    footer {
      text-align: center;
      padding: 30px 20px;
      color: #94a3b8;
      border-top: 1px solid rgba(255,255,255,0.08);
    }

    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.8s ease;
    }

    .reveal.active {
      opacity: 1;
      transform: translateY(0);
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-12px); }
    }

    @media (max-width: 900px) {
      .hero-content, .about-grid {
        grid-template-columns: 1fr;
      }

      .hero h1 { font-size: 2.5rem; }
    }

    @media (max-width: 768px) {
      .nav-links {
        position: absolute;
        top: 75px;
        right: 5%;
        width: 220px;
        flex-direction: column;
        background: rgba(15, 23, 42, 0.98);
        border: 1px solid rgba(255,255,255,0.08);
        border-radius: 18px;
        padding: 20px;
        display: none;
      }

      .nav-links.active { display: flex; }
      .menu-toggle { display: block; }
      .hero h1 { font-size: 2.1rem; }
    }
  </style>
</head>
<body>

  <header>
    <div class="container">
      <nav>
        <div class="logo">Rubenilson.dev</div>
        <ul class="nav-links" id="navLinks">
          <li><a href="#inicio">Início</a></li>
          <li><a href="#sobre">Sobre</a></li>
          <li><a href="#habilidades">Habilidades</a></li>
          <li><a href="#projetos">Projetos</a></li>
          <li><a href="#contato">Contato</a></li>
        </ul>
        <div class="menu-toggle" id="menuToggle">☰</div>
      </nav>
    </div>
  </header>

  <section class="hero" id="inicio">
    <div class="container hero-content">
      <div class="reveal">
        <span class="badge">Portfólio Profissional • TI & Desenvolvimento Web</span>
        <h1>Olá, eu sou <span>Rubenilson Júnior</span></h1>
        <p>
          Estudante de Análise e Desenvolvimento de Sistemas, com foco em suporte técnico,
          manutenção de computadores e desenvolvimento web. Busco oportunidades para crescer
          na área de Tecnologia da Informação e entregar soluções com organização, dedicação e prática.
        </p>
        <div class="buttons">
          <a href="https://github.com/ruben0192/Projeto.git" target="_blank" class="btn btn-primary">Ver GitHub</a>
          <a href="#contato" class="btn btn-secondary">Falar comigo</a>
        </div>
      </div>

      <div class="hero-card reveal">
        <h3>Resumo Profissional</h3>
        <ul>
          <li>Estudante de ADS</li>
          <li>Experiência em suporte técnico</li>
          <li>Conhecimento em HTML, CSS e Python</li>
          <li>Interesse em vagas de estágio e júnior</li>
        </ul>
      </div>
    </div>
  </section>

  <section id="sobre">
    <div class="container">
      <h2 class="section-title reveal">Sobre Mim</h2>
      <p class="section-subtitle reveal">
        Tenho interesse em tecnologia desde cedo e venho construindo minha base prática em manutenção,
        suporte técnico e desenvolvimento web. Meu objetivo é crescer profissionalmente e contribuir com soluções úteis e eficientes.
      </p>

      <div class="about-grid">
        <div class="card reveal">
          <h3>Formação</h3>
          <p>
            Atualmente curso <strong>Análise e Desenvolvimento de Sistemas (ADS)</strong> na
            <strong>UNINASSAU</strong>, buscando ampliar meus conhecimentos técnicos e evoluir na área de TI.
          </p>
        </div>

        <div class="card reveal">
          <h3>Experiência</h3>
          <p>
            Atuo com <strong>suporte técnico</strong>, manutenção preventiva e corretiva, instalação de sistemas,
            softwares e apoio a usuários no dia a dia da área de Tecnologia da Informação.
          </p>
        </div>
      </div>
    </div>
  </section>

  <section id="habilidades">
    <div class="container">
      <h2 class="section-title reveal">Habilidades</h2>
      <p class="section-subtitle reveal">Tecnologias e competências que fazem parte da minha base profissional.</p>

      <div class="skills-grid">
        <div class="card skill-item reveal"><h4>HTML5</h4><p>Estruturação de páginas web modernas.</p></div>
        <div class="card skill-item reveal"><h4>CSS3</h4><p>Estilização, layout responsivo e design visual.</p></div>
        <div class="card skill-item reveal"><h4>JavaScript</h4><p>Interatividade, menus, animações e comportamento da página.</p></div>
        <div class="card skill-item reveal"><h4>Python</h4><p>Lógica de programação e scripts simples.</p></div>
        <div class="card skill-item reveal"><h4>Suporte Técnico</h4><p>Atendimento e solução de problemas para usuários.</p></div>
        <div class="card skill-item reveal"><h4>Manutenção de PCs</h4><p>Limpeza, instalação e correção de falhas básicas.</p></div>
        <div class="card skill-item reveal"><h4>Windows</h4><p>Formatação, instalação e configuração do sistema.</p></div>
        <div class="card skill-item reveal"><h4>GitHub</h4><p>Versionamento e publicação de projetos.</p></div>
      </div>
    </div>
  </section>

  <section id="projetos">
    <div class="container">
      <h2 class="section-title reveal">Projetos em Destaque</h2>
      <p class="section-subtitle reveal">Alguns exemplos de projetos e práticas desenvolvidas para fortalecer minha jornada na área de TI.</p>

      <div class="projects-grid">
        <div class="project-card reveal">
          <h3>Tela de Login</h3>
          <p>Projeto criado para praticar estrutura de formulário, design visual e organização de interface.</p>
          <div class="tags">
            <span class="tag">HTML</span>
            <span class="tag">CSS</span>
          </div>
          <a href="https://github.com/ruben0192/Projeto.git" target="_blank" class="btn btn-secondary">Ver projeto</a>
        </div>

        <div class="project-card reveal">
          <h3>Tabela de Sistemas</h3>
          <p>Página desenvolvida para treinar estruturação de conteúdo, estilização e exibição organizada de informações.</p>
          <div class="tags">
            <span class="tag">HTML</span>
            <span class="tag">CSS</span>
          </div>
          <a href="https://github.com/ruben0192/Projeto.git" target="_blank" class="btn btn-secondary">Ver projeto</a>
        </div>

        <div class="project-card reveal">
          <h3>Projetos em Python</h3>
          <p>Exercícios e pequenos sistemas para praticar lógica, entrada de dados, condições e automação básica.</p>
          <div class="tags">
            <span class="tag">Python</span>
            <span class="tag">Lógica</span>
          </div>
          <a href="https://github.com/ruben0192/Projeto.git" target="_blank" class="btn btn-secondary">Ver projeto</a>
        </div>
      </div>

      <div class="stats-grid">
        <div class="card stat-box reveal"><h3>ADS</h3><p>Curso superior em andamento</p></div>
        <div class="card stat-box reveal"><h3>TI</h3><p>Foco em suporte e manutenção</p></div>
        <div class="card stat-box reveal"><h3>Web</h3><p>Desenvolvimento front-end em evolução</p></div>
        <div class="card stat-box reveal"><h3>GitHub</h3><p>Projetos publicados para portfólio</p></div>
      </div>
    </div>
  </section>

  <section id="contato">
    <div class="container">
      <h2 class="section-title reveal">Contato</h2>
      <p class="section-subtitle reveal">Se quiser falar sobre oportunidades, projetos ou parcerias, estou disponível.</p>

      <div class="contact-grid">
        <div class="contact-card reveal">
          <h3>Email</h3>
          <a href="mailto:rubenilsonjunior63@gmail.com">rubenilsonjunior63@gmail.com</a>
        </div>

        <div class="contact-card reveal">
          <h3>WhatsApp</h3>
          <a href="https://wa.me/5579988455771" target="_blank">(79) 98845-5771</a>
        </div>

        <div class="contact-card reveal">
          <h3>GitHub</h3>
          <a href="https://github.com/ruben0192/Projeto.git" target="_blank">github.com/ruben0192/Projeto</a>
        </div>

        <div class="contact-card reveal">
          <h3>Localização</h3>
          <p>Riachuelo - Sergipe, Brasil</p>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <p>© 2026 Rubenilson Júnior • Portfólio Profissional de Tecnologia da Informação</p>
  </footer>

  <script>
    const menuToggle = document.getElementById('menuToggle');
    const navLinks = document.getElementById('navLinks');

    menuToggle.addEventListener('click', () => {
      navLinks.classList.toggle('active');
    });

    document.querySelectorAll('.nav-links a').forEach(link => {
      link.addEventListener('click', () => {
        navLinks.classList.remove('active');
      });
    });

    const reveals = document.querySelectorAll('.reveal');

    function revealOnScroll() {
      reveals.forEach(item => {
        const windowHeight = window.innerHeight;
        const revealTop = item.getBoundingClientRect().top;
        const revealPoint = 100;

        if (revealTop < windowHeight - revealPoint) {
          item.classList.add('active');
        }
      });
    }

    window.addEventListener('scroll', revealOnScroll);
    revealOnScroll();
  </script>
</body>
</html>
