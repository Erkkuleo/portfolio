<script>
  const blue  = "#5577bf";
  const paper = "#f4f1ea";
  const ink   = "#15151a";
</script>

<svelte:head>
  <title>Quantum Dashboard — Erkka Kiukkonen</title>
  <meta name="description" content="Live monitoring surface for distributed services. Charts as sentences." />
</svelte:head>

<div class="page" style:background={paper} style:color={ink}>
  <header class="topbar" style:border-color={ink + '22'}>
    <a href="/" class="back" style:color={ink}>← Index</a>
    <span class="tag" style:color={blue}>Systems</span>
  </header>

  <section class="hero">
    <div class="meta-col">
      <div class="eyebrow">02 · 2025</div>
      <dl class="meta">
        <dt>Role</dt>    <dd>Aalto · COS</dd>
        <dt>Stack</dt>   <dd>Rust · SvelteKit · WebSocket</dd>
        <dt>Status</dt>  <dd>Shipped</dd>
      </dl>
    </div>

    <div class="title-col">
      <h1 class="title">
        Quantum<br />
        <span class="italic-accent" style:color={blue}>Dashboard</span>
      </h1>
      <p class="lede">
        Live monitoring surface for distributed services. Charts as sentences — data that speaks before you ask it a question.
      </p>
    </div>
  </section>

  <div class="placeholder" style:border-color={ink + '18'}>
    <span class="placeholder-label">[ project image / demo ]</span>
  </div>

  <section class="body">
    <div class="col-offset">
      <h2 class="h2">The problem</h2>
      <p>Dashboards are usually walls of numbers. The team needed a surface that surfaced anomalies before they became incidents — something you could glance at, not study.</p>

      <h2 class="h2">What I built</h2>
      <p>A Rust backend ingesting service metrics over a fanout WebSocket pipeline, paired with a SvelteKit frontend that renders sparklines and plain-language summaries side by side. When a service dips, you see the chart and a sentence like "p99 latency up 40 % since 14:22."</p>

      <h2 class="h2">What I learned</h2>
      <p>The hardest part wasn't the data pipeline — it was deciding what not to show. Every metric added cognitive load. Cutting the panel count in half made the remaining panels actually useful.</p>
    </div>
  </section>

  <footer class="footer" style:border-color={ink + '22'}>
    <a href="/projects/neural-canvas" style:color={ink}>← Neural Canvas</a>
    <a href="/projects/echo-protocol" style:color={blue}>Next: Echo Protocol →</a>
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
