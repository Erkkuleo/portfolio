<script>
  let hov = $state(null);

  const projects = [
    { n: "01", year: "2026", title: "Neural Canvas",     where: "Solo / studio", tag: "Interactive", desc: "AI-assisted generative art studio with collaborative paper-like brushes.", href: "/projects/neural-canvas" },
    { n: "02", year: "2025", title: "Quantum Dashboard", where: "Aalto · COS",   tag: "Systems",     desc: "Live monitoring surface for distributed services. Charts as sentences.",  href: "/projects/quantum-dashboard" },
    { n: "03", year: "2025", title: "Echo Protocol",     where: "Solo",          tag: "Identity",    desc: "Brand and product surface for a decentralised messaging network.",         href: "/projects/echo-protocol" },
    { n: "04", year: "2024", title: "Solder & Sketch",   where: "Solo",          tag: "Hardware",    desc: "Field-notebook of homemade circuits, PCB layouts, first-pass schematics.", href: "/projects/solder-and-sketch" },
  ];

  const blue  = "#5577bf";
  const paper = "#f4f1ea";
  const ink   = "#15151a";

  const nav = ["Work", "Now", "About", "Contact"];
  const linksRows = [
    ["Email",    "erkka.kiukkonen@gmail.com",     "mailto:erkka.kiukkonen@gmail.com"],
    ["GitHub",   "github.com/erkkuleo",            "https://github.com/erkkuleo"],
    ["LinkedIn", "in/erkka-kiukkonen",             "https://linkedin.com/in/erkka-kiukkonen"],
  ];
  const nowRows = [
    ["Studying", "Distributed Systems"],
    ["Building", "Custom 36-key keyboard"],
    ["Reading",  "DDIA — Kleppmann"],
    ["Drinking", "Filter, dark roast"],
  ];
</script>

<svelte:head>
  <title>Erkka Kiukkonen — Code, circuits, quiet ideas.</title>
  <meta name="description" content="B.Sc. Computer Science at Aalto University. A slow index of projects in code and hardware." />
</svelte:head>

<div
  class="page"
  style:background={paper}
  style:color={ink}
