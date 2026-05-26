<script>
  const blue = "#5577bf";
  const ink  = "#15151a";

  const nav = ["Work", "Now", "About", "Contact"];
</script>

<header class="topbar" style:border-color={ink + '22'}>
  <div class="brand">
    <a href="/" class="brand-name">Erkka Kiukkonen</a>
    <span class="dot">·</span>
    <span class="brand-role">B.Sc. Computer Science, Aalto</span>
  </div>
  <nav class="nav">
    {#each nav as l}
      <a href={"/#" + l.toLowerCase()} class="navlink">
        <span>{l}</span>
        <span class="underline" style:background={blue}></span>
      </a>
    {/each}
  </nav>
</header>

<style>
  .topbar {
    padding: 2.5rem 3.5rem 1.5rem;
    border-bottom: 1px solid;
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    gap: 2rem;
  }
  .brand { display: flex; align-items: baseline; gap: 1rem; }
  .brand-name {
    font-size: 14px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    font-weight: 500;
    text-decoration: none;
    color: inherit;
  }
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

  @media (max-width: 960px) {
    .topbar { padding-left: 1.5rem; padding-right: 1.5rem; }
    .nav { gap: 1.25rem; }
    .brand-role { display: none; }
  }
</style>
