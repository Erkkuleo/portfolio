<script>
  import Topbar from '$lib/Topbar.svelte';
  let hov = $state(null);

  const blue  = "#5577bf";
  const paper = "#f4f1ea";
  const ink   = "#15151a";

  const projects = [
    { n: "08", year: "2025", title: "Regenie Nonlinear", where: "Solo", tag: "Research", desc: "A fork of REGENIE 4.1.2 extending whole-genome regression with nonlinear phenotype modelling.", href: "/projects/regenie-nonlinear" },
  ];
</script>

<svelte:head>
  <title>Projects — Erkka Kiukkonen</title>
</svelte:head>

<div class="page" style:background={paper} style:color={ink}>
  <Topbar />

  <section class="work">
    <div class="section-head" style:border-color={ink + '22'}>
      <div class="eyebrow">All projects · 2025 – 2026</div>
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
</div>

<style>
  .page {
    font-family: 'Söhne', 'Inter Tight', 'Helvetica Neue', Helvetica, Arial, sans-serif;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
  }
  .work { padding: 0 3.5rem 6rem; }
  .section-head {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    border-bottom: 1px solid;
    padding: 3rem 0 1rem;
    margin-bottom: 0.5rem;
  }
  .eyebrow { font-size: 12px; letter-spacing: 0.22em; text-transform: uppercase; opacity: 0.55; }
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
  .italic-accent { font-family: 'Newsreader', 'Times New Roman', serif; font-style: italic; font-weight: 400; }
  .proj-tag { margin-left: 0.5rem; font-size: 22px; vertical-align: baseline; }
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

  @media (max-width: 960px) {
    .work { padding-left: 1.5rem; padding-right: 1.5rem; }
    .proj-row { grid-template-columns: 36px 1fr; row-gap: 0.25rem; }
    .proj-desc, .proj-where, .proj-year { grid-column: 2; text-align: left; }
  }
</style>
