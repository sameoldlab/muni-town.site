<script>
  import p1 from "./profiles/profile-1.webp";
  import p2 from "./profiles/profile-2.webp";
  import p3 from "./profiles/profile-3.webp";
  import p4 from "./profiles/profile-4.webp";
  let { profiles = [p1, p2, p3, p4] } = $props();
</script>

<section>
  <div class="first container">
    <h2>Cultivate your personal space on the interwebs</h2>
    <p class="subhead">
      from scribble-saplings to digital garden, in communion with fellow
      weirdos.
    </p>
  </div>
  <div class="second container">
    <div class="cards">
      {#each profiles as src}
        <div class="card">
          <img {src} alt="" />
        </div>
      {/each}
    </div>
    <div class="new-thing">
      <p>
        Weird is a brand new thing, but: Think of it as if <a
          href="https://wordpress.org"
        >
          WordPress</a
        >
        and <a href="https://notion.com">Notion</a>
        had a Linktree-shaped baby. That is to say, a WordPress-type website engine
        with the editing experience of Notion and the simplicity of
        <a href="https://linktr.ee">Linktree</a>.
      </p>
      <div class="border"></div>
    </div>
  </div>
</section>

<style>
  :root {
    --offset: 200px;
  }
  a {
    color: inherit;
  }
  section {
    text-align: center;
  }
  .first {
    background: linear-gradient(180deg, var(--p2), var(--p3), var(--p4));
    padding-block-end: var(--offset);
  }
  h2,
  .subhead {
    color: white;
    max-width: 44rem;
    margin-inline: auto;
  }
  h2 {
    font-size: clamp(3em, 4vw, 4em);
    padding-block-end: 1rem;
  }

  .second {
    background: linear-gradient(
      180deg,
      var(--yellow),
      oklch(69.71% 0.1361 10.71)
    );
  }

  .new-thing {
    --main-width: 64rem;
    max-width: var(--main-width);
    margin-inline: auto;
    padding-block-end: 2rem;
    p {
      padding-block: 2rem;
    }
    .border {
      border-top: 1px solid black;
      height: 1px;
      max-width: calc(var(--main-width) - 10rem);
      margin-inline: auto;
      width: 100%;
    }
  }

  .cards {
    display: flex;
    gap: 2rem;
    max-width: 100%;
    justify-content: center;
    align-items: center;
    margin-block-start: calc(-1 * var(--offset));
    padding-block: 3rem;
    position: relative;
    div {
      overflow: hidden;
      position: relative;
      height: auto;
      max-width: 300px;
      aspect-ratio: 5/7;
      box-shadow:
        0px 10px 16px -3px oklch(0.6 0.01 45 / .1),
        0px 0px 30px 0px   oklch(0.6 0.01 45 / .1),
        0px 8px 7px 0px    oklch(0.6 0.01 45 / .1);
      &::before {
        content: "";
        position: absolute;
      }
      border: 2px solid white;
      border-radius: 1rem;
      transition-property: transform, rotate;
      transition-duration: 600ms;
      /* cooked overshoot */
      transition-timing-function: cubic-bezier(0, 0.74, 0.2, 1.6);
      img {
        position: relative;
        display: block;
        object-fit: cover;
      }

      &:nth-child(1) {
        background: var(--purple);
        rotate: -7.19deg;
        transform: translate(10px, 20px);
      }
      &:nth-child(2) {
        background: white;
        rotate: 7.89deg;
        transform: translate(0px, -8px);
        z-index: 1;
      }
      &:nth-child(3) {
        background: var(--yellow);
        rotate: -6.37deg;
        transform: translate(10px, -12px);
      }
      &:nth-child(4) {
        background: black;
        rotate: 8.93deg;
        transform: translate(-30px, -10px);
        z-index: 1;
      }
    }
    &:hover div {
      transform: translate(0);
      rotate: 0deg;
    }
  }
</style>
