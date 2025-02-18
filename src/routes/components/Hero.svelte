<script lang="ts">
  let subhead: HTMLParagraphElement;
  import SiteHeader from "$lib/SiteHeader.svelte";
</script>

<section class="hero">
  <div><SiteHeader /></div>
  <div class="stars"></div>
  <div class="image">
    <div class="full-size">
      <img alt="keyboard and monitor" height="450" src="/hero.svg" />
    </div>
    <div class="small-size">
      <img alt="keyboard" height="300" src="/keyboard.svg" />
      <img alt="monitor" height="200" src="/Screen.svg" />
    </div>
  </div>
  <div class="content">
    <div class="hero-copy">
      <h1>Weird</h1>
      <p bind:this={subhead}>a way to be on the web</p>
    </div>
  </div>
</section>

<style>
  .stars {
    background: url("/stars.avif");
    /* extend a bit more than the viewport */
    height: 100%;
    width: 100%;
    background-position: center;
  }

  section {
    display: grid;
    justify-items: center;
    min-height: 80svh;
    max-width: 100%;

    :global(& > div) {
      width: 100%;
      grid-column: 1/1;
      grid-row: 1/1;
    }
  }

  .content {
    display: grid;
    padding-top: 12em;
    padding-bottom: 8em;
    justify-items: center;
  }
  .hero-copy {
    text-align: center;

    h1 {
      font-family: "Rubik Mono One", monospace;
      font-weight: 400;
      font-size: min(16vw,13em);
      color: #fff5bf;
      text-shadow: -8px -8px #f55134;

      /* prefix required for all browsers */
      -webkit-text-stroke-width: 2.5px;
      -webkit-text-stroke-color: black;
    }

    p {
      color: white;
      font-weight: 700;
      font-size: 3em;

      @media (max-width: 1200px) {
        font-size: 2.5em;
      }

      @media (max-width: 800px) {
        font-size: 2em;
      }

      @media (max-width: 700px) {
        font-size: 1.5em;
      }
    }
  }

  .image {
    padding: 24rem 8rem;
    max-width: 1200px;

    .small-size {
      display: none;
    }

    @media (max-width: 800px) {
      .small-size {
        display: grid;
        grid-auto-flow: column;
        place-items: center;
        gap: 2em;
      }
      .full-size {
        display: none;
      }
    }
  }
</style>
