<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Het Snaplab – Gewoon uitgelegd</title>
  <style>
    :root {
      --bg: #bfd4ec;
      --accent: #f15a22;
      --dark: #2a1e1f;
      --text: #2d2324;
      --white: #ffffff;
      --soft: #eef4fb;
      --card: #dbe7f5;
      --shadow: 0 18px 40px rgba(32, 24, 24, 0.12);
      --radius: 26px;
      --max: 1240px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.5;
    }

    img {
      max-width: 100%;
      display: block;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .container {
      width: min(100% - 40px, var(--max));
      margin: 0 auto;
    }

    /* NAV */
    .site-header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(191, 212, 236, 0.95);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(42, 30, 31, 0.06);
    }

    .nav {
      min-height: 92px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 18px;
      font-weight: 700;
      color: var(--accent);
    }

    .brand-mark {
      font-size: 78px;
      line-height: 0.7;
      font-weight: 900;
      transform: translateY(5px);
    }

    .brand-name {
      font-size: 1.5rem;
      letter-spacing: 0.02em;
    }

    .menu {
      display: flex;
      gap: 34px;
      flex-wrap: wrap;
      align-items: center;
    }

    .menu a {
      color: var(--accent);
      font-size: 1.15rem;
      font-weight: 700;
      transition: 0.25s ease;
    }

    .menu a:hover {
      opacity: 0.75;
      transform: translateY(-1px);
    }

    /* HERO */
    .hero {
      padding: 30px 0 0;
    }

    .hero-panel {
      position: relative;
      min-height: 760px;
      border-radius: 0 0 0 0;
      overflow: hidden;
      background:
        linear-gradient(90deg, rgba(255,255,255,0.28) 0%, rgba(191,212,236,0.32) 45%, rgba(191,212,236,0.92) 68%, rgba(191,212,236,0.98) 100%),
        url("images/hero.jpg") center left / cover no-repeat;
    }

    .hero-content {
      position: relative;
      z-index: 2;
      width: min(100%, 540px);
      margin-left: auto;
      padding: 70px 70px 130px 20px;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
    }

    .hero-kicker {
      font-size: clamp(2rem, 4vw, 4.25rem);
      font-weight: 800;
      color: var(--dark);
      margin-bottom: 28px;
      line-height: 1.05;
    }

    .hero-title {
      font-size: clamp(4.6rem, 10vw, 9rem);
      line-height: 0.92;
      color: var(--dark);
      font-weight: 900;
      letter-spacing: -0.04em;
    }

    .hero-subtitle {
      margin-top: 18px;
      margin-left: auto;
      font-size: clamp(1.4rem, 2.5vw, 2.3rem);
      font-weight: 800;
      color: var(--dark);
    }

    .quote-mark {
      color: var(--dark);
      display: inline-block;
      transform: translateY(14px);
    }

    /* Intro band */
    .intro-band {
      background: var(--dark);
      color: var(--white);
      padding: 58px 0 70px;
      position: relative;
      overflow: hidden;
    }

    .intro-wrap {
      display: grid;
      grid-template-columns: 1.05fr 1fr;
      gap: 40px;
      align-items: center;
      position: relative;
    }

    .intro-text {
      max-width: 480px;
      font-size: 1.1rem;
      color: rgba(255,255,255,0.95);
      position: relative;
      z-index: 2;
    }

    .intro-text p {
      margin-bottom: 20px;
      font-size: clamp(1.1rem, 1.8vw, 1.35rem);
      line-height: 1.4;
    }

    .btn {
      display: inline-block;
      background: var(--accent);
      color: var(--white);
      font-weight: 700;
      padding: 16px 34px;
      border-radius: 999px;
      transition: 0.25s ease;
      box-shadow: 0 10px 24px rgba(241, 90, 34, 0.22);
    }

    .btn:hover {
      transform: translateY(-2px);
      opacity: 0.92;
    }

    .intro-visual {
      position: relative;
      min-height: 220px;
      z-index: 1;
    }

    .intro-visual svg {
      width: 100%;
      height: 100%;
      display: block;
    }

    .intro-cta {
      position: absolute;
      right: 20px;
      bottom: 36px;
    }

    /* Sections */
    section {
      padding: 90px 0;
    }

    .section-title {
      font-size: clamp(2.2rem, 4vw, 4rem);
      line-height: 1;
      font-weight: 900;
      color: var(--dark);
      margin-bottom: 28px;
      letter-spacing: -0.03em;
    }

    .section-intro {
      max-width: 880px;
      font-size: 1.16rem;
      margin-bottom: 26px;
    }

    .two-col {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 40px;
      align-items: start;
    }

    .text-block p {
      margin-bottom: 18px;
      font-size: 1.08rem;
    }

    .feature-list {
      list-style: none;
      display: grid;
      gap: 16px;
      margin-top: 28px;
    }

    .feature-list li {
      background: rgba(255,255,255,0.55);
      border: 1px solid rgba(42, 30, 31, 0.08);
      padding: 18px 20px;
      border-radius: 18px;
      box-shadow: var(--shadow);
      font-weight: 700;
    }

    .feature-list span {
      color: var(--accent);
      display: block;
      margin-bottom: 6px;
      font-size: 0.95rem;
    }

    /* Cards */
    .cards {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 24px;
      margin-top: 34px;
    }

    .card {
      background: rgba(255,255,255,0.62);
      border: 1px solid rgba(42, 30, 31, 0.08);
      border-radius: var(--radius);
      padding: 28px;
      box-shadow: var(--shadow);
    }

    .card h3 {
      font-size: 1.5rem;
      line-height: 1.1;
      color: var(--dark);
      margin-bottom: 16px;
    }

    .card p {
      margin-bottom: 14px;
    }

    .card ul {
      padding-left: 20px;
      margin-bottom: 18px;
    }

    .card li {
      margin-bottom: 10px;
    }

    .card .link {
      color: var(--accent);
      font-weight: 700;
    }

    .why-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 20px;
      margin-top: 30px;
    }

    .why-item {
      background: var(--dark);
      color: var(--white);
      padding: 26px 22px;
      border-radius: 24px;
      min-height: 180px;
      box-shadow: var(--shadow);
    }

    .why-item h4 {
      color: var(--accent);
      margin-bottom: 12px;
      font-size: 1.1rem;
    }

    /* Contact */
    .contact {
      padding-bottom: 120px;
    }

    .contact-box {
      background: var(--dark);
      color: var(--white);
      border-radius: 32px;
      padding: 38px;
      box-shadow: var(--shadow);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
    }

    .contact-box h3 {
      font-size: 2rem;
      margin-bottom: 14px;
    }

    .contact-box p,
    .contact-box li {
      color: rgba(255,255,255,0.92);
      font-size: 1.05rem;
    }

    .contact-list {
      list-style: none;
      display: grid;
      gap: 14px;
      margin: 20px 0;
    }

    .contact-form {
      display: grid;
      gap: 14px;
    }

    .contact-form input,
    .contact-form textarea {
      width: 100%;
      border: 0;
      border-radius: 16px;
      padding: 16px 18px;
      font: inherit;
      color: var(--text);
    }

    .contact-form textarea {
      min-height: 150px;
      resize: vertical;
    }

    .contact-form button {
      border: 0;
      cursor: pointer;
      width: fit-content;
    }

    footer {
      padding: 30px 0 50px;
      color: rgba(42, 30, 31, 0.8);
      font-weight: 700;
    }

    @media (max-width: 1100px) {
      .hero-panel {
        min-height: 680px;
        background:
          linear-gradient(180deg, rgba(255,255,255,0.18) 0%, rgba(191,212,236,0.48) 48%, rgba(191,212,236,0.95) 100%),
          url("images/hero.jpg") center left / cover no-repeat;
      }

      .hero-content {
        width: 100%;
        max-width: 700px;
        margin-left: auto;
        padding: 60px 30px 90px;
      }

      .cards,
      .why-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }

      .two-col,
      .contact-box,
      .intro-wrap {
        grid-template-columns: 1fr;
      }

      .intro-cta {
        position: static;
        margin-top: 20px;
      }
    }

    @media (max-width: 760px) {
      .nav {
        align-items: flex-start;
        padding: 18px 0;
        flex-direction: column;
      }

      .menu {
        gap: 16px 22px;
      }

      .brand-mark {
        font-size: 58px;
      }

      .brand-name {
        font-size: 1.2rem;
      }

      .hero-panel {
        min-height: 600px;
      }

      .hero-content {
        padding: 40px 22px 60px;
      }

      .hero-subtitle {
        margin-left: 0;
      }

      .cards,
      .why-grid {
        grid-template-columns: 1fr;
      }

      section {
        padding: 70px 0;
      }

      .contact-box {
        padding: 28px 22px;
      }
    }
  </style>
