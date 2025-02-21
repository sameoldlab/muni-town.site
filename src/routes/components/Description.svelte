<script>
  let {profiles = [{name: 'first'}]} = $props()
</script>
<section>
  <div class="container">
    <h2>Cultivate your personal space on the interwebs</h2>
    <p class="subhead">Ipsum perspiciatis magnam, itaque non nemo quos provident, dolores voluptas eius inventore omnis ea tenetur vitae nisi.
    </p>
    <div class="cards">
      {#each profiles as profile}
        <div> {profile.name} </div>
      {/each}
    </div>
    <div class="stack">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum perspiciatis magnam, itaque non nemo quos provident, dolores voluptas eius inventore omnis ea tenetur vitae nisi. Animi dolor dolore quos est.</div>
  </div>
</section>

<style>
  section {
    background: var(--purple);
    border-top: 2px solid black;
    text-align: center;
  }
  h2 {font-size: 2.5em;}

</style>
