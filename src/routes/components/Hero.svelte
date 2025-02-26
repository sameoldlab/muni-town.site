<script lang="ts">
  let subhead: HTMLParagraphElement;
  import SiteHeader from "$lib/SiteHeader.svelte";
    import Cta from "./hero/Cta.svelte";
  function typeWriter(
    element: HTMLElement,
    text: string,
    speed = 500,
    fn: () => void,
  ) {
    let i = 0;
    let lastTime = 0;

    function animate(current: number) {
      const delta = current - lastTime;
      if (delta >= Math.random() * speed + i * 7 && i < text.length) {
        lastTime = current;
        element.textContent += text.charAt(i);
        i++;
      }
      if (i < text.length) {
        requestAnimationFrame(animate);
      }
      if (i === text.length) {
        fn();
      }
    }

    animate(0);
  }
  $effect(() => {
  if(window.matchMedia('(prefers-reduced-motion: reduce)').matches) return 
    let txt = subhead.innerText;
    subhead.innerText = "";
    subhead.dataset.typing = "true";
    console.log(subhead.dataset.typing);
    typeWriter(subhead, txt, undefined, () => {
      subhead.dataset.typing = "false";
      console.log(subhead.dataset.typing);
    });
  });
</script>

<section class="hero">
  <div class="header"><SiteHeader /></div>
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
      <p class="subhead" data-typing="true" bind:this={subhead}>
        a way to be on the web!
      </p>
    </div>
    <Cta/>
  </div>
</section>

<style>
  section {
    display: grid;
    grid-template-rows: min-content 1fr;
    justify-items: center;
    min-height: 80svh;
    max-width: 100%;
    background: linear-gradient(
      180deg,
      var(--p1),
      var(--p2) 80%
    );
    & > div {
      width: 100%;
      grid-column: 1/1;
      grid-row: 2/-1;
    }
    .header {
      grid-column: 1/1;
      grid-row: 1/1;
      z-index: 1;
    }
  }
  .stars {
    background: url("/stars.avif");
    /* extend a bit more than the viewport */
    height: 100%;
    width: 100%;
    background-position: center;
    position: relative;
    grid-column: 1/1;
    grid-row: 1/-1;

    &:before,
    &:after {
      content: "";
      background: url("/cloud.svg");
      background-repeat: no-repeat;
      position: absolute;
      bottom: 10vh;
      /* actual size of the image */
      height: 170px;
      width: 240px;
    }
  }

  .content {
    display: grid;
    padding-top: 2em;
    padding-bottom: 8em;
    justify-items: center;
    z-index: 1;
  }
  @keyframes pulse {
    50% {
      opacity: 0;
    }
  }
  @media (prefers-reduced-motion: no-preference) {
    [data-typing="true"]::after {
      content: "|";
      animation: pulse 1.3s step-start infinite;
    }
  }
  .hero-copy {
    text-align: center;

    h1 {
      font-family: "Rubik Mono One", monospace;
      font-weight: 400;
      font-size: min(16vw, 10em);
      color: var(--yellow);
      text-shadow: -8px -8px var(--orange);

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
    padding: 9rem 8rem;
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
