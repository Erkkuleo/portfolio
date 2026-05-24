<script>
  const blue  = "#5577bf";
  const paper = "#f4f1ea";
  const ink   = "#15151a";
</script>

<svelte:head>
  <title>Solder & Sketch — Erkka Kiukkonen</title>
  <meta name="description" content="Field-notebook of homemade circuits, PCB layouts, first-pass schematics." />
</svelte:head>

<div class="page" style:background={paper} style:color={ink}>
  <header class="topbar" style:border-color={ink + '22'}>
    <a href="/" class="back" style:color={ink}>← Index</a>
    <span class="tag" style:color={blue}>Hardware</span>
  </header>

  <section class="hero">
    <div class="meta-col">
      <div class="eyebrow">04 · 2024</div>
      <dl class="meta">
        <dt>Role</dt>    <dd>Solo</dd>
        <dt>Stack</dt>   <dd>KiCad · C · RP2040</dd>
        <dt>Status</dt>  <dd>Ongoing</dd>
      </dl>
    </div>

    <div class="title-col">
      <h1 class="title">
        Solder<br />&amp;<br />
        <span class="italic-accent" style:color={blue}>Sketch</span>
      </h1>
      <p class="lede">
        Field-notebook of homemade circuits, PCB layouts, and first-pass schematics. A record of things that worked and things that smoked.
      </p>
    </div>
  </section>

  <div class="placeholder" style:border-color={ink + '18'}>
    <span class="placeholder-label">[ project image / demo ]</span>
  </div>

  <section class="body">
    <div class="col-offset">
      <h2 class="h2">What this is</h2>
      <p>Not a product — a log. Every circuit I've built since 2024 lives here: schematic, layout, notes on what failed, and what I'd change. The 36-key keyboard is the current chapter.</p>

      <h2 class="h2">Current build</h2>
      <p>A split 36-key keyboard around an RP2040, hand-wired on a custom PCB. Low-profile Choc v2 switches, QMK firmware, wireless half still in progress. The case is designed in FreeCAD and will be milled from aluminium.</p>

      <h2 class="h2">What I keep learning</h2>
      <p>Hardware has no undo. Every mistake is physical and costs real time. That constraint forces a clarity of thought that software sometimes lets you skip — you can't ship a schematic and patch it later.</p>
    </div>
  </section>

  <footer class="footer" style:border-color={ink + '22'}>
    <a href="/projects/echo-protocol" style:color={ink}>← Echo Protocol</a>
    <a href="/" style:color={blue}>Back to index →</a>
  </footer>
</div>

<style>
  .page {
    font-family: 'Söhne', 'Inter Tight', 'Helvetica Neue', Helvetica, Arial, sans-serif;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
  }
  .topbar {
    padding: 2rem 3.5rem;
    border-bottom: 1px solid;
    display: flex;
    align-items: baseline;
    justify-content: space-between;
  }
  .back { font-size: 13px; text-decoration: none; opacity: 0.7; }
  .back:hover { opacity: 1; }
  .tag { font-size: 11px; letter-spacing: 0.22em; text-transform: uppercase; }

  .hero {
    padding: 5rem 3.5rem 4rem;
    display: grid;
    grid-template-columns: 1fr 3fr;
    gap: 3rem;
    align-items: start;
  }
  .eyebrow { font-size: 12px; letter-spacing: 0.22em; text-transform: uppercase; opacity: 0.5; margin-bottom: 2rem; }
  .meta { display: grid; grid-template-columns: max-content 1fr; column-gap: 1.5rem; row-gap: 0.6rem; font-size: 13px; margin: 0; }
  .meta dt { opacity: 0.5; }
  .meta dd { margin: 0; }

  .title {
    margin: 0 0 2.5rem;
    font-size: clamp(64px, 10vw, 140px);
    line-height: 0.9;
    letter-spacing: -0.02em;
    font-weight: 500;
  }
  .italic-accent { font-family: 'Newsreader', 'Times New Roman', serif; font-style: italic; font-weight: 400; }
  .lede { margin: 0; font-size: 20px; line-height: 1.6; opacity: 0.8; max-width: 38rem; }

  .placeholder {
    margin: 0 3.5rem;
    border: 1px solid;
    aspect-ratio: 16/7;
    display: flex;
    align-items: center;
    justify-content: center;
    background: repeating-linear-gradient(45deg, #e7e2d6 0 10px, #efe9dc 10px 20px);
  }
  .placeholder-label { font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase; opacity: 0.4; }

  .body { padding: 5rem 3.5rem 6rem; }
  .col-offset { max-width: 40rem; margin-left: calc(25% + 3rem); }
  .h2 { font-size: 13px; letter-spacing: 0.18em; text-transform: uppercase; opacity: 0.5; margin: 2.5rem 0 0.75rem; }
  .body p { font-size: 17px; line-height: 1.75; opacity: 0.85; margin: 0 0 1rem; }

  .footer {
    padding: 2rem 3.5rem;
    border-top: 1px solid;
    display: flex;
    justify-content: space-between;
    font-size: 13px;
  }
  .footer a { text-decoration: none; }
  .footer a:hover { text-decoration: underline; }

  @media (max-width: 760px) {
    .hero { grid-template-columns: 1fr; padding: 3rem 1.5rem 2rem; }
    .placeholder, .body, .footer, .topbar { padding-left: 1.5rem; padding-right: 1.5rem; }
    .col-offset { margin-left: 0; max-width: 100%; }
  }
</style>