>
  <!-- Top bar -->
  <header class="topbar" style:border-color={ink + '22'}>
    <div class="brand">
      <span class="brand-name">Erkka Kiukkonen</span>
      <span class="dot">·</span>
      <span class="brand-role">B.Sc. Computer Science, Aalto</span>
    </div>
    <nav class="nav">
      {#each nav as l}
        <a href={"#" + l.toLowerCase()} class="navlink">
          <span>{l}</span>
          <span class="underline" style:background={blue}></span>
        </a>
      {/each}
    </nav>
  </header>

  <!-- Hero -->
  <section class="hero">
    <div class="hero-text">
      <div class="eyebrow">Helsinki · since 2003</div>

      <h1 class="title">
        Code, circuits,<br />
        and a few <span class="italic-accent" style:color={blue}>quiet ideas</span>.
      </h1>

      <p class="lede">
        I'm a <em class="serif">B.Sc. Computer Science</em> student at Aalto University. I write software, sketch hardware, and keep this page as a slow index of finished things and half-finished ones. Mostly the latter.
      </p>

      <div class="cta-row">
        <a href="#work" class="cta-primary" style:text-decoration-color={blue}>
          Selected work <span aria-hidden="true">→</span>
        </a>
        <a href="/cv.pdf" class="cta-secondary">CV (pdf) <span aria-hidden="true">↗</span></a>
        <a href="mailto:erkka.kiukkonen@gmail.com" class="cta-secondary">erkka.kiukkonen@gmail.com</a>
      </div>
    </div>

    <aside class="portrait-col">
      <div class="portrait">
        <div class="portrait-tint" style:--blue={blue}></div>
        <div class="portrait-label">
          [ portrait ]
          <div class="portrait-sub">/static/me.jpg</div>
        </div>
      </div>
      <dl class="meta">
        <dt>Location</dt>  <dd>Helsinki, FI</dd>
        <dt>Pronouns</dt>  <dd>he/him</dd>
        <dt>Languages</dt> <dd>fi · en · sv</dd>
        <dt>Status</dt>
        <dd class="status">
          <span class="pip" style:background={blue}></span>
          Open to projects
        </dd>
      </dl>
    </aside>
  </section>

  <!-- Selected work -->
  <section id="work" class="work">
    <div class="section-head" style:border-color={ink + '22'}>
      <div class="eyebrow">Selected work · 2024 – 2026</div>
      <a href="/projects" class="muted-link">All projects ↗</a>
    </div>

    <ol class="proj-list">
      {#each projects as p, i}
        <li>
        <a
          href={p.href}
          class="proj-row"
          class:active={hov === i}
          style:border-color={hov === i ? blue + '66' : ink + '1a'}
          onmouseenter={() => (hov = i)}
          onmouseleave={() => (hov = null)}
        >
          <span class="proj-n">{p.n}</span>
          <h3 class="proj-title">
            {p.title}
            <span class="italic-accent proj-tag" style:color={blue}>— {p.tag.toLowerCase()}</span>
          </h3>
          <p class="proj-desc">{p.desc}</p>
          <div class="proj-where">{p.where}</div>
          <div class="proj-year">{p.year}</div>
          <span class="proj-marker" style:background={blue} aria-hidden="true"></span>
        </a>
        </li>
      {/each}
    </ol>
  </section>

  <!-- About / Now -->
  <section id="about" class="about" style:border-color={ink + '22'}>
    <div class="about-head">
      <div class="eyebrow">About</div>
      <h2 class="h2">
        A short<br />
        <span class="italic-accent" style:color={blue}>self-portrait</span>.
      </h2>
    </div>

    <div class="about-body">
      <p>
        I grew up taking small electronics apart and not always putting them back together. That habit became Computer Science at <em class="serif">Aalto University</em>, where I'm finishing my bachelor's.
      </p>
      <p>
        Day to day I write a lot of TypeScript and a little Rust, draw schematics in KiCad, and try to keep my code as quiet as my soldering iron is loud.
      </p>
      <p>
        Outside the screen I cycle, read more than I finish, and brew filter coffee with more equipment than is reasonable.
      </p>
    </div>

    <div class="now" id="now">
      <div class="eyebrow">Currently</div>
      <ul class="now-list">
        {#each nowRows as [k, v]}
          <li style:border-color={ink + '18'}>
            <span class="now-k">{k}</span>
            <span class="now-v">{v}</span>
          </li>
        {/each}
      </ul>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="contact" style:border-color={ink + '22'}>
    <div class="contact-left">
      <div class="eyebrow">Contact</div>
      <h2 class="h2 h2-lg">
        Drop a <span class="italic-accent" style:color={blue}>line</span>.
      </h2>
      <p class="contact-sub">
        Email is the most reliable. I read everything; I reply to most.
      </p>
    </div>

    <ul class="links">
      {#each linksRows as [k, v, href]}
        <li style:border-color={ink + '1a'}>
          <a href={href} class="link-row">
            <span class="link-k">{k}</span>
            <span class="link-v">
              {v}
              <span class="link-underline" style:background={blue}></span>
            </span>
            <span class="link-arrow" style:color={blue}>↗</span>
          </a>
        </li>
      {/each}
    </ul>
  </section>

  <footer class="footer" style:border-color={ink + '22'}>
    <span>© Erkka Kiukkonen · 2026</span>
    <span>Handmade in Helsinki — SvelteKit</span>
    <span>v.5 · last edit 22.05.26</span>
  </footer>
</div>

<style>
  .page {
    font-family: 'Söhne', 'Inter Tight', 'Helvetica Neue', Helvetica, Arial, sans-serif;
    min-height: 100vh;
    font-feature-settings: "ss01", "ss02", "kern";
    -webkit-font-smoothing: antialiased;
  }

  .serif, .italic-accent {
    font-family: 'Newsreader', 'Times New Roman', Times, serif;
    font-weight: 400;
    font-style: italic;
  }

  /* ── Topbar ──────────────────────────────────────── */
  .topbar {
    padding: 2.5rem 3.5rem 1.5rem;
    border-bottom: 1px solid;
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    gap: 2rem;
  }
  .brand { display: flex; align-items: baseline; gap: 1rem; }
  .brand-name { font-size: 14px; letter-spacing: 0.18em; text-transform: uppercase; font-weight: 500; }
  .brand-role { font-size: 14px; opacity: 0.6; }
  .dot { opacity: 0.5; }
  .nav { display: flex; gap: 2rem; }
  .navlink {
    position: relative;
    font-size: 13px;
    text-decoration: none;
    color: inherit;
    opacity: 0.85;
  }
  .navlink:hover { opacity: 1; }
  .navlink .underline {
    position: absolute;
    left: 0; right: 0; bottom: -4px;
    height: 2px;
    transform: scaleX(0);
    transform-origin: left center;
    transition: transform 320ms cubic-bezier(.7,0,.2,1);
  }
  .navlink:hover .underline { transform: scaleX(1); }

  /* ── Hero ────────────────────────────────────────── */
  .hero {
    padding: 5rem 3.5rem 6rem;
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 2.5rem;
    align-items: start;
  }
  .eyebrow {
    font-size: 12px;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    opacity: 0.55;
  }
  .title {
    margin: 2rem 0 0;
    font-size: clamp(56px, 8.5vw, 120px);
    line-height: 0.92;
    letter-spacing: -0.015em;
    font-weight: 500;
    text-wrap: balance;
  }
  .italic-accent {
    font-style: italic;
  }
  .lede {
    margin: 3rem 0 0;
    max-width: 36rem;
    font-size: 19px;
    line-height: 1.6;
    opacity: 0.82;
  }
  .cta-row {
    margin-top: 2.5rem;
    display: flex;
    align-items: baseline;
    gap: 2rem;
    flex-wrap: wrap;
    font-size: 13px;
  }
  .cta-primary, .cta-secondary {
    color: inherit;
    text-decoration: none;
  }
  .cta-primary {
    text-decoration: underline;
    text-decoration-thickness: 1.5px;
    text-underline-offset: 6px;
  }
  .cta-secondary { opacity: 0.7; }
  .cta-secondary:hover { opacity: 1; }

  /* Portrait */
  .portrait-col { padding-top: 0.5rem; }
  .portrait {
    position: relative;
    aspect-ratio: 4 / 5;
    width: 100%;
    overflow: hidden;
    border-radius: 2px;
    background: repeating-linear-gradient(45deg,#e7e2d6 0 10px,#efe9dc 10px 20px);
  }
  .portrait-tint {
    position: absolute; inset: 0;
    background: radial-gradient(circle at 70% 25%, color-mix(in srgb, var(--blue) 14%, transparent), transparent 60%);
  }
  .portrait-label {
    position: absolute; inset: 0;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase;
    opacity: 0.5;
  }
  .portrait-sub { margin-top: 0.5rem; opacity: 0.7; }

  .meta {
    margin: 1.25rem 0 0;
    display: grid;
    grid-template-columns: max-content 1fr;
    column-gap: 1rem;
    row-gap: 0.5rem;
    font-size: 12px;
  }
  .meta dt { opacity: 0.5; }
  .meta dd { margin: 0; }
  .status { display: inline-flex; align-items: center; gap: 0.5rem; }
  .pip { width: 6px; height: 6px; border-radius: 9999px; display: inline-block; }

  /* ── Work ─────────────────────────────────────────── */
  .work { padding: 0 3.5rem 6rem; }
  .section-head {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    border-bottom: 1px solid;
    padding-bottom: 1rem;
    margin-bottom: 0.5rem;
  }
  .muted-link {
    font-size: 12px;
    color: inherit;
    text-decoration: none;
    opacity: 0.6;
  }
  .muted-link:hover { opacity: 1; }

  .proj-list { list-style: none; margin: 0; padding: 0; }
  .proj-list li { list-style: none; }
  .proj-row {
    position: relative;
    display: grid;
    grid-template-columns: 60px 5fr 4fr 1fr 1fr;
    align-items: baseline;
    gap: 1.5rem;
    border-bottom: 1px solid;
    padding: 1.75rem 0 1.75rem 1rem;
    transition: border-color 380ms;
    cursor: pointer;
    text-decoration: none;
    color: inherit;
  }
  .proj-n { font-size: 12px; letter-spacing: 0.18em; opacity: 0.5; }
  .proj-title {
    margin: 0;
    font-size: 36px;
    font-weight: 500;
    line-height: 1.05;
    letter-spacing: -0.01em;
    transition: transform 380ms cubic-bezier(.7,0,.2,1);
  }
  .proj-row.active .proj-title { transform: translateX(10px); }
  .proj-tag {
    margin-left: 0.5rem;
    font-size: 22px;
    vertical-align: baseline;
  }
  .proj-desc { margin: 0; font-size: 14px; opacity: 0.75; line-height: 1.5; }
  .proj-where { font-size: 12px; opacity: 0.6; }
  .proj-year  { font-size: 12px; opacity: 0.6; text-align: right; }
  .proj-marker {
    position: absolute;
    left: 0; top: 0;
    width: 3px; height: 100%;
    transform: scaleY(0);
    transform-origin: top center;
    transition: transform 380ms cubic-bezier(.7,0,.2,1);
  }
  .proj-row.active .proj-marker { transform: scaleY(1); }

  /* ── About / Now ──────────────────────────────────── */
  .about {
    padding: 4rem 3.5rem 6rem;
    border-top: 1px solid;
    display: grid;
    grid-template-columns: 4fr 5fr 3fr;
    gap: 2.5rem;
  }
  .h2 {
    margin: 1rem 0 0;
    font-size: 44px;
    font-weight: 500;
    line-height: 1;
    letter-spacing: -0.015em;
  }
  .h2-lg { font-size: clamp(48px, 6vw, 84px); }
  .about-body { font-size: 16px; line-height: 1.7; opacity: 0.85; }
  .about-body p { margin: 0 0 1.25rem; }
  .now-list { list-style: none; margin: 1rem 0 0; padding: 0; }
  .now-list li {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    border-bottom: 1px solid;
    padding-bottom: 0.5rem;
    margin-bottom: 0.75rem;
    font-size: 13.5px;
  }
  .now-k { opacity: 0.5; }

  /* ── Contact ──────────────────────────────────────── */
  .contact {
    padding: 4rem 3.5rem 5rem;
    border-top: 1px solid;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2.5rem;
    align-items: start;
  }
  .contact-sub {
    margin: 1.5rem 0 0;
    max-width: 28rem;
    font-size: 15px;
    opacity: 0.75;
  }
  .links { list-style: none; margin: 0; padding: 0; }
  .links li { border-bottom: 1px solid; }
  .link-row {
    display: grid;
    grid-template-columns: max-content 1fr max-content;
    align-items: baseline;
    gap: 1rem;
    padding: 1.25rem 0;
    color: inherit;
    text-decoration: none;
  }
  .link-k { font-size: 12px; letter-spacing: 0.22em; text-transform: uppercase; opacity: 0.55; }
  .link-v {
    position: relative;
    justify-self: end;
    font-size: 20px;
  }
  .link-underline {
    position: absolute;
    left: 0; right: 0; bottom: -2px;
    height: 2px;
    transform: scaleX(0);
    transform-origin: left center;
    transition: transform 360ms cubic-bezier(.7,0,.2,1);
  }
  .link-row:hover .link-underline { transform: scaleX(1); }
  .link-arrow { opacity: 0; transition: opacity 240ms; }
  .link-row:hover .link-arrow { opacity: 1; }

  /* ── Footer ───────────────────────────────────────── */
  .footer {
    padding: 2rem 3.5rem;
    border-top: 1px solid;
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    font-size: 11px;
    opacity: 0.55;
  }

  /* ── Responsive ───────────────────────────────────── */
  @media (max-width: 960px) {
    .hero, .about, .contact { grid-template-columns: 1fr; }
    .topbar, .hero, .work, .about, .contact, .footer { padding-left: 1.5rem; padding-right: 1.5rem; }
    .proj-row { grid-template-columns: 36px 1fr; row-gap: 0.25rem; }
    .proj-desc, .proj-where, .proj-year { grid-column: 2; text-align: left; }
    .nav { gap: 1.25rem; }
    .brand-role { display: none; }
  }
</style>