</head>
<body>

  <header class="site-header">
    <div class="container nav">
      <a href="#home" class="brand" aria-label="Ga naar home">
        <span class="brand-mark">“</span>
        <span class="brand-name">Snaplab</span>
      </a>

      <nav class="menu">
        <a href="#home">Home</a>
        <a href="#voor-wie">Voor wie</a>
        <a href="#aanbod">Ons aanbod</a>
        <a href="#over-ons">Over ons</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="hero-panel">
        <div class="container">
          <div class="hero-content">
            <p class="hero-kicker">Welkom bij</p>
            <h1 class="hero-title">
              Snap<br />
              lab<span class="quote-mark">“</span>
            </h1>
            <p class="hero-subtitle">Gewoon uitgelegd</p>
          </div>
        </div>
      </div>

      <div class="intro-band">
        <div class="container intro-wrap">
          <div class="intro-text">
            <p>
              Gedrag kan soms ingewikkeld zijn. Wij helpen jou het te snappen.
              Wij zijn er voor professionals die vastlopen op onverklaarbaar gedrag
              en daar grip op willen krijgen.
            </p>
            <p>
              Via trainingen bieden wij heldere inzichten en direct toepasbare tips.
              Zonder jargon, mét impact.
            </p>
            <a class="btn" href="#contact">Meer weten? Neem contact op</a>
          </div>

          <div class="intro-visual" aria-hidden="true">
            <svg viewBox="0 0 800 300" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M30 220C160 310 279 282 355 152C399 76 418 24 468 24C518 24 526 123 500 171C470 226 463 260 510 272C593 292 639 137 738 63C774 37 818 28 860 40"
                    stroke="white" stroke-width="3.2" stroke-linecap="round"/>
              <path d="M818 28L857 37L828 63" stroke="white" stroke-width="3.2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            <div class="intro-cta">
              <a class="btn" href="#contact">Contact</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="voor-wie">
      <div class="container two-col">
        <div class="text-block">
          <h2 class="section-title">Voor wie?</h2>
          <p>
            Wij werken voor bedrijven en professionals die grip willen krijgen op gedrag
            dat schuurt, stoort of verwart.
          </p>
          <p>
            Wij bieden ondersteuning aan juristen, politie, artsen, winkelmedewerkers,
            organisaties die met GGZ-patiënten te maken hebben en nog veel meer.
            Samenwerken is een cruciaal onderdeel voor bijna elke professional en organisatie.
            Wij zorgen dat deze samenwerking weer soepel gaat lopen.
          </p>
          <p>
            Eigenlijk kunnen wij voor ieder bedrijf waar mensen met elkaar samenwerken
            van toevoeging zijn. Investeren in het snappen van de ander is namelijk
            nooit verloren tijd.
          </p>
        </div>

        <div>
          <ul class="feature-list">
            <li>
              <span>Wat je van ons mag verwachten</span>
              Gewoon taal: geen jargon, wel helderheid
            </li>
            <li>
              <span>Praktisch</span>
              Direct bruikbaar: inzichten die meteen het verschil maken in de praktijk
            </li>
            <li>
              <span>Communicatie</span>
              Van storing naar snapmoment: wij brengen de klik terug in communicatie
            </li>
            <li>
              <span>Actueel</span>
              De nieuwste wetenschappelijke inzichten direct in praktijk brengen
            </li>
          </ul>
        </div>
      </div>
    </section>

    <section id="aanbod">
      <div class="container">
        <h2 class="section-title">Ons aanbod</h2>
        <p class="section-intro">
          Onverklaarbaar gedrag zorgt bij veel professionals voor lastige situaties.
          Het Snaplab helpt om miscommunicatie, vertraging en frustratie te voorkomen
          of op te lossen met trainingen die praktisch, wetenschappelijk onderbouwd
          en direct toepasbaar zijn.
        </p>
        <p class="section-intro">
          Wij werken allebei in de GGZ en blijven up-to-date met de nieuwste ontwikkelingen.
          Daarom komen wij juist bij jullie langs om op de werkvloer toepasbare trainingen te geven.
        </p>

        <div class="cards">
          <article class="card">
            <h3>Psychische problematiek herkennen en snappen</h3>
            <p>Trainingen voor het beter begrijpen van gedrag en signalen.</p>
            <ul>
              <li>Herkennen en omgaan met PTSS</li>
              <li>Herkennen en omgaan met een licht verstandelijke beperking</li>
              <li>Herkennen en omgaan met psychose / schizofrenie</li>
              <li>Omgaan met psychische problemen zonder specifieke classificatie</li>
            </ul>
            <a class="link" href="#contact">Lees meer / schrijf in</a>
          </article>

          <article class="card">
            <h3>Omgaan met uitdagend gedrag in samenwerking of klantcontact</h3>
            <p>Praktische handvatten voor lastige communicatie en samenwerking.</p>
            <ul>
              <li>Werken met dominante of controlerende personen</li>
              <li>Motiveren van mensen die passief of teruggetrokken zijn</li>
              <li>Effectief blijven in emotionele of verwarrende situaties</li>
            </ul>
            <a class="link" href="#contact">Lees meer / schrijf in</a>
          </article>

          <article class="card">
            <h3>Maatwerk voor jouw organisatie</h3>
            <p>Specifieke trainingen afgestemd op jullie vraagstuk.</p>
            <ul>
              <li>Gedrag begrijpen onder stress</li>
              <li>Omgaan met hoge werkdruk</li>
              <li>Zelfzorg op de werkvloer</li>
              <li>Trainingen op maat voor jullie praktijk</li>
            </ul>
            <a class="link" href="#contact">Vraag een maatwerktraining aan</a>
          </article>
        </div>
      </div>
    </section>

    <section id="cursus-detail">
      <div class="container">
        <h2 class="section-title">Detailpagina per cursus</h2>
        <div class="cards">
          <article class="card">
            <h3>Doelgroep</h3>
            <p>Voor professionals, teams en organisaties die gedrag beter willen begrijpen.</p>
          </article>

          <article class="card">
            <h3>Inhoud</h3>
            <p>Leerdoelen, modules, voorbeelden uit de praktijk en direct toepasbare tips.</p>
          </article>

          <article class="card">
            <h3>Praktische info</h3>
            <p>Duur, locatie, kosten en een duidelijke call-to-action om contact op te nemen of in te schrijven.</p>
          </article>
        </div>
      </div>
    </section>

    <section id="waarom">
      <div class="container">
        <h2 class="section-title">Waarom het Snaplab?</h2>
        <div class="why-grid">
          <div class="why-item">
            <h4>Gewoon taal</h4>
            <p>Geen jargon, wel helderheid.</p>
          </div>
          <div class="why-item">
            <h4>Direct bruikbaar</h4>
            <p>Inzichten die meteen het verschil maken in de dagelijkse praktijk.</p>
          </div>
          <div class="why-item">
            <h4>Van storing naar snapmoment</h4>
            <p>Wij brengen de klik terug in communicatie.</p>
          </div>
          <div class="why-item">
            <h4>Wetenschap + praktijk</h4>
            <p>De nieuwste wetenschappelijke inzichten direct vertaald naar de werkvloer.</p>
          </div>
        </div>
      </div>
    </section>

    <section id="over-ons">
      <div class="container two-col">
        <div class="text-block">
          <h2 class="section-title">Over ons</h2>
          <p>
            Wij zijn Annelein en Manon. We zijn beiden GZ-psychologen met een
            wetenschappelijke achtergrond en jarenlange ervaring in de praktijk.
          </p>
          <p>
            Naast ons werk bij Het Snaplab zijn we nog steeds actief in de geestelijke
            gezondheidszorg. We hebben veel gewerkt met mensen met psychose, trauma,
            een verstandelijke beperking of persoonlijkheidsstoornissen.
          </p>
          <p>
            We zien dagelijks hoe gedrag verkeerd wordt geïnterpreteerd, hoe mensen zich
            onbegrepen voelen en hoe dat leidt tot miscommunicatie, frustratie of uitsluiting.
            Niet uit onwil, maar uit onbegrip.
          </p>
          <p>
            Met Het Snaplab willen we professionals helpen om gedrag beter te snappen,
            zodat ze met meer vertrouwen, effectiviteit en menselijkheid kunnen handelen.
          </p>
        </div>

        <div>
          <ul class="feature-list">
            <li>
              <span>Onze visie</span>
              Als je snapt wat er speelt, kun je echt contact maken – en dat maakt het verschil.
            </li>
            <li>
              <span>Onze kracht</span>
              Wetenschappelijke kennis gecombineerd met praktijkervaring.
            </li>
            <li>
              <span>Onze aanpak</span>
              Helder, menselijk, toepasbaar en afgestemd op jullie werkveld.
            </li>
          </ul>
        </div>
      </div>
    </section>

    <section class="contact" id="contact">
      <div class="container">
        <div class="contact-box">
          <div>
            <h3>Contact</h3>
            <p>
              Neem contact op voor meer informatie, een training op maat,
              of om direct een aanvraag te doen.
            </p>

            <ul class="contact-list">
              <li><strong>E-mail:</strong> info@hetsnaplab.nl</li>
              <li><strong>Telefoon:</strong> 06 12 34 56 78</li>
              <li><strong>Website:</strong> www.hetsnaplab.nl</li>
            </ul>

            <p>
              Vul het formulier in of stuur direct een e-mail.
            </p>
          </div>

          <form class="contact-form">
            <input type="text" placeholder="Naam" />
            <input type="email" placeholder="E-mailadres" />
            <input type="text" placeholder="Organisatie" />
            <textarea placeholder="Waar wil je meer over weten?"></textarea>
            <button type="submit" class="btn">Verstuur</button>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      Het Snaplab — Gewoon uitgelegd
    </div>
  </footer>

</body>
</html>
