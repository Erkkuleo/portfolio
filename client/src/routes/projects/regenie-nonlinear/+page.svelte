<script>
  const blue  = "#5577bf";
  const paper = "#f4f1ea";
  const ink   = "#15151a";
</script>

<svelte:head>
  <title>Regenie Nonlinear — Erkka Kiukkonen</title>
  <meta name="description" content="A fork of REGENIE 4.1.2 extending whole-genome regression with nonlinear phenotype modelling for biobank-scale GWAS." />
</svelte:head>

<div class="page" style:background={paper} style:color={ink}>
  <header class="topbar" style:border-color={ink + '22'}>
    <a href="/" class="back" style:color={ink}>← Index</a>
    <span class="tag" style:color={blue}>Research</span>
  </header>

  <section class="hero">
    <div class="meta-col">
      <div class="eyebrow">05 · 2025</div>
      <dl class="meta">
        <dt>Role</dt>    <dd>Solo</dd>
        <dt>Stack</dt>   <dd>C / C++</dd>
        <dt>Status</dt>  <dd>In progress</dd>
      </dl>
    </div>

    <div class="title-col">
      <h1 class="title">
        Regenie<br />
        <span class="italic-accent" style:color={blue}>Nonlinear</span>
      </h1>
      <p class="lede">
        A fork of REGENIE 4.1.2 that extends the toolkit with nonlinear phenotype modelling for large-scale genome-wide association studies.
      </p>
    </div>
  </section>

  <div class="placeholder" style:border-color={ink + '18'}>
    <span class="placeholder-label">[ project image / demo ]</span>
  </div>

  <section class="body">
    <div class="col-offset">
      <h2 class="h2">The problem</h2>
      <p>REGENIE is the standard tool for whole-genome regression on biobank-scale data, but it assumes linear relationships between genotype and phenotype. Many complex traits don't fit that assumption — nonlinear effects go undetected.</p>

      <h2 class="h2">What I built</h2>
      <p>A fork of REGENIE 4.1.2 with a nonlinear calculation path added to the step 2 regression. The modification preserves the original tool's memory-efficient block-ridge design while allowing non-linear kernel functions to be swapped in.</p>

      <h2 class="h2">What I learned</h2>
      <p>Large C++ codebases built for performance have very little slack — every added allocation shows up in benchmarks. Getting the nonlinear path to run at biobank scale meant understanding the existing memory layout deeply before touching anything.</p>
    </div>
  </section>

  <section class="links-section" style:border-color={ink + '22'}>
    <div class="links-label">
      <div class="eyebrow">Resources</div>
    </div>
    <ul class="links">
      <li style:border-color={ink + '1a'}>
        <a href="https://github.com/Erkkuleo/regenie-nonlinear" class="link-row">
          <span class="link-k">GitHub</span>
          <span class="link-v">
            erkkuleo/regenie-nonlinear
            <span class="link-underline" style:background={blue}></span>
          </span>
          <span class="link-arrow" style:color={blue}>↗</span>
        </a>
      </li>
      <li style:border-color={ink + '1a'}>
        <a href="https://github.com/rgcgithub/regenie" class="link-row">
          <span class="link-k">Upstream</span>
          <span class="link-v">
            rgcgithub/regenie
            <span class="link-underline" style:background={blue}></span>
          </span>
          <span class="link-arrow" style:color={blue}>↗</span>
        </a>
      </li>
    </ul>
  </section>

  <footer class="footer" style:border-color={ink + '22'}>
    <a href="/" style:color={ink}>← Index</a>
    <a href="/projects/solder-and-sketch" style:color={blue}>Next: Solder & Sketch →</a>
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

  .links-section {
    padding: 4rem 3.5rem 5rem;
    border-top: 1px solid;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2.5rem;
    align-items: start;
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

  @media (max-width: 760px) {
    .hero { grid-template-columns: 1fr; padding: 3rem 1.5rem 2rem; }
    .placeholder, .body, .footer, .topbar { padding-left: 1.5rem; padding-right: 1.5rem; }
    .col-offset { margin-left: 0; max-width: 100%; }
    .links-section { grid-template-columns: 1fr; }
  }
</style>
