<script>
  let {
    profiles = [
      { name: "first" },
      { name: "first" },
      { name: "first" },
      { name: "first" },
    ],
  } = $props();
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
      {#each profiles as profile}
        <div>{profile.name}</div>
      {/each}
    </div>
    <div class="new-thing">
      <p>
        Weird is a brand new thing, but: Think of it as if WordPress and Notion
        had a Linktree-shaped baby. That is to say, a WordPress-type website
        engine with the editing experience of Notion and the simplicity of
        Linktree.
      </p>
      <div class="border"></div>
    </div>
  </div>
</section>

<style>
  :root {
    --offset: 200px;
  }
  section {
    text-align: center;
  }
  .first {
    background: linear-gradient(
      180deg,
      var(--p2),
      var(--p3),
      var(--p4)
    );
    padding-block-end: var(--offset);
  }
  h2,
  .subhead {
    color: white;
    max-width: 44rem;
    margin-inline: auto;
  }
  h2 {
    font-size: 3em;
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
    justify-content: space-between;
    margin-block-start: calc(-1 * var(--offset));
    padding-block: 3rem;
    div {
      height: calc(1.4 * var(--offset));
      min-width: 100px;
      border: 1px solid black;
    }
  }
</style>
